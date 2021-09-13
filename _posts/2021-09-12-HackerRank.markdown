---
layout: post
title:  "HackerRank: 30 Days of Code"
date:   2021-09-08
categories: 
---

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Read input from STDIN and save to variable
- print "Hello, World." to STDOUT
- print variable to STDOUT 
"""
#!/bin/python3

# Read a full line of input from stdin and save it to our dynamically typed variable, input_string. 
input_string = input()
# Print a string literal saying "Hello, World." to stdout. 
print('Hello, World.')
# TODO: Write a line of code here that prints the contents of input_string to stdout. 
print(input_string)
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### DAY 0: Hello, World :earth_africa:
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Given the variables 'i', 'd', and 's'
- Initialize 3 separate variables from STDIN: one of type int, one of type double, and one of type string
- Print the sum of 'i' plus your int variable on a new line.
- Print the sum of 'd' plus your double variable to a scale of one decimal place on a new line.
- Concatenate 's' with the string you read as input and print the result on a new line.
"""
#!/bin/python3

# The variables 'i', 'd', and 's' below are pre-defined by HackerRank and cannot be modified 
i = 4
d = 4.0
s = 'HackerRank '

# Declare second integer, double, and String variables.
# This instruction does not apply to Python 3. 's' is redefined below b\c the space at the end of the 
# variable above causes the challenge to fail
s = 'HackerRank'

# Read and save an integer, double, and String to your variables.
int_eger = input()
dou_ble = input()
str_ing = input()

# Print the sum of both integer variables on a new line.
print(i + int(int_eger))
# Print the sum of the double variables on a new line.
print(round(d + float(dou_ble),1))
# Concatenate and print the String variables on a new line
print(s + " " + str_ing)
# The 's' variable above should be printed first.
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 1: Data Types
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Complete the 'solve' function below
- calculate tip, given tip percentage
- calculate tax, given tax percentage
- sum the meal cost, tip, and tax and round to the nearest integer
- print the total

"""
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the 'solve' function below.
#
# The function accepts following parameters:
#  1. DOUBLE meal_cost
#  2. INTEGER tip_percent
#  3. INTEGER tax_percent

def solve(meal_cost, tip_percent, tax_percent):
    tip = meal_cost/100*tip_percent
    tax = tax_percent/100*meal_cost
    total = round(meal_cost + tip + tax)
    print(total)

if __name__ == '__main__':
    meal_cost = float(input().strip())

    tip_percent = int(input().strip())

    tax_percent = int(input().strip())

    solve(meal_cost, tip_percent, tax_percent)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 2: Operators
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Given an integer 'n' perform the following conditional actions:
- If n is odd, print 'Weird'
- If n is even and in the inclusive range of 2 to 5 print 'Not Weird'
- If n is even and in the inclusive range of 6 to 20 print 'Weird'
- If n is even and greater than 20 print 'Not Weird'
CONSTRAINT:
- 1 <= n <= 100 
"""
#!/bin/python3

import math
import os
import random
import re
import sys

# function that checks to see if a number is even and returns True, False otherwise
def is_even(num):
    if (num % 2) == 0:
        return True
    else:
        return False
    
