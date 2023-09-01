{% capture content %}
### Day 22: Binary Search Trees 
- Instructions:
    - The height of a binary search tree is the number of edges between the tree's root and its furthest leaf. 
    - You are given a pointer, root, pointing to the root of a binary search tree. 
    - Complete the `getHeight` function provided in your editor so that it returns the height of the binary search tree. 
    - The first line of input contains an integer, `n`, denoting the number of nodes in the tree. 
    - Each of the n subsequent lines of input contain an integer, `data`, denoting the value of an element that must be added to the BST. 

{% capture details %}
{% highlight python linenos=table %}

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

    def getHeight(self,root):
        #Write your code here

T=int(input())
myTree=Solution()
root=None
for i in range(T):
    data=int(input())
    root=myTree.insert(root,data)
height=myTree.getHeight(root)
print(height) 

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Excercise
{% endcapture %}{% include details.html %}

{% capture details %}
{% highlight python linenos=table %}

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

    def getHeight(self,root,height=0, a_set=None):
        if root is None:
            return "None"
        root.height = height
        if a_set == None:
            a_set = set()
            a_set.add(height)
            
        if root.left is not None:
            root.left.height = height + 1
            a_set.add(root.left.height)
            self.getHeight(root.left, root.left.height,a_set)
            
        if root.right is not None:
            root.right.height = height + 1
            a_set.add(root.right.height)
            self.getHeight(root.right, root.right.height,a_set)
    
        if root.height == 0:
            return max(a_set)
            
T=int(input())
myTree=Solution()
root=None
for i in range(T):
    data=int(input())
    root=myTree.insert(root,data)
height=myTree.getHeight(root)
print(height)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
Solution
{% endcapture %}{% include details.html %}

{% endcapture %}{% include code.html %}