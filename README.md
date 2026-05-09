# Password_Generator_using_python
A simple Python project that generates strong and secure random passwords based on the user’s desired length. The passwords include uppercase and lowercase letters, numbers, and special characters for better security.
import random
import string 

def generate_password(min_length):
    
    letters = string.ascii_letters
    digits = string.digits
    special = string.punctuation
    
    characters = letters + digits + special
    
    pwd = ""
    has_number = False
    has_special = False
    
    while not has_number or not has_special or len(pwd)< min_length:
        new_char = random.choice(characters)
        pwd += new_char
        
        if new_char in digits:
          has_number = True
        elif new_char in special:
          has_special = True
          
    return pwd 
    
min_length = int(input("Enter the minimum password length:"))
  
pwd = generate_password(min_length)
print("The generated password is:", pwd)
