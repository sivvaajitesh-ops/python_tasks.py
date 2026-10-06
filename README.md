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