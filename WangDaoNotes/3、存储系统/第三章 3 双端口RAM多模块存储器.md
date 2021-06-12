@[toc]
# 双端口RAM
- RAM(随机存储器) 
- ROM (只读存储器)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512151431491.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
# 多模块存储器（重要）
## 单体多字存储器
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021051215212785.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)


- ==缺点==： 指令与数据必须**连续存放**

## 多体并行存储器
![在这里插入图片描述](https://img-blog.csdnimg.cn/202105121523570.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
### 高低位交叉编址的多体存储器
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512152850224.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
- 前者（左边） 高位为体号 ， 低位为体内地址

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512153418973.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
 - 时空图为表达流水线的一个重要概念


==**高位交叉编址**==
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512154043558.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
- 由图可以发现 连续取n个存储字 耗时nT (耗时 5T)
 
 - 高位交叉编址相当于==扩容==，对时间没有质的提升


==**高位交叉编址**==

- 因为M0与M1是独立的，所以可以异步进行（访问M1时，不需要等M0访问结束）

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512154720151.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512154900475.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

 耗时 T + (n-1)t 
#### 计算题
==微观==
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512155349519.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021051216044269.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

`m >= T/r`  的原因  有可能再调用 M0 时，其还没工作完。

==宏观==

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512160503114.png)
==补充==：可以并行工作，如总线宽度为mW时，可以同时取出长度为mW的数据。

# 总结
![ ](https://img-blog.csdnimg.cn/20210512160626567.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

