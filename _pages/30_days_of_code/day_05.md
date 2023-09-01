{% capture content %}
### Day 5: Loops
- Instructions:
    - print the first 10 multiples of n x i using the format n x i = result
    - Constraints: 
        - `1 <= i <= 10` 
        - `2 <= n <= 20`

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

if __name__ == '__main__':
    n = int(input().strip())
    for i in range(1,11):
        print("{} x {} = {}".format(n,i,n * i))

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}

