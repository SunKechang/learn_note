ArrayList LinkedList Vector

#### ArrayList扩容机制？

ArrayList扩容的本质是计算出新的扩容数组的size后实例化，并将原有数组内容复制到新数组中。默认情况下，新的容量会是原容量的1.5倍。

#### Array与ArrayList区别？应用情况？

- Array可以包含基本类型和对象类型，ArrayList只能包含对象类型
- Array大小是固定的，ArrayList大小是动态变化的
- ArrayList提供了很多方法和特性，addAll(), removeAll(), iterator()等等

#### ArrayList与Vector区别？

- Vector线程安全（使用synchronized）， ArrayList线程不安全
- ArrayList单次扩容是原基础的0.5倍，Vector扩容为1倍，ArrayList有利于节约内存空间。



