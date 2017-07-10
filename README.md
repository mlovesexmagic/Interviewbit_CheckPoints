# Interviewbit_CheckPoints

### Checkpoint 1: AMORTIZED2
What is the time complexity of the following code :

```
        int j = 0;
        for(i = 0; i < n; ++i) {
            while(j < n && arr[i] < arr[j]) {
                j++;
            }
        }
```
Solution: O(n)

### Checkpoint 2: Prettyprint
Print concentric rectangular pattern in a 2d matrix. 
```
class Solution:
    # @param A : integer
    # @return a list of list of integers
    def prettyPrint(self, A):
      rowSize = A * 2 - 1;
      colSize = rowSize;
      Matrix = [[A for x in range(colSize)] for y in range(rowSize)] 
      
      num = A-1;
      counter = 0;
    
      reduceRow = 2;
      reduceCol = 2;
      
      for r in range(num):
        counter = counter + 1;
        for i in range(counter-1,rowSize - reduceRow):
          for j in range(counter-1,colSize - reduceCol):
            Matrix[i+1][j+1] = A-counter;
        reduceRow = reduceRow + 1;
        reduceCol = reduceCol + 1;
            

      return Matrix;
```
      
 ### Checkpoint 3: Kth Smallest Element in the Array
 
```
 class Solution:
    # @param A : tuple of integers
    # @param B : integer
    # @return an integer
    def kthsmallest(self, A, k):
      B = [None] * len(A);
      for i in range(len(A)):
        B[i] = A[i];
      B.sort();  
      return B[k-1];
```
      
### Checkpoint 4: SUBTRACT - modify the value of first half nodes
```
  # Definition for singly-linked list.
class ListNode:
    def __init__(self, x):
        self.val = x
        self.next = None

class Solution:
    # @param A : head node of linked list
    # @return the head node in the linked list
    def subtract(self, A):
      size = 1;
      curNode = A;
      while(curNode.next != None):
        size = size + 1;
        curNode = curNode.next;

        
      len = size / 2;
      firstNode = A;
      for i in range(len):
        lastNode = A;  
        for j in range(size-i-1):
          # print(j)
          lastNode = lastNode.next;
        firstNode.val = lastNode.val - firstNode.val;
        firstNode = firstNode.next;
        
      return A;
```
### Checkpoint 5: Longest Consecutive Sequence
```
 class Solution:
    # @param A : tuple of integers
    # @return an integer
    def longestConsecutive(self, A):
        output, lengths = 1, {key: 0 for key in A}
        for i in A:
            if lengths[i] == 0:
                lengths[i] = 1
                left, right = lengths.get(i - 1, 0), lengths.get(i + 1, 0)
                length = 1 + left + right
                output, lengths[i - left], lengths[i + right] = max(output, length), length, length
        return output
        ```        
      

