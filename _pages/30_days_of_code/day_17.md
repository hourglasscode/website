{% capture content %}
### Day 17: More Exceptions 
- Instructions:
    - Write a Calculator class with a single method: `int power(int,int)`
    - The power method takes two integers `n` & `p` as parameters and returns the integer result of `n^p` 
    - If either `n` or `p` is negative, then the method must throw an exception with the message: `n and p should be non-negative`

{% capture details %}
{% highlight python linenos=table %}

#Write your code here

myCalculator=Calculator()
T=int(input())
for i in range(T):
    n,p = map(int, input().split())
    try:
        ans=myCalculator.power(n,p)
        print(ans)
    except Exception as e:
        print(e) 

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

#Write your code here

class Calculator:
    def power(self,n,p):
        Error = ValueError('n and p should be non-negative')
        self.n = n
        self.p = p
        if self.n < 0 or self.p < 0:
            raise Error
        else:
            return n ** p

myCalculator=Calculator()
T=int(input())
for i in range(T):
    n,p = map(int, input().split())
    try:
        ans=myCalculator.power(n,p)
        print(ans)
    except Exception as e:
        print(e) 

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}