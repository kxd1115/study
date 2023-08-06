#### C语言中的数据类型

1. int 整数
   
   * 储存一个int至少要占用一个机器字长，而字长根据计算机的位长决定
   
   * 目前规定的最小范围：-32768 ~ 32767
   
   ```c
   int erns;
   int hogs, cows, goats;
   
   
   // 直接赋值
   int hogs = 21;
   int cows = 32, goats = 14;
   ```
   
   

1. float 浮点数
   
   * 3.16E7表示3.16*10^7



> 位、字节和字
> 
> * 最小存储单元是位（bit），用来存储0和1
> 
> * 1字节为8位
>   
>   * 8位字节有256（2的8次方）种可能的0和1的组合方式
>   
>   * 因此8位字节可以用来表示0~255的整数或一组字符
> 
> * 字：自然存储单位
>   
>   * 计算机的字长越大，数据转移越快，允许的内存访问也更多



#### C语言函数

1. scanf() 读取键盘的输入

2. printf() 打印输出

