# python_tasks.py



Python Programs
A set of four basic Python programs implemented and tested using Jupyter Notebook.
Task 1 — Find XOR Pairs
This program accepts a list of numbers and a target value. It checks each pair and displays the pairs whose XOR result matches the given target.
1, 2, 3, 4, 5, 6])
CODE:
def xor(l):
    target = int(input("Enter the target: "))
    
    for i in l:
        for j in l:
            if i ^ j == target:
                print(i, j)

xor([1, 2, 3, 4, 5, 6])
OUTPUT:
Enter the target: 3
1 2
2 1
2 3
3 2
5 6
6 5

Task 2 — Find Second Highest and Second Lowest
This program identifies the second highest and second lowest values from a list without arranging the elements in sorted order.
CODE:
def find(l):
    largest = l[0]
    smallest = l[0]

    for i in l:
        if i > largest:
            largest = i
        if i < smallest:
            smallest = i

    second_largest = l[0]
    second_smallest = l[0]

    for i in l:
        if i != largest and i > second_largest:
            second_largest = i
        if i != smallest and i < second_smallest:
            second_smallest = i

    print("Second largest:", second_largest)
    print("Second smallest:", second_smallest)

find([10, 5, 8, 20, 3])
OUTPUT:
Second largest: 10
Second smallest: 5
Task 3 — Reverse Alphabets Only
This program reverses the alphabetic characters in a string while leaving special characters in their original locations.
CODE:
def reverse(text):
    letters = []

    for ch in text:
        if ch.isalpha():
            letters.append(ch)

    letters.reverse()

    result = ""

    for ch in text:
        if ch.isalpha():
            result += letters.pop(0)
        else:
            result += ch

    return result

print(reverse("a$b%c"))
OUTPUT:
c$b%a
Task 4 — Check for Anagrams
This program compares two strings and determines whether they contain the same characters in a different order. It returns True for anagrams and False otherwise.
def anagram(str1, str2):
    return sorted(str1.lower()) == sorted(str2.lower())

print(anagram("hello", "HELLO"))
Output:
True

EXPLANATION:

1. 
     How it works:
The code takes a target integer as input from the user.
It uses nested for loops to iterate over every possible pair (i, j) in the list l.
The ^ operator calculates the bitwise XOR between i and j. If i ^ j equals target, the pair (i, j) is printed.

2.
     How it works:
First Pass: The function iterates through the list to find the absolute maximum (largest) and minimum (smallest) elements.
Second Pass: It iterates through the list again:
To find second_largest, it checks for elements that are not equal to largest but greater than second_largest.
To find second_smallest, it checks for elements that are not equal to smallest but smaller than second_smallest.
Finally, it prints both values.

3.
   How it works:
Extraction: It scans the input string text and appends all alphabetic characters (ch.isalpha()) to the letters list.
Reversal: It reverses the letters list using .reverse().
Reconstruction: It iterates through the original text again:
If the character is a letter, it pops the next reversed letter from letters (letters.pop(0)).
If it is a special character, it keeps the character as-is in its original index.
Returning "c$b%a" from "a$b%c" demonstrates that a, b, and c were reversed to c, b, and a, while $ and % stayed in place.

4.
       How it works:
Both input strings (str1 and str2) are converted to lowercase using .lower() to make the check case-insensitive.
sorted() converts each string into a sorted list of individual characters.
If both sorted lists are identical (==), the strings contain the exact same characters in different permutations, returning True.
In the example anagram("hello", "HELLO"), both strings normalize to "hello", which sort identically to ['e', 'h', 'l', 'l', 'o'], returning True.
   