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
