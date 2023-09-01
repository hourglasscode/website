{% capture content %}
### Day 16: Exceptions - String to Integer 
- Instructions:
    - Read a string `S` and print it's integer value 
    - if `S` cannot be converted to an integer, print `Bad String` 
    - use String-to-Integer exception handling instead of loops/conditional statements 
    - Constraints:
        - `1 <= |S| <= 6` : `|S|` is length of string S 
        - `S` is composed of either lowercase letters (a-z) or decimal digits (0-9) 

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

import math
import os
import random
import re
import sys

if __name__ == '__main__':
    S = input()

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

S = input().strip()
try:
    print(int(S))
except ValueError:
    print("Bad String")

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}