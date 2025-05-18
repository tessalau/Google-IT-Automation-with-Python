1. The find_item function uses binary search to recursively locate an item in the list, returning True if found, False otherwise. Something is missing from this function. Can you spot what it is and fix it? Add debug lines where appropriate, to help narrow down the problem.
```python
def find_item(list, item):
    #Returns True if the item is in the list, False if not.
  try:
    pos = list.index(item)
    if len(list) == 0:
      return False

    #Is the item in the center of the list?
    middle = len(list)//2
    if list[middle] == item:
      return True
  
    #Is the item in the first half of the list? 
    if pos < middle:
      #Call the function with the first half of the list
      return find_item(list[:middle], item)
    else:
      #Call the function with the second half of the list
      return find_item(list[middle+1:], item)
  except Exception as e:
    print(f"Error msg is {e}")
    return False

list_of_names = ["Parker", "Drew", "Cameron", "Logan", "Alex", "Chris", "Terry", "Jamie", "Jordan", "Taylor"]

print(find_item(list_of_names, "Alex")) # True
print(find_item(list_of_names, "Andrew")) # False
print(find_item(list_of_names, "Drew")) # True
print(find_item(list_of_names, "Jared")) # False
```
2. The binary_search function returns the position of key in the list if found, or -1 if not found. You want to make sure that it's working correctly, so you need to place debugging lines to let you know each time that the list is cut in half, whether you're on the left or the right. You do not want to print anything when the key is located.

For example, the command binary_search([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 3) performs these steps:
1) It determines that the key, 3, is in the left half of the list and prints "Checking the left side". 
2) It then determines that 3 is in the right half of the new list and prints "Checking the right side".
3) Finally, it returns the value of 2, which is the position of the key in the list.

Add commands to the code to print out "Checking the left side" or "Checking the right side" in the appropriate places.  
```python
def binary_search(list, key):
	list.sort() # Binary search starts with a sorted list
	left = 0 # The first value of the list
	right = len(list) - 1 # The last value of the list


	while left <= right:
		middle = (left + right) // 2


		if list[middle] == key:
			return middle
		elif list[middle] > key:
			print("Checking the left side")
			right = middle - 1
		else:
			print("Checking the right side")
			left = middle + 1
	return -1

print(binary_search([10, 2, 9, 6, 7, 1, 5, 3, 4, 8], 1))
print(binary_search([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 5))
print(binary_search([10, 9, 8, 7, 6, 5, 4, 3, 2, 1], 7))
print(binary_search([1, 3, 5, 7, 9, 10, 2, 4, 6, 8], 10))
print(binary_search([5, 1, 8, 2, 4, 10, 7, 6, 3, 9], 11))
```
3. The best_search function compares linear_search and binary_search functions, to locate a key in the list, and returns how many steps each method took, and which one is the best for that situation. The list does not need to be sorted, as the binary_search function sorts it before proceeding (and uses one step to do so). Here, linear_search and binary_search functions both return the number of steps that it took to either locate the key, or determine that it's not in the list. If the number of steps is the same for both methods (including the extra step for sorting in binary_search), then the result is a tie. Fill in the blanks to make this work.
 ``` python
   def linear_search(lst, key):
    # Returns the number of steps to determine if key is in the list 
    steps = 0
    for i, item in enumerate(lst):
        steps += 1
        if item == key:
            break
    return steps  # Return the number of steps taken

def binary_search(lst, key):
    # Returns the number of steps to determine if key is in the list 

    lst.sort()  # Sorting the list, which counts as one step
    steps = 1  # Initialize the counter with 1 for sorting

    left = 0
    right = len(lst) - 1
    while left <= right:
        steps += 1
        middle = (left + right) // 2
        
        if lst[middle] == key:
            break
        if lst[middle] > key:
            right = middle - 1
        else:
            left = middle + 1

    return steps  # Return the number of steps taken

def best_search(lst, key):
    steps_linear = linear_search(lst, key)
    steps_binary = binary_search(lst, key)

    results = "Linear: " + str(steps_linear) + " steps, "
    results += "Binary: " + str(steps_binary) + " steps. "

    if steps_linear < steps_binary:
        results += "Best Search is Linear."
    elif steps_binary < steps_linear:
        results += "Best Search is Binary."
    else:
        results += "Result is a Tie."

    return results

# Test cases
print(best_search([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 1))  
# Expected: Linear: 1 steps, Binary: 4 steps. Best Search is Linear.

print(best_search([10, 2, 9, 1, 7, 5, 3, 4, 6, 8], 1))  
# Expected: Linear: 4 steps, Binary: 4 steps. Result is a Tie.

print(best_search([10, 9, 8, 7, 6, 5, 4, 3, 2, 1], 7))  
# Expected: Linear: 4 steps, Binary: 5 steps. Best Search is Linear.

print(best_search([1, 3, 5, 7, 9, 10, 2, 4, 6, 8], 10))  
# Expected: Linear: 6 steps, Binary: 5 steps. Best Search is Binary.

print(best_search([5, 1, 8, 2, 4, 10, 7, 6, 3, 9], 11))  
# Expected: Linear: 10 steps, Binary: 5 steps. Best Search is Binary.
```
