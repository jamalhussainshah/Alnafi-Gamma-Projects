                    
                    
"""                    
Excercise No:4

Create a program that asks the user for a number and then prints out a list
of all the divisors of that number. (If you don’t know what a divisor is, 
it is a number that divides evenly into another number. For example, 13 is a 
divisor of 26 because 26 / 13 has no remainder.)
"""



num = int(input("Please choose a number to divide: "))

listRange = list(range(1,num+1))

divisorList = []

for number in listRange:
    if num % number == 0:
        divisorList.append(number)

print(divisorList)


############## OUTPUT ###########################

Please choose a number to divide: 23
[1, 23]


Please choose a number to divide: 12
[1, 2, 3, 4, 6, 12]


Please choose a number to divide: 6
[1, 2, 3, 6]

Please choose a number to divide: 7
[1, 7]
