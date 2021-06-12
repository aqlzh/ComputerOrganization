> 你一定要做自己，做自己喜欢的事，然后把自己交给命运！
> 专注与静心


@[toc]
# I/O 接口
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210608215105741.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
## IO 接口的功能

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210612154223609.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
## IO 接口的基本结构


==注意==

- 1、内部接口与外部接口
- 2、IO接口中实现功能的五大硬件

![](https://img-blog.csdnimg.cn/20210612160340294.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

==注意==：
1、接口与端口的区别  

[参考链接](https://blog.csdn.net/number1killer/article/details/79226772)

## IO接口工作过程
- IO接口工作过程  如下序号顺序
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210612165507457.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
# 接口与端口
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210612170836844.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
## IO 端口及其编址
### 统一编址
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210612171540928.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
- ==优点== ：不需要专门的输入/输出指令，可使CPU访问的操作更灵活、更方便，还可使端口有较大的编址空间。
- ==缺点== ： 端口占用了存储器地址，使内存容量变小，而且利用存储器编址的I/O设备进行数据输入/输出操作，执行速度较慢。

### 独立编址
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210612172004437.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

- ==优点==：输入/输出指令与存储器指令有明显区别，程序编制清晰，便于理解。

- ==缺点==：输入/输出指令少，一般只能对端口送操作，尤其需要CPU提供存储器读/写两组控制信号，增加了控制的复杂性。


## IO 接口的类型
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210612173827423.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
# 总结
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210612173922450.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

