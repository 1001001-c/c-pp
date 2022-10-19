# 第二章 开始学习C++

> - 主要内容
>   - 创建c++程序
>   - c++程序的一般格式
>   - #include编译指令
>   - main() 函数
>   - 使用 cout对象进行输出
>   - 在c++程序中加入注释
>   - 合适以及如何使用endl
>   - 声明和使用变量
>   - 定义和使用简单函数



## 复习题

### 1

C++程序的模块叫什么？

> 函数

### 2

下面的预处理器编译指令是做什么用的？

`#include <iostream>`

> 加入头文件iostream
>
> > 这将导致在最终的编译之前，使用 iostream 文件的内容替换该编译指令。

### 3

下面的语句是做什么用的？

` using namespace std;`

> 使用命名空间std
>
> > 它使得程序可以使用 std 名称空间中的定义。

### 4

什么语句可以用来打印短语“Hello，world”，然后开始新的一行？

```c++
std::cout << "Hello, world" << std::endl;
```

### 5

什么语句可以用来创建名为cheeses的整数变量？

```c++
int cheeses;
```

### 6

什么语句可以用来将值32赋给变量cheeses？

```c++
cheeses = 32;
```

### 7

什么语句可以用来将从键盘输入的值读入变量cheeses中？

```c++
std::cin >> cheeses;
```

### 8

什么语句可以用来打印“We have X varieties of cheese,”，其中X为变量cheeses的当前值。

```c++
int cheeses;
std::cin >> cheeses;
cout << "We have " << cheeses << " varieties of cheese," << endl;
```

### 9

下面的函数原型指出了关于函数的哪些信息？

```c++
int froop(double t); // 函数名是 froop，需要传一个double类型的参数t, 函数的返回值类型是 int
void rattle(int n); //  函数名是 rattle，需要有一个int类型的参数你， 函数不返回参数
int prune(void); // 函数名是 prune，不需要传参，返回值的类型是int

/*调用函数 froop()时，应提供一个参数，该参数的类型为 double，而该函数将返回一个 int 值。例如， 可以像下面这样使用它： int gval = froop(3.14159); 
函数 rattle()接受一个 int 参数且没有返回值。例如，可以这样使用它： 
rattle(37); 
函数 prune()不接受任何参数且返回一个 int 值。例如，可以这样使用它：
int residue = prune();
*/
```

### 10

定义函数时，在什么情况下不必使用关键字return？

> 在函数返回类型为 void时不必使用关键字return
>
> >当函数的返回类型为 void 时，不用在函数中使用 return。然而，如果不提供返回值，则可以使 用它：return;

### 11

假设您编写的main( )函数包含如下代码：

```c++ 
cout << "Please enter your PIN: ";
```

而编译器指出cout是一个未知标识符。导致这种问题的原因很可能是什么？指出3种修复这种问题的方法。

> 没有使用std作用域
>
> 修复方法
>
> 1.`using namespace std;`
>
> 2.`using std::cout;`
>
> 3.`std::cout << "please enter you PIN:";`

## 编程练习

### 1

编写一个C++程序，它显示您的姓名和地址。

```c++
int main()
{
    string name, adress;
    name = "李智乾";
    adress = "山西省阳泉市山西工程技术学院";
    cout << "name :" << name << endl;
    cout << "adress :" << adress << endl;
    return 0;
}
```

### 2

编写一个C++程序，它要求用户输入一个以long为单位的距离，然后将它转换为码（一long等于220码）。

```c++
int main()
{
    int _long = 0;
    int _ma = 0;
    cout << "please input your distance (long) :" << endl;
    cin >> _long;
    _ma = 220 * _long;
    cout << "The number turn ma:" << _ma << endl;
    return 0;
}
```

### 3

编写一个C++程序，它使用3个用户定义的函数（包括main( )），并生成下面的输出：

> Three blind mice
>
> Three blind mice
>
> See how they run
>
> See how they run

其中一个函数要调用两次，该函数生成前两行；另一个函数也被调用两次，并生成其余的输出。

```c++
void f1(void)
{
    cout << "Three blind mice" << endl;
}

void f2(void)
{
    cout << "See how they run" << endl;
}

int main()
{
    f1();
    f1();
    f2();
    f2();
}
```

### 4

编写一个程序，让用户输入其年龄，然后显示该年龄包含多少个月，如下所示：

> Enter your age: 29

```c++
int main()
{
	int age = 0;
	int month = 0;
	cout << "Enter your age : ";
	cin >> age;
	month = age * 12;
	cout << "you have been through " << month << " months" << endl;
	return 0;
}
```

### 5

编写一个程序，其中的main( )调用一个用户定义的函数（以摄氏温度值为参数，并返回相应的华氏温度值）。该程序按下面的格式要求用户输入摄氏温度值，并显示结果：

> Please enter a Celsius value: 20
>
> 20 degrees Celsius is 68 degrees Fahrenheit.

下面是转换公式：

华氏温度 = 1.8×摄氏温度 + 32.0

```c++
int main()
{
	double c = 0.0;
	double f = 0.0;
	cout << "Please enter a Celsius value:";
	cin >> c;
	f = 1.8 * c + 32;
	cout << c << " degrees Celsius is " << f << " degrees Fahrenheit" << endl;
	return 0;
}
```

### 6

编写一个程序，其main( )调用一个用户定义的函数（以光年值为参数，并返回对应天文单位的值）。该程序按下面的格式要求用户输入光年值，并显示结果：

> Enter the number of light years: 4.2
>
> 4.2 light years = 265608 astronomical units.

天文单位是从地球到太阳的平均距离（约150000000公里或93000000英里），光年是光一年走的距离（约10万亿公里或6万亿英里）（除太阳外，最近的恒星大约离地球4.2光年）。请使用double类型（参见程序清单2.4），转换公式为：

> 1 light years = 63240 astronomical units

```c++
int main()
{
	constexpr int turn = 63240;
	double light_years = 0.0;
	double astronomical_units = 0.0;
	cout << "Please enter the number light years:";
	cin >> light_years;
	astronomical_units = light_years * turn;
	cout << light_years << " light years = " << astronomical_units << " astronomical units" << endl;
	return 0;
}
```

### 7

编写一个程序，要求用户输入小时数和分钟数。在main( )函数中，将这两个值传递给一个void函数，后者以下面这样的格式显示这两个值：

> Enter the number of hours: 9
>
> Enter the number of minutes: 28
>
> Time: 9:28

```c++
void clock(int h, int m) {
	cout << "Time " << h << ':' << m << endl;
}

int main()
{
	int h = 0;
	int m = 0;
	cout << "Enter the number of hours:";
	cin >> h;
	cout << "Enter the number of minuter:";
	cin >> m;
	clock(h, m);
	return 0;
}
```

