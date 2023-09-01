{% capture content %}
### Day 3: Intro to Conditional Statements
- Instructions:
    - Given an integer `n` perform the following conditional actions:
        - If n is odd, print `Weird` 
        - If n is even and in the inclusive range of 2 to 5 print `Not Weird`
        - If n is even and in the inclusive range of 6 to 20 print `Weird`
        - If n is even and greater than 20 print 'Not Weird'
    - Constraint: 
        - `1 <= n <= 100`

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

import math
import os
import random
import re
import sys

if __name__ == '__main__':
    N = int(input().strip())

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

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
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}
