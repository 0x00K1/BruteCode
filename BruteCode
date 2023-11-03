import random
import pyautogui
from termcolor import colored

# Constants
CHAR_SETS = {
    "1": "0123456789qwertyuiopasdfghjklzxcvbnm~!@#$%^&*()_+=",
    "2": "qwertyuiopasdfghjklzxcvbnm",
    "3": "0123456789",
    "4": "~!@#$%^&*()_+="
}

# DISCLAIMER: This script is for educational purposes only.
# Use only on systems you have explicit permission to test.

def print_logo():
    logo = '''\n
                                <  C   Y   B   E   R      K   U   N  />
    '''
    print(colored(logo, "red"))

def get_password_type():
    print(colored("1-Normal pass", 'green'),
          colored("2-Just letters", 'yellow'),
          colored("3-Just numbers", 'red'),
          colored("4-Symbols", "blue"))
    return input("Enter number of method: ")

def get_counter_preference():
    return input("Do you want a counter (Yes/No)? ").strip().lower()

def brute_force_password(character_set):
    password = pyautogui.password("Enter password here: ")
    guess_password = ''
    counter = 0
    
    while guess_password != password:
        guess_password = random.choices(character_set, k=len(password))
        print(">>>>>" + "".join(guess_password) + "<<<<<")
        counter += 1
        if "".join(guess_password) == password:
            print("Your password is: " + "".join(guess_password))
            return counter
    return None

def main():
    print_logo()
    password_type = get_password_type()
    
    if password_type not in CHAR_SETS:
        print(colored("Please just enter the number of the method", 'red'))
        return
    
    counter_preference = get_counter_preference()
    character_set = list(CHAR_SETS[password_type])
    
    attempts = brute_force_password(character_set)
    
    if attempts is not None and counter_preference in ['yes', 'y']:
        print(f"Password cracked after {attempts} attempts.")

if __name__ == "__main__":
    main()
