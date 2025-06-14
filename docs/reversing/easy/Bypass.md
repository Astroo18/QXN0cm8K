## CHALLENGE DESCRIPTION

**The Client is in full control. Bypass the authentication and read the key to get the Flag.**

For this challenge, I used Windows 11 and the program I used was **dnSpy (32-bit)**.

First, I analyzed the code until I found the following fragment:

![!\[\[Pasted image 20250614130420.png\]\]](<Images/Pasted image 20250614130420.png>)

Since the flags are using boolean values, we can set a breakpoint at this part and debug the code.

![!\[\[Pasted image 20250614130525.png\]\]](<Images/Pasted image 20250614130525.png>)

When the program opens, it asks for a username and a password.

![!\[\[Pasted image 20250614130559.png\]\]](<Images/Pasted image 20250614130559.png>)

We don’t know these values, but after pressing Enter (after entering the password), we can see the values in **dnSpy**.

![!\[\[Pasted image 20250614130627.png\]\]](<Images/Pasted image 20250614130627.png>)
What we need to do is set these values to `true`.

![!\[\[Pasted image 20250614130652.png\]\]](<Images/Pasted image 20250614130652.png>)

Next, we need to analyze the code further. I found another boolean flag; here we should place a breakpoint at the conditional check. This prevents the program from continuing before it validates the value.

![!\[\[Pasted image 20250614130817.png\]\]](<Images/Pasted image 20250614130817.png>)

Continue running the program, and it will now ask for a **secret key**.

![!\[\[Pasted image 20250614131020.png\]\]](<Images/Pasted image 20250614131020.png>)

If we enter a random value:

![!\[\[Pasted image 20250614131036.png\]\]](<Images/Pasted image 20250614131036.png>)

We can see the actual value of the secret key in **dnSpy**, or we can simply set the corresponding flag to `true`.

![!\[\[Pasted image 20250614131056.png\]\]](<Images/Pasted image 20250614131056.png>)

In this case, I set it to `true`.
![!\[\[Pasted image 20250614131121.png\]\]](<Images/Pasted image 20250614131121.png>)

Once we continue the program, we get the **flag**, because we set the required value to `true`.

![!\[\[Pasted image 20250614131244.png\]\]](<Images/Pasted image 20250614131244.png>)

We can also get the actual value from the secret key and it will retrieve the flag too.

Made by **Astro**