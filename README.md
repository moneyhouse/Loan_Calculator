import datetime
import math

# Function: Calculate monthly loan payment using the annuity formula
def calculate_loan_payment(principal, annual_rate, years):
    monthly_rate = annual_rate / 12 / 100
    months = years * 12
    payment = principal * (monthly_rate * (1 + monthly_rate)**months) / ((1 + monthly_rate)**months - 1)
    return round(payment, 2)

# User inputs: salary and bonus
try:
    salary = float(input("Enter your annual salary (e.g., 50000): "))
    bonus = float(input("Enter your bonus amount (e.g., 300): "))
except ValueError:
    print("Please enter valid numeric values for salary and bonus.")
    exit()

# Hourly rate calculation
hourly_rate = salary / (40 * 52)  # Assuming full-time hours
print(f"\nYour hourly rate is: ${round(hourly_rate, 2)} per hour.")

# Today's date
current_date = datetime.date.today()
print(f"Today's date: {current_date.strftime('%d %b, %Y')}")

# Deadline input
str_deadline = input("\nEnter your loan payoff deadline (MM/DD/YYYY): ")
try:
    deadline = datetime.datetime.strptime(str_deadline, "%m/%d/%Y").date()
except ValueError:
    print("Invalid date format. Please use MM/DD/YYYY.")
    exit()

# Loan details input
try:
    loan_amount = float(input("Enter loan amount (e.g., 10000): "))
    interest_rate = float(input("Enter annual interest rate (%) (e.g., 5): "))
    loan_years = int(input("Enter loan duration in years (e.g., 5): "))
except ValueError:
    print("Please enter valid numeric values for loan details.")
    exit()

# Calculate monthly payment
monthly_payment = calculate_loan_payment(loan_amount, interest_rate, loan_years)
print(f"\nYour estimated monthly loan payment: ${monthly_payment}")

# Time until deadline
days_until_deadline = (deadline - current_date).days
weeks = days_until_deadline // 7
days = days_until_deadline % 7
print(f"\nTime until deadline: {weeks} weeks and {days} days")

# Total paycheck amount
paycheck_total = salary + bonus
print(f"\nTotal paycheck (salary + bonus): ${paycheck_total}")

#  Machine Learning in Python certificate @ Alison.com
