{% capture content %}
### Day 0: Hello World
- Instructions:
	- Write a line of code here that prints the contents of `input_string` to stdout.

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

# Read a full line of input from stdin and save it to our dynamically typed variable, input_string.
input_string = input()

# Print a string literal saying "Hello, World." to stdout.
print('Hello, World.')

# TODO: Write a line of code here that prints the contents of input_string to stdout.

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

# Read a full line of input from stdin and save it to our dynamically typed variable, input_string. 
input_string = input()

# Print a string literal saying "Hello, World." to stdout. 
print('Hello, World.')

# TODO: Write a line of code here that prints the contents of input_string to stdout. 
print(input_string)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}