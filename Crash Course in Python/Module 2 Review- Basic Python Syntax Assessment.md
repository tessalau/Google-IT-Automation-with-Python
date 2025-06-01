
Question 1

Complete the code to output the statement, “Diego’s favorite food is lasagna”. Remember that precise syntax must be used to receive credit.
``` python
name = 'Diego'
fav_food = 'lasagna'
print(name + "’s favorite food is " + fav_food) 
```
Question 4

Consider the following scenario about using if-elif-else statements:

The fall weather is unpredictable.  If the temperature is 32 degrees Fahrenheit or below, a heavy coat should be worn.  If it is above 32 degrees but not above 50 degrees, then a jacket should be sufficient.  If it is above 50 but not above 65 degrees, a sweatshirt is appropriate, and above 65 degrees a t-shirt can be worn.  

Fill in the blanks in the function below so it returns the proper clothing type for the temperature.
``` python
def clothing_type(temp):
    if temp>65:
        clothing = "T-Shirt"
    elif temp>50 and temp<=65:
        clothing = "Sweatshirt"
    elif temp>32 and temp<=50:
        clothing = "Jacket"
    else:
        clothing = "Heavy Coat"
    return clothing


print(clothing_type(72)) # Should print T-Shirt
print(clothing_type(55)) # Should print Sweatshirt
print(clothing_type(65)) # Should print Sweatshirt
print(clothing_type(50)) # Should print Jacket
print(clothing_type(45)) # Should print Jacket
print(clothing_type(32)) # Should print Heavy Coat
print(clothing_type(0)) # Should print Heavy Coat
```

Question 6

Fill in the blanks to complete the function. The “identify_IP” function receives an “IP_address” as a string through the function’s parameters, then it should print a description of the IP address. Currently, the function should only support three IP addresses and return "unknown" for all other IPs.
``` python
def identify_IP(IP_address):
    if IP_address == "192.168.1.1":
        IP_description = "Network router"
    elif IP_address == "8.8.8.8" or IP_address == "8.8.4.4":
        IP_description = "Google DNS server"
    elif IP_address == "142.250.191.46":
        IP_description = "Google.com"
    else:
        IP_description = "unknown"
    return IP_description


print(identify_IP("8.8.4.4")) # Should print 'Google DNS server'
print(identify_IP("142.250.191.46")) # Should print 'Google.com'
print(identify_IP("192.168.1.1")) # Should print 'Network router'
print(identify_IP("8.8.8.8")) # Should print 'Google DNS server'
print(identify_IP("10.10.10.10")) # Should print 'unknown'
print(identify_IP("")) # Should Should print 'unknown'
```

Question 9

Fill in the blanks to complete the function. The “return_nonnegative” function takes in two numbers and determines which number is larger.  Then, it subtracts the smaller number from the larger and returns the result. The result will always be greater than or equal to 0. Complete the body of the function so that it returns the correct result.
``` python
def return_nonnegative(first_num, second_num):
    if first_num > second_num:
        result = first_num - second_num
    else:
        result = second_num - first_num
    return result


print(return_nonnegative(5, 5)) # Should print 0
print(return_nonnegative(4, 5)) # Should print 1
print(return_nonnegative(5, 3)) # Should print 2
print(return_nonnegative(2, 5)) # Should print 3
print(return_nonnegative(5, 0)) # Should print 5
print(return_nonnegative(0, 5)) # Should print 5
