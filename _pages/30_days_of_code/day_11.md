{% capture content %}
### Day 11: 2D Arrays
- Instructions:
    - Given a 6 x 6 2D Array, A: 
        - `1 1 1 0 0 0` 
        - `0 1 0 0 0 0` 
        - `1 1 1 0 0 0` 
        - `0 0 2 4 4 0` 
        - `0 0 0 2 0 0` 
        - `0 0 1 2 4 0` 
    - Calculate the hourglass sum for every hourglass in A 
    - Then print the maximum hourglass sum 
    - An hourglass is defined as a subset of values with indices falling in the following graphical representation: 
        - `1 1 1` 
        - &nbsp;&nbsp;&nbsp;`1`   
        - `1 1 1` 
    - There are 16 hourglasses in A and an hourglass sum is the sum of an hourglass' values 
    - In the array above, the maximum hourglass sum is 19 for the hourglass 
        - `2 4 4` 
        - &nbsp;&nbsp;&nbsp;`2` 
        - `1 2 4` 
    - Constraints: 
        - `9 <= A[i][j] <= 9`
        - `0 <= i,j <= 5`

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

import math
import os
import random
import re
import sys

if __name__ == '__main__':

    arr = []

    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))

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

def findMax(array):
    d ={}
    for n in range(1,17):
        d['hourglass{}'.format(n)] = 0
        
    x = 0
    y = 0
    while y < 6:
        while x < 6:
            n = array[y][x]
            if 0 <= x <= 2 and 0 <= y <= 2:
                if y == 1 and x != 1:
                    pass
                else:
                    d['hourglass1'] += n
            if 1 <= x <= 3 and 0 <= y <= 2:
                if y == 1 and x != 2:
                    pass
                else:
                    d['hourglass2'] += n
            if 2 <= x <= 4 and 0 <= y <= 2:
                if y == 1 and x != 3:
                    pass
                else:
                    d['hourglass3'] += n
            if 3 <= x <= 5 and 0 <= y <= 2:
                if y == 1 and x != 4:
                    pass
                else:
                    d['hourglass4'] += n
            if 0 <= x <= 2 and 1 <= y <= 3:
                if y == 2 and x != 1:
                    pass
                else:
                    d['hourglass5'] += n
            if 1 <= x <= 3 and 1 <= y <= 3:
                if y == 2 and x != 2:
                    pass
                else:
                    d['hourglass6'] += n
            if 2 <= x <= 4 and 1 <= y <= 3:
                if y == 2 and x != 3:
                    pass
                else:
                    d['hourglass7'] += n
            if 3 <= x <= 5 and 1 <= y <= 3:
                if y == 2 and x != 4:
                    pass
                else:
                    d['hourglass8'] += n
            if 0 <= x <= 2 and 2 <= y <= 4:
                if y == 3 and x != 1:
                    pass
                else:
                    d['hourglass9'] += n
            if 1 <= x <= 3 and 2 <= y <= 4:
                if y == 3 and x != 2:
                    pass
                else:
                    d['hourglass10'] += n
            if 2 <= x <= 4 and 2 <= y <= 4:
                if y == 3 and x != 3:
                    pass
                else:
                    d['hourglass11'] += n
            if 3 <= x <= 5 and 2 <= y <= 4:
                if y == 3 and x != 4:
                    pass
                else:
                    d['hourglass12'] += n
            if 0 <= x <= 2 and 3 <= y <= 5:
                if y == 4 and x != 1:
                    pass
                else:
                    d['hourglass13'] += n
            if 1 <= x <= 3 and 3 <= y <= 5:
                if y == 4 and x != 2:
                    pass
                else:
                    d['hourglass14'] += n
            if 2 <= x <= 4 and 3 <= y <= 5:
                if y == 4 and x != 3:
                    pass
                else:
                    d['hourglass15'] += n
            if 3 <= x <= 5 and 3 <= y <= 5:
                if y == 4 and x != 4:
                    pass
                else:
                    d['hourglass16'] += n                        
            x+=1
        y+=1
        x=0
        
    allValues = d.values()
    return(max(allValues))
            
if __name__ == '__main__':

    arr = []
 
    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))

    print(findMax(arr))  

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}
