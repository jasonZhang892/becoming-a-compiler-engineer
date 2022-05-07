# 编译技术入门与实战

## Cooper 教授 L18-IR 评注

### 0 - 16

复习

### 17

引入了BB的概念
BB引出了CFG的概念

### 18

SSA是重要的概念。换名原则。
SSA能够极大简化某些分析。

A = B + 1;
A = 3 + C;
D = A + 2;
-->
A1 = B + 1;
A2 = 3 + C;
D = ??? + 2;

Kills 也是编译中的经典概念。

### 19

在汇聚点考虑 phi 节点。

### 20

Phi 节点：存在性、最优解
每个汇聚点对每个变量考虑phi
有些phi可以删除掉（确定性的）

### 21

优劣分析，现在的我们看不懂，没关系。

### 22

冷知识：IR的数量大于编译器的数量

### 23

命名空间、or、名字空间。

跳转到 slide p30 先看下。

### 24

注意符号表的选择和设计是经验艺术。
初学者一般是仿照现有设计。
可以大胆的简化，刚好够用就行。

### 25

现实世界各种设计规则的组合爆炸。
还有实际程序运行中的速度和空间问题。

词法作用域：在编译时刻就完成名字绑定。
动态作用域：根据调用序列。

例子：
```C
int y;
Foo (x: int){
  return x + y;
}

foo(x); // use global y.

goo (z: int) {
  int y;
  foo(x); // ???
}
```

### 26

想象一个链表。
从最内层开始查，先查到一个就停。
C语言中的大括号构建了名字空间。

### 27

练习：搜索Python的相关文章。

defy：违反

### 28

实际工程化中的各种麻烦事情。
会导致新手无法预计工作时间 ;-)
实现细节选择特别多。最好是抄设计，参考现成的编译代码框架。

### 29

在代码生成上，需要考虑名字空间，具体实现细节。

### 30

最后的图，一开始贴出来比较好。