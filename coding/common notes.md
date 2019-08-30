# Common mistakes and avoidance measures in programming
### 1 路径导致的程序错误
尽量多做路径是否存在的判断，对于文件的读取，判断是否读取成功

### 2 路径权限问题
Linux系统中应用程序默认是没有写文件权限的，如果必要程序中要做一些权限检测，如果权限不够高可以报错退出，或者程序升高权限

### 3 编程中的数值问题
整数与浮点数使用不当的问题，小整数除以大整数得0，编程中遇到除法时一定要注意整数除的问题。
整数中有符号数和无符号数的问题，整数分为unsigned 和 signed，对于unsigned数做减法时一定要小心，可能会差生溢出
``` c
#include<stdio.h>
int main()
{
   unsigned int a=1;
   a=a-2;
   printf("a is: %u\n",a);
   unsigned int b=0xffffffff;
   printf("b is: %u\n",b);//b is: 
   return 0;
}
/********output*****
a is: 4294967295
b is: 4294967295
********************/
```
###4 指针错误，常发生在结构体，对象出现的时候，声明一个指针后没有指向一个实体，然后将这个指针按照实体来操作
```c

typedef Mat{
	int *data;
	int row;
	int col;
};
Mat* m;
m->col=23;

Mat* m=new Mat;

```
### 5 申请一个数组后一定要考虑是否清0


### 6 多重循环中index变量不要弄混，因为经常使用for(int i ...) 所以会不自觉的在内层循环里写i作为index变量，这是一个巨大的错误

