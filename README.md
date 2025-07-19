SanjayShriram Password Generator

This is a simple Python project that generates strong, random passwords based on user input. The password includes a mix of uppercase letters, lowercase letters, numbers, and symbols to ensure maximum security.


Project Description

The SanjayShriram Password Generator is a command-line application that allows users to generate secure passwords of custom length. It ensures that each password contains at least one lowercase letter, one uppercase letter, one number, and one special character.
This tool is great for personal use or as a beginner-level programming project to learn about string handling, random number generation, and input validation in Python.



 Features

  Personalized welcome message
  User defined password length
Mix of:
    Uppercase letters
    Lowercase letters
    Numbers
    Symbols
Ensures strong and valid password structure
Handles input errors

 Line by Line Explanation of Password Generator
 
Full Code for Reference:
python
import random
import string

def generate_password():
    print("Welcome to SanjayShriram Password Generator!")
    
    try:
        length = int(input("Enter the desired password length (minimum 4): "))
    except ValueError:
        print(" Invalid input. Please enter a number.")
        return

    if length < 4:
        print(" Password length should be at least 4 characters.")
        return

Characters to use in password
    lower = string.ascii_lowercase
    upper = string.ascii_uppercase
    digits = string.digits
    symbols = string.punctuation
 Combine all character sets
    all_chars = lower + upper + digits + symbols

Make sure the password includes at least one from each category
    password = [
        random.choice(lower),
        random.choice(upper),
        random.choice(digits),
        random.choice(symbols)
    ]

Fill the rest with random characters
    password += random.choices(all_chars, k=length - 4)

Shuffle the result so the fixed characters aren't always at the beginning
    random.shuffle(password)
convert list to string
    final_password = ''.join(password)

    print(f" Your generated password is: {final_password}")
 Run the function
generate_password()

Step by Step Explanation

`import random`

This line imports Python's `random` module, which lets us randomly pick characters for the password.

`import string`

The string module provides ready-made character sets like:

* lowercase letters (`a-z`)
* uppercase letters (`A-Z`)
* digits (`0-9`)
* punctuation (`!@#$%^&*`, etc.)


def generate_password():

Defines a **function** called `generate_password`. This is where all password logic will live.

print("Welcome to SanjayShriram Password Generator!")

Prints a **friendly welcome message** to the user, with your name included.

try:
We begin a `try...except` block to safely take numeric input from the user.

`length = int(input(...))`

Prompts the user to **enter the password length**, converts it to an integer using `int()`.

`except ValueError:`

If the user enters something that **isn't a number**, this catches the error and shows a warning.

`if length < 4:`

Makes sure the password has at least 4 characters (1 of each type: lowercase, uppercase, digit, symbol).

`lower = string.ascii_lowercase`

Stores all lowercase letters (`abcdefghijklmnopqrstuvwxyz`).

 `upper = string.ascii_uppercase`

Stores all uppercase letters (`ABCDEFGHIJKLMNOPQRSTUVWXYZ`).

---

### `digits = string.digits`

Stores all digits (`0123456789`).


 `symbols = string.punctuation`

Stores special characters (`!@#$%^&*()_+{}|:"<>?` and more).


 `all_chars = lower + upper + digits + symbols`

**Combines all character types** into one string so we can randomly pick from all of them later.



password = [...]

Creates a list with **one character from each required category** to ensure the password is secure:

* One lowercase
* One uppercase
* One digit
* One symbol



password += random.choices(..., k=length - 4)

Fills the remaining characters of the password with random choices from all characters.

`k=length - 4` means we subtract the 4 already added.



random.shuffle(password)

Shuffles the list so that the first 4 fixed characters aren’t always in the same place.



final_password = ''.join(password)

Joins the list of characters into a single password string.


print(...)

Displays the final generated password to the user.

generate_password()

Calls the function to run everything when the script is executed.

This code ensures:

* Random and secure password
* Meets basic security rules (uppercase, lowercase, digit, symbol)
* Simple and interactive command line interface

