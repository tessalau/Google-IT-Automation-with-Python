
Question 1

The format of the input variable “address_string” is: numeric house number, followed by the street name which may contain numbers and could be several words long (e.g., "123 Main Street", "1001 1st Ave", or "55 North Center Drive"). 

Complete the string methods needed in this function so that input like "123 Main Street" will produce the output "House number 123 on a street named Main Street". This function should:

accept a string through the parameters of the function;

separate the address string into new strings: house_number and street_name; 

return the variables in the string format: "House number X on a street named Y". 
``` python
def format_address(address_string):
    word=address_string.split()

    house_number = word[0]
    street = address_string.replace(word[0],"")




    return ("House number {} on a street named{}".format(house_number,street))


print(format_address("123 Main Street"))
# Should print: "House number 123 on a street named Main Street"


print(format_address("1001 1st Ave"))
# Should print: "House number 1001 on a street named 1st Ave"


print(format_address("55 North Center Drive"))
# Should print "House number 55 on a street named North Center Drive"

```
Question 2

Complete the for loop and string method needed in this function so that a function call like "alpha_length("This has 1 number in it")" will return the output "17". This function should:

accept a string through the parameters of the function;

iterate over the characters in the string;

determine if each character is a letter (counting only alphabetic characters; numbers, punctuation, and spaces should be ignored);

increment the counter;

return the count of letters in the string.
``` python

def alpha_length(string):
    character = ""
    count_alpha = 0
    # Complete the for loop sequence to iterate over "string".
    for character in string: 
        # Complete the if-statement using a string method. 
        if character.isalpha():
            count_alpha += 1  
    return count_alpha
 
print(alpha_length("This has 1 number in it")) # Should print 17
print(alpha_length("Thisisallletters")) # Should print 16
print(alpha_length("This one has punctuation!")) # Should print 21
```

Question 3

Consider the following scenario about using Python lists: 

A professor gave his two assistants, Aniyah and Imani, the task of keeping an attendance list of students in the order they arrived in the classroom. Aniyah was the first one to note which students arrived, and then Imani took over. After class, they each entered their lists into the computer and emailed them to the professor. The professor wants to combine the two lists into one and sort it in alphabetical order. 

Complete the code by combining the two lists into one and then sorting the new list. This function should:

accept two lists through the function’s parameters;,

combine the two lists;

sort the combined list in alphabetical order;

return the new list. 
``` python
def alphabetize_lists(list1, list2):


  list1.extend(list2) # Initialize a new list.
    
  list1.sort() # Assign the combined lists to the "new_list".
  return list1


Aniyahs_list = ["Jacomo", "Emma", "Uli", "Nia", "Imani"]
Imanis_list = ["Loik", "Gabriel", "Ahmed", "Soraya"]


print(alphabetize_lists(Aniyahs_list, Imanis_list))
# Should print: ['Ahmed', 'Emma', 'Gabriel', 'Imani', 'Jacomo', 'Loik', 'Nia', 'Soraya', 'Uli']
```
Question 4

Fill in the blank to complete the “increments” function. This function should use a list comprehension to create a list of squared numbers (using either the expression n*n or n**2). The function receives two variables and should return the list of squares that occur between the “start” and “end” variables exclusively (meaning don’t modify the default behavior of the range to exclude the “end” value in the range). For example, squares(2, 3) should return [4].
``` python
def squares(start, end):
    new= [x**2 for x in range(start,end)]
    return(new)
        # Create the required list comprehension


print(squares(2, 3)) # Should be [4]
print(squares(1, 5)) # Should be [1, 4, 9, 16]
print(squares(0, 10)) # Should be [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

```
Question 5

Fill in the blanks to complete the “countries” function. This function accepts a dictionary containing a list of continents (keys) and several countries from each continent (values).  For each continent, format a string to print the names of the countries only. The values for each key should appear on their own line.
``` python
def countries(countries_dict):
    result = ""
    # Complete the for loop to iterate through the key and value items 
    # in the dictionary.
    for continent, countries in countries_dict.items():

        # Use a string method to format the required string.
        result += countries+", "
    print(result, end=" ")

print(countries_dict({"Africa": ["Kenya", "Egypt", "Nigeria"], "Asia":["China", "India", "Thailand"], "South America": ["Ecuador", "Bolivia", "Brazil"]}))

# Should print:
# ['Kenya', 'Egypt', 'Nigeria']
# ['China', 'India', 'Thailand']
# ['Ecuador', 'Bolivia', 'Brazil']
```
Question 6

Consider the following scenario about using Python dictionaries and lists: 

Tessa and Rick are hosting a party. Before they send out invitations, they want to add all of the people they are inviting to a dictionary so they can also add how many guests each friend is bringing to the party.  

Complete the function so that it accepts a list of people, then iterates over the list and adds all of the names (elements) to the dictionary as keys with a starting value of 0. Tessa and Rick plan to update these values with the number of guests their friends will bring with them to the party. Then, print the new dictionary.

This function should:

accept a list variable named “guest_list” through the function’s parameter;

add the contents of the list as keys to a new, blank dictionary;

assign each new key with the value 0;

print the new dictionary.
``` python
def setup_guests(guest_list):
    dict={}
    for guest in guests:
        dict[guest]=0

    # loop over the guest list and add each guest to the dictionary with
    # an initial value of 0
    
    return dict

guests = ["Adam","Camila","David","Jamal","Charley","Titus","Raj","Noemi","Sakira","Chidi"]

print(setup_guests(guests))
```
Question 7

Complete the function so that input like "This is a sentence." will return a dictionary that holds the count of each letter that occurs in the string: {'t': 2, 'h': 1, 'i': 2, 's': 3, 'a': 1, 'e': 3, 'n': 2, 'c': 1}. This function should:

accept a string “text” variable through the function’s parameters;

iterate over each character the input string to count the frequency of each letter found, (only letters should be counted, do not count blank spaces, numbers, or punctuation; keep in mind that Python is case sensitive);

populate the new dictionary with the letters as keys, ensuring each key is unique, and assign the value for each key with the count of that letter;

return the new dictionary.
``` python
def count_letters(text):
  # Initialize a new dictionary.
  dictionary = {}
 
  # Complete the for loop to iterate through each "text" character and 
  # use a string method to ensure all letters are lowercase.
  for letter in text.lower():
    if letter.isalpha():
      if letter not in dictionary:
        
        dictionary[letter]=1
      else: 
        dictionary[letter]+=1  
   
  return dictionary

print(count_letters("AaBbCc"))
# Should be {'a': 2, 'b': 2, 'c': 2}

print(count_letters("Math is fun! 2+2=4"))
# Should be {'m': 1, 'a': 1, 't': 1, 'h': 1, 'i': 1, 's': 1, 'f': 1, 'u': 1, 'n': 1}

print(count_letters("This is a sentence."))
# Should be {'t': 2, 'h': 1, 'i': 2, 's': 3, 'a': 1, 'e': 3, 'n': 2, 'c': 1}





