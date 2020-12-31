设置长方柱的类，数据成员包括length(长)、width(宽)、height(高)、volume(体积)。要求用成员函数实现以下功能：

（1）初始化长方柱的长、宽、高，体积均为零，使用成员初始化列表进行初始化；

（2）能设置长宽高的数值

（3）计算体积

（4）输出体积

```c++
#include <iostream>
using namespace std;
class Rectangle{
public:
	Rectangle() :iLength(0), iWidth(0), iHeight(0), iVolume(0){};
	~Rectangle();
	void SetLength(int iLength){
		this->iLength = iLength;
	}
	void SetWidth(int iWidth){
		this->iWidth = iWidth;
	}
	void SetHeight(int iHeight){
		this->iHeight = iHeight;
	}
	void CountVolume(){
		iVolume = iLength * iWidth * iHeight;
	}
	void PrintVolume(){
		this->CountVolume();
		cout << iVolume << endl;
	}
private:
	int iLength;
	int iWidth;
	int iHeight;
	int iVolume;
};
Rectangle::~Rectangle(){}
int main(){
	Rectangle Rec;
	Rec.SetHeight(10);
	Rec.SetLength(5);
	Rec.SetWidth(2);
	Rec.PrintVolume();
	fflush(stdin);
	getchar();
}
```

------

使用C++实现栈的相关操作。

   1）入栈操作

   2）出栈操作

   3）判断栈是否为空

   4）判断栈是否为满

~~~c++
#include <iostream>
#define MaxSize 3
using namespace std;
typedef struct Stack{
    int data[MaxSize];
    int top;
}Stack;
void InitStack(Stack *stack){
    stack->top = -1;
}
void Pop(Stack *stack, int data){
    if (isFull(stack)){
        cout << Is Full << endl;
        return;
    }
    stack->data[++stack->top] = data;
}
void Push(Stack *stack){
    if (isEmpty(stack)){
        cout << Is Empty\n << endl;
        return;
    } 
    cout << stack->data[stack->top--] << endl;
}
int isEmpty(Stack *stack){
    if (stack->top == -1)
        return 1;
    else
        return 0;
}
int isFull(Stack *stack){
    if (stack->top == MaxSize - 1)
        return 1;
    else
        return 0;
}
int main(){
    Stack S;
    InitStack(&S);
    cout << Empty: << isEmpty(&S) << endl;
    cout << Full: << isFull(&S) << endl;
    Push(&S);
    Pop(&S, 1);
    cout << Empty: << isEmpty(&S) << endl;
    cout << Full: << isFull(&S) << endl;
    Pop(&S, 2);
    Push(&S);
    Pop(&S, 3);
    Pop(&S, 4);
    Pop(&S, 5);
    cout << Full: << isFull(&S) << endl;
    Push(&S);
    Push(&S);
    Push(&S);
}
~~~



------

下列关于构造函数的论述中,不正确的是  **C**

   A. 构造函数的函数名与类名相同        B. 构造函数可以设置默认参数

 **C. 构造函数的返回类型缺省为int型** (`没有返回类型`)    D. 构造函数可以重载

------

若一个类的成员函数前用static关键字修饰，则该成员函数  **B**

A. 可以被声明为const             **B. 没有this指针**

C. 可以访问该类的所有成员           D. 只能用对象名来调用

---

**B**  不是属于面向对象程序设计的特性

   A. 抽象性     **B. 数据相关性**       

   C. 多态性     D. 继承性

----

将对某一类数据的处理算法应用到另一类数据的处理中,要用到C++的  **D**

   A. 类       B. 虚函数         

   C. 运算符重载   **D. 模板**

----

动态内存分配的主要目的是  **B**

   A. 使程序按动态联编方式运行         **B. 正确合理的使用内存**

   C. 提高程序的运行速度            D. 提高程序的可维护性

----

在C++函数的形参前加const关键字,是为了提高函数的  **C**

   A. 数据封装性   B. 可理解性        

   **C. 可维护性**    D. 可重用性

---

函数重载的目的是  **B**

   A. 实现共享    **B. 使用方便，提高可读性**  

   C. 提高速度    D. 减少空间

----

如果一个类的成员函数print()不修改类的数据成员值，则应将其声明为  **A**

   **A. void print() const;**            B. const void print();

   C. void const print();            D. void print(const);

----

