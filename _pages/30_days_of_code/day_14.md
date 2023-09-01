{% capture content %}
### Day 14: Scope  
- Instructions:
    - Complete the difference class by writig the following:
        - A classconstructor that takes an array of integers as a parameter and saves it to the `__elements` instance variable
        - A computeDifference method that finds the maximum absolute difference between any 2 numbers in `__elements` and stores it in the `maximumDifference` instance variable
        - The difference class has a private integer array `elements` for storing `N` non-negative integers, and a public integer `maximumDifference` for storing the maximum absolute difference
            - The maximum absolute difference between two integers in a set of positive integers, elements, is the largest absolute difference `|a - b|` between any two integers, a and b, in `__elements`.
    - Constraints:
        - `1 <= N <= 10`
        - `1 <= __elements[i] <= 100 where 0 <= i <= N-1`


{% capture details %}
{% highlight python linenos=table %}

class Difference:
    def __init__(self, a):
        self._elements = a

    # Add your code here

# End of Difference class

_ = input()
a = [int(e) for e in input().split(' ')]

d = Difference(a)
d.computeDifference()

print(d.maximumDifference)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

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
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}