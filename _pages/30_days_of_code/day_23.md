{% capture content %}
### Day 23: BST Level-Order Traversal 
- Instructions:
    - A level-order traversal, also known as a breadth-first search, visits each level of a tree's nodes from left to right, top to bottom. 
    - You are given a pointer, root, pointing to the root of a binary search tree. 
    - Complete the `levelOrder` function provided in your editor so that it prints the level-order traversal of the binary search tree. 
    - The first line of input contains an integer, `T` (the number of test cases). 
    - The `T` subsequent lines each contain an integer, `data`, denoting the value of an element that must be added to the BST. 
    - Constraints: 
        - `1 <= N <= 20` 
        - `1 <= node.data[i] <= 100` 

{% capture details %}
{% highlight python linenos=table %}

import sys

class Node:
    def __init__(self,data):
        self.right=self.left=None
        self.data = data
class Solution:
    def insert(self,root,data):
        if root==None:
            return Node(data)
        else:
            if data<=root.data:
                cur=self.insert(root.left,data)
                root.left=cur
            else:
                cur=self.insert(root.right,data)
                root.right=cur
        return root

    def levelOrder(self,root):
        #Write your code here

T=int(input())
myTree=Solution()
root=None
for i in range(T):
    data=int(input())
    root=myTree.insert(root,data)
myTree.levelOrder(root)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

import sys

class Node:
    def __init__(self,data):
        self.right=self.left=None
        self.data = data
class Solution:
    def insert(self,root,data):
        if root==None:
            return Node(data)
        else:
            if data<=root.data:
                cur=self.insert(root.left,data)
                root.left=cur
            else:
                cur=self.insert(root.right,data)
                root.right=cur
        return root

    def levelOrder(self,root,lst=None):
        print(root.data)
        if lst == None:
            lst = []
            lst.append(root.data)
            
        if root.left is not None:
            lst.append(root.left.data)
              
        if root.right is not None:
            lst.append(root.right.data)
            
        if root.left is not None: 
            self.levelOrder(root.left, lst)
            
        if root.right is not None: 
            self.levelOrder(root.right, lst)
        
        print(lst)  

T=int(input())
myTree=Solution()
root=None
for i in range(T):
    data=int(input())
    root=myTree.insert(root,data)
myTree.levelOrder(root)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}