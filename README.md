# Loan_Calculator
import math

# Function to calculate loan payment
def calculate_loan_payment(principal, annual_rate, years):
    monthly_rate = annual_rate / 12 / 100
    months = years * 12
    payment = principal * (monthly_rate * (1 + monthly_rate)**months) / ((1 + monthly_rate)**months - 1)
    return round(payment, 2)

# User inputs salary and bonus
salary = float(input("Please enter your yearly salary: "))  # Example: 50000
bonus = float(input("Please enter your bonus: "))  # Example: 300
hourly_rate = salary / (40 * 52)  # Assuming 40 hours per week

print(f"Your hourly rate is: ${round(hourly_rate, 2)} per hour.")

# Loan details
loan_amount = float(input("Enter loan amount: "))  # Example: 10000
interest_rate = float(input("Enter annual interest rate (%): "))  # Example: 5
loan_years = int(input("Enter loan term (years): "))  # Example: 5

# Calculate monthly loan payment
monthly_payment = calculate_loan_payment(loan_amount, interest_rate, loan_years)

print(f"Your monthly loan payment would be: ${monthly_payment}")

# Convert salary and bonus to float again (if needed for calculations)
paycheckAmount = salary + bonus

print(f"Total paycheck amount: ${paycheckAmount}")

# Monthly loan payment will be: $188.71
# Total paycheck amount: $50300.0                      

#  Machine Learning in Python certificate @ Alison.com
