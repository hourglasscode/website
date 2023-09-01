{% capture content %}
### Day 20: Sorting 
- Instructions:
    - Given an array `a` of size `n` distinct elements,  sort the array in ascending order using the Bubble Sort algorithm 
    - Once sorted, print the following  lines: 
        - Array is sorted in numSwaps swaps, where `numSwaps` is the number of swaps that took place. 
        - First Element: firstElement, where `firstElement` is the first element in the sorted array. 
        - Last Element: lastElement, where `lastElement` is the last element in the sorted array. 
    - The first line of input contains an integer, `n`, the number of elements in array `a` 
    - The second line of input contains n space-separated integers that describe `a[0],a[1],...,a[n-1]` 
    - Constraints: 
        - `2 <= n <= 600` 
        - `1 <= a[i] <= 2 x 10^6`, where 0 <= i < n 

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

    a = list(map(int, input().rstrip().split()))

    # Write your code here

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

    a = list(map(int, input().rstrip().split()))

    # Write your code here
    iteration_count = 0
    for i in range(n):
        for idx in range(n - i - 1):
            if a[idx] > a[idx+1]:
                a[idx], a[idx+1] = a[idx+1], a[idx]
                iteration_count += 1
                
    print("Array is sorted in {0} swaps.".format(iteration_count))
    print("First Element:",a[0])
    print("Last Element:",a[-1])

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}
