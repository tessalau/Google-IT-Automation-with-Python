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
3. International Standard Book Numbers (ISBNs) are used to uniquely identify published books. They follow a 13-digit format: 

XXX-X-XX-XXXXXX-X

where each X represents one numeric digit. You have a list of books, information about those books, and their ISBN numbers. You want to extract the 6 digits of the ISBN that come before the last hyphen of each book’s ISBN number. However, you need to be careful to avoid 6-digit strings that are not part of the ISBN numbers you’re interested in. 

Complete the find_isbn() function so you can use it to extract the 6-digit portion of the ISBN numbers of the books on your list. 

```python
def find_isbn(text):
    pattern = r"\b\d{3}-\d-\d{2}-(\d{6})-\d\b"
    result = re.search(pattern, text)
    if result is None:
        return ""
    return result.group(1)  # Returning the correct capturing group



print(find_isbn("123-4-12-098754-0")) # Should return 098754
print(find_isbn("223094-AB-30")) # result should be blank
print(find_isbn("1123-4-12-098754-0")) # result should be blank
```

