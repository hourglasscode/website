{% capture content %}
### Day 7: Arrays 
- Instructions:
    - Given an array of N integers, print the integers in reverse order on a single line with a space between each character
    - Constraints:
        - `1 <= N <= 1000` 
        - `1 <= A[i] <= 1000, where A[i] is the i'th integer of the array`

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

    arr = list(map(int, input().rstrip().split()))

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
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}
