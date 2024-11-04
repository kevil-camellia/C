#### 1.求最大公因数，最小公倍数

辗转相除法

```c
#include<stdio.h>

//求解最大公因数
int max_number(int m,int n)
{
    /
	if(n==0)
	{
        return m;
	}
	else
	{
		return max_number(n,m%n);
	}
}
int min_number(int a,int b)

{
	int min;
	min = a*b/max_number(a,b);
	return min;
}


```

连续整数检测

```c
#include <stdio.h>


int main() {
 
   int a ,b ;
   scanf("%d %d",&a,&b);

   int c = gcd(a,b);//最大公因数 
   printf("c=%d",c);
 
 
}
int gcd(int m, int n) {
    int min = (m < n) ? m : n;
    for (int i = min; i > 0; i--) {
        if (m % i == 0 && n % i == 0) {
            return i;
        }
    }
    return 1; // 如果没有找到，返回 1
}
```

质因数分解法

```c
#include <stdio.h>


int main() {
 
   int a =24 ,b =12,i;
   int t =1;
   for(i=2;(i<=a ) && (i<= b);i++)
   {
   	while( (a%i ==0) && (b%i ==0))
   	{
   		t = t*i;
   		a =a/i;
   		b =b/i;  		
	   }
   }
   printf("t=%d",t);//最大公因数
}
```



#### 2.输出的细节问题

```c
printf("%d %d",a,c);
```

>==如果之间有空格 那么输出也会有空格   >>> 2  9==
>
>在 scanf 输入的时候，**要是有输出的时候  会先把所有的输入 全部执行**
>
>##### ==scanf 每次输入的时候一定要按下空格再输入下一个==

```c
scanf("%d")  //不能接受空格
gets(score)  //可以输入空格 不能输入换行符 enter
getchar()    //只能接受一个字符  
```



==getchar只能接受字符，不能指等于定任何变量==；

```c
  s=getchar();
  gets(s);
```

```c
#include <stdio.h>
int main()
{
	int n =0;
	while(getchar()!='\n')//可以接受空格 
	{
		n++;
		printf("个数=%d",n);
	}	
	
 } 
```

#### 3.八进制十进制

```c
#include <stdio.h>
int main() {
	int n;
	scanf("%d",&n);
	printf("%#o %d %#x\n",n,n,n);

}
```

>##### %#x  打印出 0x 前缀
>
>##### %#o  打印出 0前缀

#### 4.break  continue

#### 5.判断2~N之间的素数

```c
//【判断2~N之间的素数的】 
#include<stdio.h>
#include<math.h>
int main()
{
    int i,j;
    int N,a;
    scanf("%d",&N);
    for(i=2;i<=N;i++)       
    {
        a=0;               
        for(j=2;j<=sqrt(i);j++)    //判断 它的平方根 要等于不然4不会被判断
        {
            if(i%j==0)       
            a++;    
        }
        if(a==0)
		{
			 printf("%d\n",i);
					}                    
    }
    return 0;
}
```

#### 6.scanf("%d %s")输入的问题

- **整数输入 (`%d`)**：自动跳过空白字符。
- **字符输入 (`%c`)**：不跳过空白字符，直接读取下一个字符。

因此，在使用 `%c` 时，如果您希望跳过空白字符，您需要在格式字符串前加一个空格。

```c

```

#### 7.ASCII 码   A：65 a:97

>#### a[i] = (s[i] -'A' + 4)%26 + 'A'; 	

```c
#include <stdio.h>


int main()
{
  char s[6],a[6];
  gets(s); 
  for(int i=0;i<5;i++)
  {
  		if((s[i]>='A'&& s[i]<= 'Z'))
 	 {
  		a[i] = (s[i] -'A' + 4)%26 + 'A'; 	
  	}
  	else if(s[i]>='a'&& s[i]<= 'z')
  	{
  		a[i] = (s[i] - 'a' + 4)%26 + 'a';	
 	 }
  	
  }
    printf("s=%s",s);
	printf("a=%s",a);	
 } 
```

[http]: 

