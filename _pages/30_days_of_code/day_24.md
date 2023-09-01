{% capture content %}
### Day 24: More Linked Lists 
- Instructions:
    - A Node object has an integer data field, `data`, and a Node instance pointer, `next`, pointing to another node (i.e.: the next node in a list). 
    - A `removeDuplicates` function is declared in your editor, which takes a pointer to the  node of a linked list as a parameter. 
    - Complete `removeDuplicates` so that it deletes any duplicate nodes from the list and returns the head of the updated list. 
    - The first line of input contains an integer, `N`, the number of nodes to be inserted. 
    - The `N` subsequent lines each contain an integer describing the `data` value of a node being inserted at the list's tail. 
    - Contraint: 
        - The data elements of the linked list argument will always be in non-decreasing order. 

{% capture details %}
{% highlight python linenos=table %}

class Node:
    def __init__(self,data):
        self.data = data
        self.next = None 
class Solution: 
    def insert(self,head,data):
            p = Node(data)           
            if head==None:
                head=p
            elif head.next==None:
                head.next=p
            else:
                start=head
                while(start.next!=None):
                    start=start.next
                start.next=p
            return head  
    def display(self,head):
        current = head
        while current:
            print(current.data,end=' ')
            current = current.next

    def removeDuplicates(self,head):
        #Write your code here

mylist= Solution()
T=int(input())
head=None
for i in range(T):
    data=int(input())
    head=mylist.insert(head,data)    
head=mylist.removeDuplicates(head)
mylist.display(head); 

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

class Node:
    def __init__(self,data):
        self.data = data
        self.next = None 
class Solution: 
    def insert(self,head,data):
            p = Node(data)           
            if head==None:
                head=p
            elif head.next==None:
                head.next=p
            else:
                start=head
                while(start.next!=None):
                    start=start.next
                start.next=p
            return head  
    def display(self,head):
        current = head
        while current:
            print(current.data,end=' ')
            current = current.next

    def removeDuplicates(self,head):
        current = head
        while current:
            if current.next != None:
                if current.next.data != current.data:
                    current = current.next
                else:
                    next_node = current.next.next
                    current.next = None
                    current.next = next_node
            else:
                return head
            
mylist= Solution()
T=int(input())
head=None
for i in range(T):
    data=int(input())
    head=mylist.insert(head,data)    
head=mylist.removeDuplicates(head)
mylist.display(head); 

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}