if __name__ == '__main__':
    N = int(input().strip())
    if 1 <= N <= 100:
        if (is_even(N)==False) or ((is_even(N)==True) and (6<=N<=20)):
            print("Weird")
        if (is_even(N)==True) and ((2<=N<=5) or (N>20)):
            print("Not Weird")
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 3: Intro to Conditional Statements
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Given the statements: 
- - 'class Person:', 'def __init__(self,initialAge):', 'def amIOld(self):', 'def yearPasses(self):'
- -  and everything below and including the statement 't = int(input())'
- use the constructor to check whether the parameter 'initialAge'
- - if initialAge is negative, print "Age is not valid, setting age to 0." and set  the instance
- - variable'age' to 0
- complete the amIOld method 
- - if age < 13 print "You are young."
- - if 13 <= age < 18 print "You are a teenager."
- - otherwise print "You are old."
- complete the yearPasses method by incrementing the age instane variable by 1   
CONSTRAINTS:
- 1 <= t <= 4
- -5 <= age <= 30
"""
#!/bin/python3

class Person:
    def __init__(self,initialAge):
        # Add some more code to run some checks on initialAge
        if initialAge < 0:
            print("Age is not valid, setting age to 0.")
            self.age = 0
        else:
            self.age = initialAge
    def amIOld(self):
        # Do some computations in here and print out the correct statement to the console
        if self.age < 13:
            print("You are young.")
        elif 13 <= self.age < 18:
            print("You are a teenager.")
        else:
            print("You are old.")
    def yearPasses(self):
        # Increment the age of the person in here
        self.age+=1
        
t = int(input())
for i in range(0, t):
    age = int(input())         
    p = Person(age)  
    p.amIOld()
    for j in range(0, 3):
        p.yearPasses()       
    p.amIOld()
    print("")
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 4: Class vs. Instance
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Given the statements "if __name__ == '__main__':" and "n = int(input().strip())"
- print the first 10 multiples of n x i using the format n x i = result
CONSTRAINTS:
- 1 <= i <= 10
- 2 <= n <= 20
"""
#!/bin/python3

import math
import os
import random
import re
import sys

if __name__ == '__main__':
    n = int(input().strip())
    for i in range(1,11):
        print("{} x {} = {}".format(n,i,n*i))
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 5: Loops :arrows_counterclockwise:
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Given a string 's' of length 'N' that is indexed from 0 to 'N - 1' print its even-indexed and
- odd-indexed characters as  space-separated strings on a single line 
EXAMPLE:
s = adbecf
prints out: abc def
CONSTRAINTS:
- 1 <= t <= 10 : (t is number of test cases) 
- 2 < length of s <= 10000
"""
#!/bin/python3

if __name__ == '__main__':
    # number of strings user will provide
    numStrings = int(input())
    count = 0
    strings = []

    # get strings from user and append to strings array 
    while count != numStrings:
        s = str(input())
        strings.append(s)
        count+=1
    
    x = 0
    evens = ""
    odds = ""

    # loop through elements in strings array
    while x < len(strings):
        y = 0
        # loop through characters in element
        while y < len(strings[x]):
            if y%2==0:
                evens+=strings[x][y]
            else:
                odds+=strings[x][y]     
            y+=1
        print("{} {}".format(evens,odds))
        evens = ""
        odds = ""
        x+=1
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 6: Let's Review
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Given an array of N integers, print the integers in reverse order 
- - on a single line with a space between each character
GIVEN SYNTAX:
- - if __name__ == '__main__':
- - n = int(input().strip())
- - arr = list(map(int, input().rstrip().split()))
CONSTRAINTS:
- 1 <= N <= 1000
- 1 <= A[i] <= 1000, where A[i] is the i'th integer of the array
"""
#!/bin/python3

import math
import os
import random
import re
import sys

if __name__ == '__main__':
n = int(input().strip())

arr = list(map(int, input().rstrip().split()))

x = len(arr)-1
s = ""

while x >= 0:
    s+= "{} ".format(arr[x])
    x-=1

print(s)
{% endhighlight %}
{% endcapture %}
{% capture summary %}
### Day 7: Arrays
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
- Given n names and phone numbers, assemble a phone book that maps friends' names
- - to their respective phone numbers.
- Given an unknown number of names to query, print the associated entry from the 
- - phone book on a new line in the form name=phoneNumber
- If an entry for 'name' is not found, print 'Not found'
- Phone book should be a Dictionary/Map/HashMap data structure
"""
# Enter your code here. Read input from STDIN. Print output to STDOUT
#!/bin/python3

if __name__ == '__main__':
    n = int(input())
    
    phoneBook=dict(input().split(' ',2) for _ in range(n))
    
    while True:
        try:
            name = str(input())
            if name in phoneBook.keys():
                print("{}={}".format(name,phoneBook[name]))
            else:
                print("Not found")
        except:
            break
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 8: Dictionaries and Maps
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:

"""
#!/bin/python3

import math
import os
import random
import re
import sys

