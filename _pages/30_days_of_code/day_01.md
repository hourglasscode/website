{% capture content %}
### Day 1: Data Types
- Instructions:
	- Given the variables `i`, `d`, and `s` 
	- Initialize 3 separate variables from STDIN: one of type int, one of type double, and one of type string 
	- Print the sum of `i` plus your int variable on a new line 
	- Print the sum of `d` plus your double variable to a scale of one decimal place on a new line 
	- Concatenate `s` with the string you read as input and print the result on a new line. 

{% capture details %}
{% highlight python linenos=table %}

i = 4
d = 4.0
s = 'HackerRank '
# Declare second integer, double, and String variables.

# Read and save an integer, double, and String to your variables.

# Print the sum of both integer variables on a new line.

# Print the sum of the double variables on a new line.

# Concatenate and print the String variables on a new line
# The 's' variable above should be printed first.

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

#!/bin/python3

i = 4
d = 4.0
s = 'HackerRank '

# Declare second integer, double, and String variables.
# Read and save an integer, double, and String to your variables.
int_eger = input()
dou_ble = input()
str_ing = input()

# Print the sum of both integer variables on a new line.
print(i + int(int_eger))

# Print the sum of the double variables on a new line.
print(round(d + float(dou_ble),1))

# Concatenate and print the String variables on a new line
# The 's' variable above should be printed first.
print(s + str_ing)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}


