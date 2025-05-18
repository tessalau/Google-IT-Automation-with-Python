
1. The compare_strings function is supposed to compare just the alphanumeric content of two strings, ignoring upper vs lower case and punctuation. But something is not working. Fill in the code to try to find the problems, then fix the problems. Your goal is to search for the character “-” but - is typically reserved for ranges. Find a work-around that enables you to compare the two strings.
```python
import re
def compare_strings(string1, string2):
 try:
    #Convert both strings to lowercase
   #and remove leading and trailing blanks
   string1 = string1.lower().strip()
   string2 = string2.lower().strip()


 #Ignore punctuation
   punctuation = r"[.?!,;:\-']" # re.error: bad character range :-' at position 6




   string1 = re.sub(punctuation, r"", string1)
   string2 = re.sub(punctuation, r"", string2)
  


   return string1 == string2

 #DEBUG CODE GOES HERE

 except re.error as e:
      print(f"Regex Error: {e}")  # Catches regex-related errors
      return False

 except Exception as e:
      print("Failure to send email: {}".format(e), file=sys.stderr)
   


print(compare_strings("Have a Great Day!", "Have a great day?")) # True
print(compare_strings("It's raining again.", "its raining, again")) # True
print(compare_strings("Learn to count: 1, 2, 3.", "Learn to count: one, two, three.")) # False
print(compare_strings("They found some body.", "They found somebody.")) # False
```


2. The datetime module supplies classes for manipulating dates and times, and contains many types, objects, and methods. You've seen some of them used in the dow function, which returns the day of the week for a specific date. We'll use them again in the next_date function, which takes the date_string parameter in the format of "year-month-day", and uses the add_year function to calculate the next year that this date will occur (it's 4 years later for the 29th of February during Leap Year, and 1 year later for all other dates). Then it returns the value in the same format as it receives the date: "year-month-day".

Can you find the error in the code? Is it in the next_date function or the add_year function? How can you determine if the add_year function returns what it's supposed to? Add debug lines as necessary to find the problems, then fix the code to work as indicated above.  
```python
import datetime
from datetime import date

def add_year(date_obj):
    try:
        new_date_obj = date_obj.replace(year=date_obj.year + 1)
    except ValueError:
        # Leap Year Calculation (if February 29 is invalid)
        new_date_obj = date_obj.replace(year=date_obj.year + 4)

    print(f"Debug: New date after adding year(s) - {new_date_obj}")  # Debugging
    return new_date_obj

def next_date(date_string):
    # Convert string to date object (fixing `datetime` issue)
    date_obj = datetime.datetime.strptime(date_string, "%Y-%m-%d").date()
    print(f"Debug: Parsed date object - {date_obj}")  # Debugging

    next_date_obj = add_year(date_obj)
    
    # Fix incorrect format in strftime
    next_date_string = next_date_obj.strftime("%Y-%m-%d")
    return next_date_string

# Test cases
today = date.today()
print(next_date(str(today)))  # Should return a year from today, unless today is Leap Day
print(next_date("2021-01-01"))  # Should return 2022-01-01
print(next_date("2020-02-29"))  # Should return 2024-02-29
```
