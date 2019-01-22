

```python
#Class node
class node:
    def __init__(self,value=None):
        self.value=value
        self.next=None
class linkedlist:
    def __init__(self):
        self.head=node()
    
    def append(self, value):
        cur=self.head
        newnode=node(value)
        while cur.next!=None:
            cur=cur.next
        cur.next=newnode
        return cur
    def display(self):
        cur=self.head
        list=[]
        while cur.next!=None:
            cur=cur.next
            list.append(cur.value)
        return list
    def length(self):
        cur=self.head
        count=0
        while cur.next!=None:
            cur=cur.next
            count+=1
        return count
    def get(self, index):
        if index>=self.length() or index<0:
            print("Index %i is out of boundaries. Enter an appropriate index"%index)
            return None
        
        cur=self.head
        idx=0
        while idx<self.length():
            if idx==index:
                cur=cur.next
                val=cur.value
            cur=cur.next
            idx+=1
        return val
    def deletebyindex(self, index):
        if index>=self.length() or index<0:
            print("Index %i is out of boundaries. Enter an appropriate index"%index)
            return None
        cur=self.head
        
        idx=0
        while True:
            nextnode=cur
            cur=cur.next
            if idx==index:
                nextnode.next=cur.next
                break
            idx+=1
       
    def deletebyvalue(self, data):
        cur=self.head

        #newnode=node(data)
        while True:
            nextnode=cur
            cur=cur.next
            if cur.value==data:
                nextnode.next=cur.next
                break
                
    def middlenode(self):     
        if self.length()%2==0:
            idxm=self.length()/2
        else:
            idxm=(self.length()+1)/2
        cur=self.head
        idx=0
        while idx<self.length():
            if idx==idxm:
                val=cur.value
            cur=cur.next
            idx+=1
        return val
    
    def middlenode2(self):
        slowpointer=self.head
        fastpointer=self.head
        while fastpointer.next.next!=None:
            slowpointer=slowpointer.next
            fastpointer=fastpointer.next.next
        return slowpointer.value
    
    def reverselinkedlist(self):
        cur=self.head
        previousnode=None
        nextnode=None
        #cur=cur.next
        while cur!=None:
            nextnode=cur.next
            cur.next=previousnode
            previousnode=cur
            cur=nextnode
        self.head=previousnode
            
    
           
            
        
        
        
        
#linked=linkedlist()
linked=linkedlist()
linked.append(1)
linked.append(2)
linked.append(3)
linked.append(5)
linked.append(5)
#linked.display(), linked.length(), linked.get(0), linked.deletebyindex(2), linked.display()
#linked.deletebyvalue(2), linked.display()
#linked.display(),
linked.middlenode()

```




    3