在程序代码：A::A(int a, int *b) { this->x = a; this->y = b; }中，this的类型是  **C**

   A. int      B. int *          

   **C. A**       D. A *

----

友元函数  **B**

A. 可以被声明为const             **B. 没有this指针**

C. 可以用类名或对象名来调用         D. 只能用对象名来调用

----

若一个类的成员函数前用static关键字修饰，则该成员函数  **B**

A. 可以被声明为const             **B. 没有this指针**

C. 可以访问该类的所有成员           D. 只能用对象名来调用

----

C++是用  **C** 实现接口重用的

   A. 内联函数    B. 虚函数         

   **C. 重载函数**    D. 模板函数 

----

公有继承的派生类对象可以访问其基类的  **A**

 **A. 公有成员**    B. 公有成员及受保护成员 

 C. 受保护成员   D. 私有成员

----

设置虚基类的目的是   **D**

   A. 简化程序      B. 使程序按动态联编方式运行 

   C. 提高程序运行效率  **D. 消除二义性**

----

关于运算符重载的不正确的描述是  **A**

   **A. 运算符重载函数是友元函数**         B. 体现了程序设计的多态性

   C. 增加新的运算符              D. 使运算符能对对象操作

------------

指针常量与常量指针

**从右往左**读，遇到 p 就替换成“p is a ”遇到 * 就替换成“point to”

```c++
const int * p; //常量指针, p is a point to int const(p是一个指向整型常量的的指针), 可修改指针的指向, 不可修改指针指向的值
int const * p; //同上,p is a point const int
int * const p; //指针常量, p is a const point to int(p是一个常量指针, 指向整型), 不可修改指针的指向, 可修改指针指向的值
```

> *象征着地址，const 象征着内容；
> 谁在前面谁就不允许改变

-----

| char   | 1    |
| ------ | ---- |
| short  | 2    |
| int    | 4    |
| float  | 4    |
| long   | 8    |
| double | 8    |

-----

**如何让成员变量变成静态成员变量** ——> 使用static关键字修饰

----

**八进制转化成十进制****:**先转化为二进制(按照顺序, 将每一位八进制数改写成等值的3位二进制数, 次序不变), 在由二进制转化为十进制

----

若需要把一个函数“void F( )；”定义为一个类AB的友元函数，则应在类AB的定义中加入一条语句**:** 

```c++
friend void F();
```

----

**纯虚函数**  定义时在函数参数表后加0，它表明程序员对函数不定义，其本质是将指向函数体的指针定为NULL

----

以下为Windows NT下的32位C++程序:

```c++
//有以下定义
char str[] = “Hello”;
char *p = str;
int n = 10;
//则
sizeof (str )=_______**6**________ ;
sizeof(p)=______**4**______;
sizeof(n)=______**4**______;
```

----

假定A为一个类，则语句A (const A& a）；为该类的  **复制构造函数**

----

在C++中，函数的参数有两种传递方式，它们是按值调用和  **按引用调用**

----

运算符( )与运算符[]必须重载为  **成员函数**

----

如果一个模板声明列出多个参数，则多个参数之间必须使用  **逗号**  隔开，每个参数都必须重复使用关键字  **class**

---

类istream的成员函数  **get()**  从指定流中读取一个字符，成员函数  getline()**  和read 从指定流中读取多个字符

----

当一个成员函数被调用时，该成员函数的  **this**  指针指向调用它的对象

----

```c++
#define mult(a, b) a*b
mult(2, 2+3) //输出结果为7而不是10，因为宏替换只是简单替换为2*2+3, 而不是2*(2+3)
```

---

设Graph类中有一个纯虚函数draw( )，该类派生一个子类line，draw函数在类line依然没有定义，则允许为line类创建对象 **错**

---

在C++程序中，任何需要检测异常的语句都必须在try语句块中执行，异常必须由紧跟着try语句后面的catch语句来捕获并处理。 **对**

---

使用运算符new创建对象时，会调用类的构造函数 **对**

---

如果类A被说明成类B的友元，则类B的成员即类A的成员 **错**

---

构造函数能声明为虚函数，析构函数不可以声明为虚函数。 **错**

---

const char *p说明了p是指向字符串的常量指针 **错**

---

C++语言的默认访问权限是private **对**

---

空类型void可以用于说明一个函数不返回任何值。**对**
