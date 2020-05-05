## C++



### 基础



#### 内联函数

> 用来加速程序运行速度

> 区别与常规函数，在与编译过程

```c++
inline double square(double x){return x*x}
```



#### 函数模板

> 使用泛型来定义函数
>
> 与函数重载相反

```c++
template <typename AnyType>
void Swap(AnyType &a,AnyType &b)//int c=1,b=2;Swap(c,b);&表示引用变量，给变量取别名
{
    AnyType temp;
    temp =a;
    a=b;
    b=temp;
}
```

> 函数模板重载

```c++
template <typename T>
void Swap(T &a,T &b)
{}

template <typename T>
void Swap(T a[],T b[],int n)
{}
```

> 实例化、具体化

```c++
template void Swap<int>(int,int);//使用Swap()模板生成int类型的函数定义//通用模板
template <> void Swap<int> (int&,int&);//不要用Swap()模板生成函数定义，使用int类型显式定义函数定义//具体化模板

```

