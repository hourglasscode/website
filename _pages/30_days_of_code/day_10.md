{% capture content %}
### Day 10: Binary Numbers 
- Instructions:
    - Given a base-10 integer `n` convert it to base-2 (binary)
    - Find and print the base-10 integer denoting the maximum number of consecutive 1s in n's binary representation
    - Constraint:
        - 1 <= n <= 10^6

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

import math
import os
import random
import re
import sys

if __name__ == '__main__':
    n = int(input().strip())

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
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}
