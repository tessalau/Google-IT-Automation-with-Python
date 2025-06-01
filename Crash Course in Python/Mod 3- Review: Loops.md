Question 1

Fill in the blanks to print the numbers 1 through 7.
``` python
number = 1 # Initialize the variable
while number<8: # Complete the while loop condition
    print(number, end=" ")
    number+=1 # Increment the variable

# Should print 1 2 3 4 5 6 7
```

Question 2

 Find and correct the error in the for loop below.  The loop should check each number from 1 to 5 and identify if the number is odd or even.  
 ``` python
for number in range(5):
    if number % 2 != 0:
        print("even")
    else:
        print("odd")


# Should print:
# odd
# even
# odd
# even
# odd
```
Question 3

Fill in the blanks to complete the “factorial” function. This function will accept an integer variable “n” through the function parameters and produce the factorials of this number (by multiplying this value by every number less than the original number [n*(n-1)], excluding 0).  To do this, the function should:

accept an integer variable “n” through the function parameters;

initialize a variable “result” to the value of the “n” variable;

iterate over the values of “n” using a while loop until “n” is equal to 0;

starting at n-1, multiply the result by the current “n” value;

decrement “n” by -1.

 For example, factorial 3 would return the value of 3*2*1, which would be 6.
 ``` python
def factorial(n):
    result = n
    n -= 1
    while n>0: # The while loop should execute as long as n is greater than 0
        result *= n # Multiply the current result by the current value of n
        n-=1 # Decrement the appropriate variable by -1
    return result


print(factorial(3)) # Should print 6
print(factorial(9)) # Should print 362880
print(factorial(1)) # Should print 1
```

Question 4

Fill in the blanks to complete the “sequence” function. This function should print a sequence of numbers in descending order, from the given "high" variable to the given "low" variable.  The range should make the loop run two times. Complete the range sequences in the nested loops so that the “sequence(1, 3)” function call prints the following:

3, 2, 1

3, 2, 1
``` python
def sequence(low, high):
    # Outer loop runs twice to create two rows
    for x in range(2):  
        # Inner loop prints numbers from 'high' to 'low' (descending order)
        for y in range(high, low - 1, -1):  # Fix: start at 'high', go down to 'low'
            if y == low:  
                # Don’t print a comma after the last item
                print(str(y))  
            else:  
                # Print a comma and a space between numbers
                print(str(y), end=", ")  


sequence(1, 3)
# Should print the sequence 3, 2, 1 two times, as shown above.
```

Question 5

Fill in the blanks to complete the “countdown” function. This function should begin at the “start” variable, which is an integer that is passed to the function,  and count down to 0. Complete the code so that a function call like “countdown(2)” will return the numbers “2,1,0”.
``` python

def countdown(start):
    x = start
    if x > 0:
        return_string = "Counting down to 0: "
        while x >= 0 : # Complete the while loop
            return_string+=str(x) # Add the numbers to the "return_string"
            if x > 0:
                return_string += ","
            x-=1 # Decrement the appropriate variable
    else:
        return_string = "Cannot count down to 0"
    return return_string


print(countdown(10)) # Should be "Counting down to 0: 10,9,8,7,6,5,4,3,2,1,0"
print(countdown(2)) # Should be "Counting down to 0: 2,1,0"
print(countdown(0)) # Should be "Cannot count down to 0"

```

Question 6

Fill in the blanks to complete the “all_numbers” function. This function should return a space-separated string of all numbers, from the starting   “minimum” variable  up to and including the “maximum” variable that's passed into the function. Complete the for loop so that a function call like “all_numbers(3,6)” will return the numbers “3 4 5 6”.
``` python

def all_numbers(minimum, maximum):

    return_string = "" # Initializes variable as a string

    # Complete the for loop with a range that includes all 
    # numbers up to and including the "maximum" value.
    for x in range(minimum,maximum+1) :
        return_string+=str(x)+" " 

        # Complete the body of the loop by appending the number
        # followed by a space to the "return_string" variable.
        ___ 

    # This .strip command will remove the final " " space 
    # at the end of the "return_string".
    return return_string.strip()


print(all_numbers(2,6))  # Should be 2 3 4 5 6
print(all_numbers(3,10)) # Should be 3 4 5 6 7 8 9 10
print(all_numbers(-1,1)) # Should be -1 0 1
print(all_numbers(0,5))  # Should be 0 1 2 3 4 5
print(all_numbers(0,0))  # Should be 0
```

Question 7

The following code is supposed to add together all numbers from x to 10.  The code is returning an incorrect answer, what is the reason for this?
``` python
x = 1
sum = 5
while x <= 10:
    sum += x
    x += 1
print(sum)
# Should print 55
```

Question 8

What is the first number that will be printed in the first iteration of this loop? Your answer should be only one number.  
``` python
for count in range(1, 6):
    print(count+1)
```
Question 9

What number is printed at the end of this code?
``` python
num1 = 0
num2 = 0

for x in range(5):
    num1 = x
    for y in range(14):
        num2 = y + 3

print(num1 + num2)
```


