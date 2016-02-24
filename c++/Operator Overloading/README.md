##C++ Note
####Operator Overloading（运算符重载）
- 对运算符语义的重新定义（即，在不同情况下对同样的运算符做不同的解释）

- 运算符函数：运算符可看作函数

 - `operand1 op operand2`可理解为：`op( operand1, operand2 )`
 - 如：`a+b => +(a,b) => Add( a, b )`
 - ps. 二元运算符是一个具有两个参数的函数； 一元运算符是一个具有一个参数的函数

- 运算符重载的作用：用自然的方式使用用户自定义的类类型。①与基本类型的使用风格一致；②提高程序的可理解性

- 运算符重载的两种形式
  - 类成员运算符重载
  - 友元运算符重载

- 不能重载的运算符：**`:: .* ?: . sizeof`**


#####类成员运算符重载
- 在类中定义运算符函数

- 一般形式：

  ```bash
  类型 类名::operator 运算符( 参数表 )
  {
     … // 运算符函数体
  }
  ```

- 重载二元运算符时，成员运算符函数只需显式传递一个参数（即二元运算符的右操作数），而左操作数则是该类对象本身，通过this指针隐式传递。
  `c1 + c2 ; <-> c1.operator +(c2);`

- 重载一元运算符时，成员运算符函数没有参数，操作数是该类对象本身，通过this指针隐式传递。
  `-c1 ; <-> c1.operator - ( );`


```cpp
class COMPLEX { //complex.h
  public:
    COMPLEX(double r = 0, double i = 0); // 构造函数
    COMPLEX(const COMPLEX & other); // 拷贝构造函数
    void print(); // 打印复数
    // 重载加法运算符（二元）
    COMPLEX operator + (const COMPLEX & other);
    // 重载减法运算符（二元）
    COMPLEX operator - (const COMPLEX & other);
    COMPLEX operator - (); // 重载求负运算符（一元）
    // 重载赋值运算符（二元）
    COMPLEX operator = (const COMPLEX & other);
  protected:
        double real, image; // 复数的实部与虚部
};
```

######赋值运算符的重载
- 若某个类没有重载赋值运算符，则编译器将自动生成一个缺省的赋值运算符， 缺省赋值运算符采用浅复制策略，把源对象逐位地拷贝到目标对象：
  - `c1 = c2 ;`

- 不含指针成员的类使用缺省赋值运算符即可， 含指针成员的类应重载赋值运算符，实现深复制策略。

- **解决方法：重载赋值运算符**

```cpp
/*
先释放指针原来指向的内存空间，然后再重新分配
内存空间，最后再把需要拷贝的内容置入这个空间
内。既避免了内存垃圾，也避免了指针重名。这就
是深复制（ deep copy）。
*/
STRING & STRING::operator = (const STRING & another) {
    length = another.length;
    if (buffer)
        delete[] buffer;
    buffer = new char[length + 1];
    if (buffer != NULL)
        strcpy(buffer, another.buffer);
    return *this;
}
```

######下标运算符[]的重载
- 形参为整型
- 返回值类型为引用类型

```cpp
const int MAX_SIZE = 10; // 定义符号常量表示向量的大小
class VECTOR {
    public:
        VECTOR() // 构造函数
        {
            int loop;
            for (loop = 0; loop <= MAX_SIZE - 1; loop = loop + 1)
                table[loop] = loop;
        }
    int & operator[](int index) // 取向量元素
        {
            if ((index < 0) || (index > MAX_SIZE - 1)) {
                cout << "Index out of bounds.\n";
                exit(1);
            }
            return table[index];
        }
    protected:
        int table[MAX_SIZE]; // 向量的内容
};
int main() {
    VECTOR label; // 定义向量对象
    cout << label[2] << "\n"; // 输出结果为2
    label[2] = 8; // 改变第三个分量的值
    cout << label[2] << "\n"; // 输出结果为8
    // 引起程序异常终止，提示Index out of bounds.
    cout << label[10] << “\n”;
    return 0;
}
```

#####友元（ friend）
- 友元（ friend）关系允许类的设计者选择出一组其他的类或函数，使得它们可以访问该类的私有和受保护成员。

- 在类的声明中，用friend声明的函数或类，即是该类的友元。

- 一个类的友元可以是：
  - 游离函数（不属于任何类的函数）
  - 另一个类
  - 其他类的成员函数。

- 友元关系破坏了类的封装性，不可滥用。

######游离函数作为友元
```cpp
// 类VALUE中定义了一个友元函数set()，注意set()不是该类的成员函数
class VALUE {
    public:
        //声明set()为VALUE的友元
        friend void set(VALUE obj, int x);
    private:
        int value;
};
void set(VALUE obj, int x) // 实现友元函数set()
{
    obj.value = x; // set()可以象VALUE成员函数一样访
                   // 问obj的私有和受保护成员
}
```

