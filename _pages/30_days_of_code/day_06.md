{% capture content %}
### Day 6: Let's Review
- Instructions:
    - Given a string `s` of length `N` that is indexed from `0` to `N - 1`, print it's even-indexed and odd-indexed characters as  space-separated strings on a single line
    - Example: `s = adbecf` prints out: `abc def`
    - Constraints
        - `1 <= t <= 10 : (t is number of test cases)` 
        - `2 < length of s <= 10000`

{% capture details %}
{% highlight python linenos=table %}

# Enter your code here. Read input from STDIN. Print output to STDOUT

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

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
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}