#
# Complete the 'factorial' function below.
#
# The function is expected to return an INTEGER.
# The function accepts INTEGER n as parameter.
#

def factorial(n):
    if n > 1:
        n = n * factorial(n-1) 
    return n

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input().strip())

    result = factorial(n)

    fptr.write(str(result) + '\n')

    fptr.close()
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 9: Recursion 3
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:

"""
#!/bin/python3

import math
import os
import random
import re
import sys

def binary(decimal,string):
    while decimal != 0:
        string+=str(decimal % 2)
        decimal = decimal//2
        binary(decimal,string)
    return string

def count_ones(binary):
    count = 0
    max_count = 0
    for x in range(0,len(binary)):
        if binary[x] == '1':
            count+=1
            if count > max_count:
                max_count = count
        elif binary[x] == '0':
            count = 0
    return max_count
        
if __name__ == '__main__':
    n = int(input().strip())
    s = ''
    b = binary(n,s)
    number_of_ones = count_ones(b)    
    print(number_of_ones)
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 10: Binary Numbers
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:

"""
#!/bin/python3

import math
import os
import random
import re
import sys

def findMax(array):
    d ={}
    for n in range(1,17):
        d['hourglass{}'.format(n)] = 0
        
    x = 0
    y = 0
    while y < 6:
        while x < 6:
            n = array[y][x]
            if 0 <= x <= 2 and 0 <= y <= 2:
                if y == 1 and x != 1:
                    pass
                else:
                    d['hourglass1'] += n
            if 1 <= x <= 3 and 0 <= y <= 2:
                if y == 1 and x != 2:
                    pass
                else:
                    d['hourglass2'] += n
            if 2 <= x <= 4 and 0 <= y <= 2:
                if y == 1 and x != 3:
                    pass
                else:
                    d['hourglass3'] += n
            if 3 <= x <= 5 and 0 <= y <= 2:
                if y == 1 and x != 4:
                    pass
                else:
                    d['hourglass4'] += n
            if 0 <= x <= 2 and 1 <= y <= 3:
                if y == 2 and x != 1:
                    pass
                else:
                    d['hourglass5'] += n
            if 1 <= x <= 3 and 1 <= y <= 3:
                if y == 2 and x != 2:
                    pass
                else:
                    d['hourglass6'] += n
            if 2 <= x <= 4 and 1 <= y <= 3:
                if y == 2 and x != 3:
                    pass
                else:
                    d['hourglass7'] += n
            if 3 <= x <= 5 and 1 <= y <= 3:
                if y == 2 and x != 4:
                    pass
                else:
                    d['hourglass8'] += n
            if 0 <= x <= 2 and 2 <= y <= 4:
                if y == 3 and x != 1:
                    pass
                else:
                    d['hourglass9'] += n
            if 1 <= x <= 3 and 2 <= y <= 4:
                if y == 3 and x != 2:
                    pass
                else:
                    d['hourglass10'] += n
            if 2 <= x <= 4 and 2 <= y <= 4:
                if y == 3 and x != 3:
                    pass
                else:
                    d['hourglass11'] += n
            if 3 <= x <= 5 and 2 <= y <= 4:
                if y == 3 and x != 4:
                    pass
                else:
                    d['hourglass12'] += n
            if 0 <= x <= 2 and 3 <= y <= 5:
                if y == 4 and x != 1:
                    pass
                else:
                    d['hourglass13'] += n
            if 1 <= x <= 3 and 3 <= y <= 5:
                if y == 4 and x != 2:
                    pass
                else:
                    d['hourglass14'] += n
            if 2 <= x <= 4 and 3 <= y <= 5:
                if y == 4 and x != 3:
                    pass
                else:
                    d['hourglass15'] += n
            if 3 <= x <= 5 and 3 <= y <= 5:
                if y == 4 and x != 4:
                    pass
                else:
                    d['hourglass16'] += n                        
            x+=1
        y+=1
        x=0
        
    allValues = d.values()
    return(max(allValues))
            
if __name__ == '__main__':

    arr = []
 
    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))

    print(findMax(arr))    
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 11: 2D Arrays
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:

