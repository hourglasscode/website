{% capture content %}
### Day 8: Dictionaries and Maps 
- Instructions:
    - Given `n` names and phone numbers, assemble a phone book that maps friends' names to their respective phone numbers.
    - Given an unknown number of names to query, print the associated entry from the phone book on a new line in the form `name=phoneNumber`
    - If an entry for `name` is not found, print `Not found`
    - Phone book should be a Dictionary/Map/HashMap data structure
    - Constraints:
        - `1 <= n <= 10^5`
        - `1 <= queries <= 10^5`

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
# Enter your code here. Read input from STDIN. Print output to STDOUT

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
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}
