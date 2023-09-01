{% capture content %}
### Day 9: Recursion 
- Instructions:
    - Complete function method called `factorial` that recursively calculates factorial of given integer `n`
    - Constraint:
        - `2 <= n <= 12`

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the 'factorial' function below.

# The function is expected to return an INTEGER.
# The function accepts INTEGER n as parameter.

def factorial(n):
    # Write your code here

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input().strip())

    result = factorial(n)

    fptr.write(str(result) + '\n')

    fptr.close()

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

# Complete the 'factorial' function below.

# The function is expected to return an INTEGER.
# The function accepts INTEGER n as parameter.


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
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}