"""
class Person:
    def __init__(self, firstName, lastName, idNumber):
        self.firstName = firstName
        self.lastName = lastName
        self.idNumber = idNumber
    def printPerson(self):
        print("Name:", self.lastName + ",", self.firstName)
        print("ID:", self.idNumber)

class Student(Person):
    #   Class Constructor
    #   
    #   Parameters:
    #   firstName - A string denoting the Person's first name.
    #   lastName - A string denoting the Person's last name.
    #   id - An integer denoting the Person's ID number.
    #   scores - An array of integers denoting the Person's test scores.
    #
    # Write your constructor here
    def __init__(self,firstName,lastName,idNumber, scores):
        super().__init__(firstName, lastName, idNumber)
        self.scores = scores
    #   Function Name: calculate
    #   Return: A character denoting the grade.
    #
    # Write your function here
    def calculate(self):
        average = sum(self.scores)/len(self.scores)
        if 90 <= average <=100:
            return('O')
        elif 80 <= average < 90:
            return('E')
        elif 70 <= average < 80:
            return('A')
        elif 55 <= average < 70:
            return('P')
        elif 40 <= average < 55:
            return('D')
        elif average < 40:
            return('T')

line = input().split()
firstName = line[0]
lastName = line[1]
idNum = line[2]
numScores = int(input()) # not needed for Python
scores = list( map(int, input().split()) )
s = Student(firstName, lastName, idNum, scores)
s.printPerson()
print("Grade:", s.calculate())
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 12: Inheritance
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:

"""
from abc import ABCMeta, abstractmethod
class Book(object, metaclass=ABCMeta):
    def __init__(self,title,author):
        self.title=title
        self.author=author   
    @abstractmethod
    def display(): pass

#Write MyBook class
class MyBook(Book):
    def __init__(self,title,author,price):
        super().__init__(title,author)
        self.price = price
        
    def display(self):
        print("Title: {}".format(self.title))
        print("Author: {}".format(self.author))
        print("Price: {}".format(self.price))

title=input()
author=input()
price=int(input())
new_novel=MyBook(title,author,price)
new_novel.display()
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 13: Abstract Classes
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:
 
"""
class Difference:
    def __init__(self, a):
        self.__elements = a

    # Add your code here
    def computeDifference(self):
        smallest = self.__elements[0]
        largest = self.__elements[0]
        for x in range(0,len(self.__elements)):
            if self.__elements[x] < smallest:
                smallest = self.__elements[x]
            if self.__elements[x] > largest:
                largest = self.__elements[x]
        self.maximumDifference = abs(smallest - largest)
# End of Difference class

_ = input()
a = [int(e) for e in input().split(' ')]

d = Difference(a)
d.computeDifference()

print(d.maximumDifference)
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 14: Scope
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:

"""
#!/bin/python3

class Node:
    def __init__(self,data):
        self.data = data
        self.next = None 
class Solution: 
    def display(self,head):
        current = head
        while current:
            print(current.data,end=' ')
            current = current.next

    def insert(self,head,data): 
    #Complete this method
        print(data, end= ' ')

mylist= Solution()
T=int(input())
head=None
for i in range(T):
    data=int(input())
    head=mylist.insert(head,data)    
mylist.display(head);
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 15: Linked List
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:

"""
#!/bin/python3

import math
import os
import random
import re
import sys

S = input().strip()
try:
    print(int(S))
except ValueError:
    print("Bad String")

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 16: Exceptions - String to Integer
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}
"""
CHALLENGE TASK:

"""
#!/bin/python3

#Write your code here

class Calculator:
    def power(self,n,p):
        Error = ValueError('n and p should be non-negative')
        self.n = n
        self.p = p
        if self.n < 0 or self.p < 0:
            raise Error
        else:
            return n**p

myCalculator=Calculator()
T=int(input())
for i in range(T):
    n,p = map(int, input().split())
    try:
        ans=myCalculator.power(n,p)
        print(ans)
    except Exception as e:
        print(e)   
{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### Day 17: More Exceptions
{% endcapture %}{% include details.html %}