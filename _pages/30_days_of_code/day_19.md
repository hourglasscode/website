{% capture content %}
### Day 19: Interfaces 
- Instructions:
    - Complete the implementation of `Calculator` class, which implements the `AdvancedArithmetic` interface. 
    - The implementation for the `divisorSum(n)` method must return the sum of all divisors of `n` 
    - Example: 
        - `n = 20`, The divisors of 20 are 1,2,4,5,10,20 
    - Constraint: 
        - `1 <= n <= 1000`

{% capture details %}
{% highlight python linenos=table %}

class AdvancedArithmetic(object):
    def divisorSum(n):
        raise NotImplementedError

class Calculator(AdvancedArithmetic):
    def divisorSum(self, n):
        pass


n = int(input())
my_calculator = Calculator()
s = my_calculator.divisorSum(n)
print("I implemented: " + type(my_calculator).__bases__[0].__name__)
print(s)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

class AdvancedArithmetic(object):
    def divisorSum(n):
        raise NotImplementedError

class Calculator(AdvancedArithmetic):
    def divisorSum(self, n):
        if n == 0 or n==1:
            return n
        else:
            list_of_divisors = []
            list_of_divisors.extend([1,n])
            max_divisor = n//2
            for i in range(2,max_divisor+1):
                if n%i == 0:
                    list_of_divisors.append(i)
        return sum(list_of_divisors)


n = int(input())
my_calculator = Calculator()
s = my_calculator.divisorSum(n)
print("I implemented: " + type(my_calculator).__bases__[0].__name__)
print(s)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}