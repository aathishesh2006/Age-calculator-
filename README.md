# Age-calculator-
from datetime import datetime

def calculate_age(birthdate: str):
    # Convert the birthdate from string to a datetime object
    birthdate = datetime.strptime(birthdate, "%Y-%m-%d")
    
    # Get today's date
    today = datetime.today()
    
    # Calculate the age
    age = today.year - birthdate.year
    
    # Check if the birthday has already occurred this year
    if today.month < birthdate.month or (today.month == birthdate.month and today.day < birthdate.day):
        age -= 1  # Decrease the age if the birthday hasn't passed yet
    
    return age

# Input the birthdate in YYYY-MM-DD format
birthdate = input("Enter your birthdate (YYYY-MM-DD): ")

# Calculate and print the age
age = calculate_age(birthdate)
print(f"You are {age} years old.")
