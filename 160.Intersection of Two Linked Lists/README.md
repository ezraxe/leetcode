## Solution

### Approach #2(Hash Table) [Accepted]

遍历其中一个链表，如A。将链表中的每一个节点的地址存入hash set，然后遍历链表B，找出B中的每一个节点是否在hash set中，如果存在，则第一个查找到的节点就是相交节点的开始节点

#### 复杂度分析

* 时间复杂度：O(m+n)
* 空间复杂度：O(n) or O(m)

### Approach #3(Two Pointer) [Accepted]

* 维护两个指针pA和pB，分别初始化为链表A和B的head结点。然后让两者每次一个节点的遍历链表
* 当pA到达链表结尾时，让其指向链表B的head节点。同样的，当pB到达链表结尾时，让其指向链表A的head节点
* 如果在任意节点内pA与pB相遇，则pA/pB就是所求的相交节点

>解释：假设A={1,3,5,7,9,11}，B={2,4,9,11}，因此，所求得的相交节点应该是9。由于B链表更短，所以pB将会先到达结尾。此时pB比pA少遍历2个节点就到达了结尾，将pB指向链表A的head结点，继续遍历。当pA也遍历完链表后，使其指向链表B的head节点。因此，在第二次迭代中，pA可以比pB少遍历2个节点

#### 复杂度分析

* 时间复杂度：O(m+n)
* 空间复杂度：O(1)