import datetime
import math

# declare and utialize variables
deadline = math
currentDate =math
strDeadline = "Feb"
totalNbrDays = 30  # (Nbr) number of days
nbrWeeks = 12
nbrDays = 30

# Todays's date
currentDate = datetime.date.today ()     #  11/09/2023
print (currentDate.strftime("%d %b, %Y" ))

# Ask user for the date of their deadline
strDeadline = input ("Please enter your deadline date ") # 02/09/2024    09 Feb, 2024          February 9,2024    3months

deadline = datetime.datetime.strptime(strDeadline, "%m/%d/%Y").date()


#Calculate number of days between the two dates
totalNbrDays = deadline - currentDate
print ( "What are the number of days before the deadline? " )

nbrDays = totalNbrDays.days%7


# The moduleo will return the remainder of the division
# which will tell us how many days are left

nbrDays = totalNbrDays.days%7

#display the result to the user

print ("You have %d weeks" %nbrWeeks + " and %d day " %nbrDays + " until your deadline.")

# OUTPUT      OUTPUT        OUTPUT                     OUTPUT                 OUTPUT
You have 12 weeks and 1 day until your deadline  
                   


