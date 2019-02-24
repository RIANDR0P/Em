i. 访问名称空间std的四种方案：
1/ 在函数定义之间，using namespace std;
2/ 放在特定的函数之中；
3/ using std::cout;
4/ 直接使用 std::cout << "text";

ii.变量名开头不要用下划线_

iii. cout << hex; //16进制；
     cout << oct；  //8进制；

cin.getline
cin.get()
cin.get(name,lim).get();  //跳过结尾换行符

cin >> str;
cin.get();
或
(cin >> str).get();

int len1=str1.size();

getline(cin,str);  //用于string

union 共用体
enum 枚举

谨记：将指针初始化为确定的地址

数据对象P102

int * p= new int ;
>>>
delete *p;

int * p= new int [10];
...
delete [] p;

关于new与delete:
1/ delete用于new划分的内存
2/ 不要释放一个内存两次
3/ 有无方括号应一致；
4/ 改变指针变量最后应返回初始值delete

键盘模拟 EOF 
while((ch=cin.get())!=EOF)

注：strcmp(a,b)函数当二者不等时返回真值

#include<cctype>
     if(isalpha(ch))
     //isalpha,isdigits,isplace,ispunct
     
switch无法处理浮点值。
switch效率高于if else

ofstream
#include<fstream>
     ofstream outfile;
     outfile.open("new.text");
     ...
     outfile.close;
     
ifstream

#include<cstdlib)
     ifstream infile;
     infile.open("list.text")
     if(!infile.is_open())
     {
          exit(EXIT.FAILURE);
          
 #5.5.4文件尾条件 eof fail
     
     函数与数组
     调用函数时，可以：
     arr(cook+4,5)   //cook为指针
     
  7.4 函数和二维数组
  
  void array(int (*ar)[4], int n)   // n固定列数
  原： row=3;column=4;
  
  
  处理不符合类型：
  if(!cin)
  {
     cin.clear;
     while(cin.get()!='\n')
          continue;
      cout<<"Please enter: ";
      //break; //不符合时直接跳出
   }
  

#处理字符串
     while(*str)
     {
          statement;
          str++；
     }

7.8 函数与array对象

引用
int & array=rabbit;      //必须初始化   

8.5 函数模板
template<typename T>
void swap(T &a, T &b)；
     ...
template<typename T>
void swap(T &a, T &b)
{
     T temp;
     temp=a;
     a=b;
     b=temp;
}
     
8.5.1 重载模板
template<typename T>
void swap(T &a, T &b);
     
template<typename T>
void swap(T &a, T &b, int c);
     
8.5.3 显式具体化
struct job
{
     double salary;
     int floor;
}
template <> void swap<job>(job &j1, job &j2);
...
template <> void swap<job>(job &j1, job &j2)
{
     double t1;
     int t2;
     t1=j1.salary;
     j1.salary=j2.salary;
     j2.salary=t1;
     ...
}

!!模板并非函数定义，使用（例如int)的模板实例是函数定义；
!!显式实例化
template void job<int>(int , int );
!!显式具体化     
template <>void job<int>(int &, int &);
     
隐式实例化、显式实例化、显式具体化统称具体化（specialization)     
     
#cout.setf
cout.setf()的作用是通过设置格式标志来控制输出形式，
其中ios_base::fixed表示：用正常的记数方法显示浮点数(与科学计数法相对应)；
ios_base::floatfield表示小数点后保留6位小数。

??提升转换与标准转换

9.内存模型和名称空间
头文件包含内容：
     函数原型
     结构声明。
     类声明。
     模板声明
     内联函数。
     符号常量（#define 或 const)
     
9.1 单独编译
#ifndef
...
#endif
9.2
静态初始化
1/ 位于代码块内 无链接
2/ 函数外       用于当前文件，内部链接
3/ static       外部链接

9.2.4
引用外部变量
extern int blem;   //此时为引用声明（declaration)
定义(definition)
1/ extern int blem=10;
2/ int blem=10;
3/ int blem;

9.2.5
定义外部变量后，若在其他文件定义相同变量，不合法。（违反单定义规则
     需添加 static 隐藏常规外部变量
     
处理行输入超过目标数组
#include<iostream>
const int ARSIZE = 10;
void strcount(char * str);

using namespace std;

int main()
{

	char input[ARSIZE];
	char next;
	cin.get(input, ARSIZE);
	while (cin)
	{
		cin.get(next);
		while (next != '\n')
			cin.get(next);
		strcount(input);
		cin.get(input, ARSIZE);
	}
	return 0;
}



void strcount(char * str)
{	 int count = 0;
	while (*str++)
		count++;
	cout << count << endl;
}

// count 可能命名重复，可换一个关键词 //定义全局变量时

9.2.7
cv-限定符
volatile 
mutable
const 全局变量的链接性为内部，即在多文件中默认每个源文件添加const int..（可理解为static
若希望链接性为外部，可利用extern 覆盖默认，但相关所有文件必须用extern声明。
9.2.8
函数默认链接性为外部
可利用static设定其链接性为内部
但函数定义及原型必须加上static关键字。

定位运算符new
不跟踪哪些内存单元已被使用，不查找未使用内存块。
参数 std::size_t 指定请求字节数
#include<iostream>
#include<new>
const int BUF= 512;
const int N = 5;
char butter[BUF];
int main()
{
	using namespace std;
	double *pd1, *pd2;
	int i;
	pd1 = new double[N];
	pd2 = new(butter) double[N];
	for (i = 0; i < N; i++)
		pd2[i] = pd1[i] = 1000 + 20 * i;
	cout << "adress:\n" << "heap: " << pd1
		<< "static: " << (void*)butter << endl;   //不使用(void*)强制转换将打印出字符串（butter为char*)
	for (i = 0; i < N; i++)
	{
		cout << pd1[i] << ": " << &pd1[i];
		cout<<pd2[i] << ": " << &pd2[i] << endl;
	}
	return 0;
}
//注：butter指定静态内存，而delete只能用于指向常规new运算符指定的heap内存。

9.3 名称空间
