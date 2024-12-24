# C++的编译和执行

## 编译执行过程

1. 编译（预处理->编译->目标文件）

形成目标代码/文件。过程：如helloworld.cpp预处理成中间文件helloworld.ii；再编译成汇编helloworld.s，再汇编成二进制文件helloworld.o

2. 连接

将目标代码（helloworld.o）跟C++函数库相连接，并将源程序所用的库代码与目标形成最终可执行的二进制机器代码（可执行程序Helloworld.exe）

3. 执行

在特定的机器环境下运行C++应用程序


## 执行过程：

```
D:\PostGraduate\Learn\C>g++
-o helloworld.ii -E helloworld.cpp

D:\PostGraduate\Learn\C>g++
-o helloworld.s -S helloworld.ii

D:\PostGraduate\Learn\C>g++
-o helloworld.o -c helloworld.s

D:\PostGraduate\Learn\C>g++
-o Helloworld.exe helloworld.o

D:\PostGraduate\Learn\C>Helloworld
```


# namespace

所谓namespace，是指标识符的各种可见范围。C++语言提供一个全局的命名空间namespace，可以避免导致全局命名冲突问题。

## 无名命名空间

标准C++引入命名空间，除了可以避免成员的名称发生冲突之外，还可以使代码保持局部性，从而保护代码不被他人非法使用。如果你的目的主要是后者，而且又为替命名空间取一个好听、有意义、且与别人的命名空间不重名的名称而烦恼的话，标准C++还允许你定义一个无名命名空间。你可以在当前编译单元中（无名命名空间之外），直接使用无名命名空间中的成员名称，但是在当前编译单元之外，它又是不可见的。

# 引用

1. 引用并非对象，只是为一个已经存在的对象起的别名；

2. 引用只能绑定在对象上，不能与字面值或某个表达式结果绑定在一起；

```
int &ref_value = 10;  //是错误的

// 可以改为：

const int &ref_value = 10;
```

3. 引用必须初始化，所以使用引用之前不需要测试其有效性，因此使用引用可能会比使用指针效率高。

## 指针和引用的关系

引用对指针进行了简单封装，底层仍然是指针；

获取引用地址时，编译器会进行内部转换。