######另一个类作为友元
```cpp
class Y; // Y类的引用性声明
class X {
    public:
        // 把Y类声明为X类的友元，则Y类的所有成员函数都是X的友元
        friend Y;
    private:
        int k;
        void m_Xfunc();
};
class Y {
    public:
        void m_Yfunc(X & obj);
};
void Y::m_Yfunc(X & obj) {
    obj.k = 100; // Y类的成员函数是X的友元，可以访问X的私有和受保护成员
}
```

######其它类的成员函数作友元
```cpp
class Y {
    public:
        void Yfunc();
};
class X {
    public:
        friend void Y::Yfunc(); // 把Y类的Yfunc函数声明为X类的友元
    private:
        int k;
    void m_Xfunc();
};
void Y::Yfunc() {
    X obj;
    obj.k = 100; // 该函数是X的友元，可以访问X的私有和受保护成员
}
```

- 解决类成员函数运算符重载存在的问题：第一操作数（二元运算的左操作数）必须是本类对象。

- 形参设置规则：
  - 一元运算符必须显式声明一个形参。
  - 二元运算符必须显式声明二个形参。

- 下列运算符不能作为友元重载：`= () [] ->`

- 友元函数不是该类的成员，因此在友元函数中不能使用this指针。

- 采用友元运算符重载改进

  ```cpp
  class INTEGER {
    public:
        INTEGER(int i = 0); // 构造函数
        INTEGER(const INTEGER & other); // 拷贝构造函数
		// 友元重载加法运算符
		friend INTEGER operator + (INTEGER left, INTEGER right);
    private:
        int value; // 私有数据
  };
  ```

######Input/Output Overload
```cpp
#include <string>
#include <iostream>
using namespace std;
class Fruit; //对于一些编译器，在重载<<和>>时需要将类和友元额外再声明一次
ostream &operator << (ostream & out, const Fruit & x);
istream &operator >> (istream & in , Fruit & x);
class Fruit {
    public:
        Fruit();
        friend ostream& operator << (ostream & out, const Fruit & x);
        friend istream& operator >> (istream & in, Fruit & x);
    private:
        string name, color;
};
```

######Increment/decrement Overload
```cpp
class COMPLEX { //complex.h
    public:
        COMPLEX(double r = 0, double i = 0); // 构造函数
	    COMPLEX(const COMPLEX & other); // 拷贝构造函数
	    void print(); // 打印复数
	    COMPLEX & operator++(); //重载前置++
	    COMPLEX operator++(int); //重载后置++
	    COMPLEX & operator--(); //重载前置--
	    COMPLEX operator--(int); //重载后置--
    protected:
        double real, image; // 复数的实部与虚部
};
COMPLEX & COMPLEX::operator++() //COMPLEX.CPP
{
    real += 1;
    image += 1;
    return *this;
}
COMPLEX COMPLEX::operator++(int) {
    COMPLEX before = * this;
    real += 1;
    image += 1;
    return before;
}
COMPLEX & COMPLEX::operator--() //COMPLEX.CPP
{
    real -= 1;
    image -= 1;
    return *this;
}
COMPLEX COMPLEX::operator--(int) {
    COMPLEX before = * this;
    real -= 1;
    image -= 1;
    return before;
}
```


######Overloading function all operator: ()
```cpp
#include <iostream>
using namespace std;
class Exchange {
    public:
        void operator()(int & , int & );
};
void Exchange::operator()(int & x, int & y) {
    int t;
    t = x;
    x = y;
    y = t;
}
int main() {
    Exchange swap;
    int i = 20;
    int j = 30;
    cout << "Before swap:i=" << i << ", j=" << j << endl;
    swap(i, j);
    cout << "After swap:i=" << i << ", j=" << j << endl;
    return 0;
}
```


```cpp
#include <iostream>
using namespace std;
class Matrix {
    private
        double v[3][3];
    public:
        Matrix(double[][3], int);
	    Matrix() {}
	    double & operator()(int, int);
};
Matrix::Matrix(double ve[][3], int r_size) {
    if (r_size != 3)
        out << " Error!!";
    else
        for (int i = 0; i < 3; i++)
            for (int j = 0; j < 3; j++)
                v[i][j] = ve[i][j];
}
double & Matrix::operator()(int i, int j) {
    return v[i][j];
}
void main() {
    double a[3][3];
    int i, j;
    for (i = 0; i < 3; i++)
        for (j = 0; j < 3; j++)
            cin >> a[i][j];
    Matrix M(a, 3);
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) cout << M(i, j) << " ";
        cout << endl;
    }
}
```


- operator() : Most obvious and probably most important usage—provides the usual function call syntax for objects.

- Such objects act like functions called function object.

- An operator() must be a member function






