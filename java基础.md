## java基础

## 1. String 、StringBuffer和StringBuilder的区别是什么

三个角度来说吧 ，

第一个就是可变和不可变的角度

String 是属于 finnal修饰符修饰的 所以它是不可变的，

StringBuffer 和StringBuilder 这俩都是继承 AbstractStringBuilder 类的 AbstractStringBuilder 是由字符数组保存的所以是可变的

线程安全的角度

String 是不可变的 所以线程是安全的

StringBuffer 对方法加了同步锁，或者对调用的方法加了同步锁，所以线程是安全的

StringBuilder 是非线程安全的

执行效率

String是最慢的，因为String是不可变的 所以每次修改它的话 都是重新生成一个String对象然后 再把指针指向新生成的对象，不仅效率低还浪费内存空间

StringBuilder 比StringBuffer效率更高一些



## 2.hashcode()和equals()

hashcode() 其实主要是查 哈希码 是一个int整数，这个是记录对象在哈希表上的索引位置的，

比如说 当你把对象放在hashset上  hashset会先通过hashcode 值来判断对象的加入位置，并且和set中的其他对象的hashcode值做比较，如果没有一样的，hashset会假设对象没有重复出现。

如果出现了hashcode值一样的情况，那么需要用equals方法来判断 两个对象的值是否相等，如果相等的话则不加入到set中。

hashcode值一样的情况下，两个对象不一定相等，但如果两个对象 equals ，他们的hashset值一定相等。

重写 equals 方法的话，一定要重写 hashcode方法，因为判断两个对象是否相等的情况是先来对比hashcode值是否相等，再用equals方法，如果不重写hashcode方法的话有可能会出现，equals 相等但是hashcode值不相等的情况。 







