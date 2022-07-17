Java泛型

**以下这个写法报错吗？**

```java
List list = new LinkedList();
list.add("11");
list.add(1);
```

答：不报错

类型擦除（泛型擦除）：使用泛型时加上的类型参数，在编译时去掉类型参数。

