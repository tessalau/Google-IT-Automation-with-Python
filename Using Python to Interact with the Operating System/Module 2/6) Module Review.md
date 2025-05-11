1. You are reading an article that includes some government websites in the form:

 https://www.website-domain.gov 

You’d like to make a list of these websites by extracting them from the text automatically, instead of copying and pasting them by hand. Complete the function find_gov_urls() to accomplish this task for all websites that end with .gov.

```python
def find_gov_urls(website):
 pattern = r"https://[\w.-]+\.gov" #enter the regex pattern here
 result = re.findall(pattern, website) #enter the re method here
 return result


print(find_gov_urls("https://www.data.gov is a great place to find open source datasets!")) # Should return ['https://www.data.gov']
print(find_gov_urls("Learn more about US National Parks at https://www.nps.gov, https://www.nationalparks.org, or https://www.recreation.gov.")) # Should return ['https://www.nps.gov', 'https://www.recreation.gov']
print(find_gov_urls("The Library of Congress (https://www.loc.gov) is an incredible resource!")) # Should return ['https://www.loc.gov']
print(find_gov_urls("The Library of Congress (www.loc.gov) is an incredible resource!")) # Should return []
```
2. You are exploring the punctuation at the end of sentences and want to split sentences so that each word is separate and any punctuation is included in the word next to it. Complete the parse_sentences() function to accomplish this task.

 ```python
def parse_sentences(sentence):
    pattern = r"(\s)"
    result = re.split(pattern, sentence)
    return [word for word in result if word.strip()]  # Remove empty str

print(parse_sentences("Hello! How are you doing?")) # should return ['Hello!', 'How', 'are', 'you', 'doing?']
print(parse_sentences("what a beautiful day it is")) # should return ['what', 'a', 'beautiful', 'day', 'it', 'is']
print(parse_sentences("2 + 2 is definitely 4!")) # should return ['2', '+', '2', 'is', 'definitely', '4!']
```
3. A company uses Product ID numbers to identify each product line it makes. Each product ID starts with 4 digits, followed by a hyphen (-), followed by two capital letters, followed by a hyphen (-), followed by two more digits, in the format: 

1234-AB-12 

The manufacturing team records information about the production of each product line daily. You want to extract the product ID numbers of one of these product lines, which begins with a 1. The other characters in the product ID can be any digit or variable, as long as they follow the product ID format described above. Complete the following code so the find_productID() function returns all product ID numbers that match the product of interest. 

```python

def find_productID(report):
    pattern = r"\b1\d{3}-[A-Z]{2}-\d{2}\b"
    result = re.findall(pattern, report)
    return result

# Test Cases
print(find_productID("Products 1234-AB-30 and 2234-AB-30, not items 12-AB-30 or 12345-AB-30"))  
# Should return ['1234-AB-30']
print(find_productID("Products of interest are 1234-AB-30, 1678-XZ-11, and 1561-CD-57. We're not interested in other products like 2345-AB-29."))  
# Should return ['1234-AB-30', '1678-XZ-11', '1561-CD-57']
```

