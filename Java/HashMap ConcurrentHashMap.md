### HashMap ConcurrentHashMap

**为什么ConcurrentHashMap线程安全：**

在put时对这个节点sychronized加锁，保证安全。

#### 两者共同构造：

HashMap：数组+链表+红黑树

ConcurrentHashMap：（jdk1.7：Segment（集成ReenTrantLock）+HashEntry）synchronized+CAS+HashEntry+红黑树

**疑问：HashEntry是单链表类似的结构，如何通过计算hash值直接找到地址的？**答：是使用的HashEntry数组

