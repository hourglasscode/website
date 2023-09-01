{% capture content %}
### Day 4: Class vs. Instance 
- Instructions:
    - Use the constructor to verify the parameter `initialAge`
        - If `initialAge` is negative, print `Age is not valid, setting age to 0.` and set  the instance variable `age` to 0 
    - Complete the `amIOld` method 
        - if `age < 13` print `You are young.` 
        - if `13 <= age < 18` print `You are a teenager.` 
        - otherwise print `You are old.` 
    - Complete the `yearPasses` method by incrementing the age instance variable by 1   
    - Contraints: 
        - `1 <= t <= 4`
        - `5 <= age <= 30` 

{% capture details %}
{% highlight python linenos=table %}

class Person:
    def __init__(self,initialAge):
        # Add some more code to run some checks on initialAge

    def amIOld(self):
        # Do some computations in here and print out the correct statement to the console

    def yearPasses(self):
        # Increment the age of the person in here

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
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

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
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}

