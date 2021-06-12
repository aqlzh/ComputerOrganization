> 一研为定，万山无阻！

@[toc]
# CPU的功能
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517165429851.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
 - ==指令控制==，完成取指令、分析指令和执行指令的操作，即程序的顺序控制。
 - ==操作控制==，一条指令的功能往往是由若干操作信号的组合来实现的。CPU管理并产生由内存取出的每条指令的操作信号，把各种操作信号送往相应的部件，从而控制这些部件按指令的要求进行动作。
 - ==时间控制==，对各种操作加以时间上的控制。时间控制要为每条指令按时间顺序提供应有的控制信号。
 - ==数据加工==，对数据进行算术和逻辑运算。
 - ==中断处理==，对计算机运行过程中出现的异常情况和特殊请求进行处理。

## 运算器控制器功能
![在这里插入图片描述](https://img-blog.csdnimg.cn/202105171710055.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

对数据进行加工（第二章已学 ）

# CPU的结构
- 组合逻辑 ALU
- 时序逻辑 CU
- 寄存器
- 中断系统
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517211754711.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)


# 运算器基本结构
## 基本构成
- 算术逻辑单元 ：  主要功能是进行算术/逻辑运算。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517192145553.png)

- 通用寄存器组：如AX、BX、CX、DX、SP等，用于存放操作数（包括源操作数、目的操作数及中间结果）和各种地址信息等。SP是堆栈指针，用于指示栈顶的地址。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517192158162.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
- `AH ,AL`   H为 high  高，L 为 low 低的意思


## 专用数据通路方式
- 专用数据通路方式：根据指令执行过程中的数据和地址的流动方向安排连接线路。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517192502142.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

- 如果直接用导线连接，相当于多个寄存器，同时并且一直向ALU传输数据每个都与 ALU 相连会发生问题，同时进行数据传输时，不知道数据为那个

### 多路选择器
**解决方法**：

- 使用多路选择器，根据控制信号选择一路输出（如下图）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517192902844.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

### 三态门
- 可以控制每一路是否输出（如下图）
如： ROut为1时R0中的数据输出到A端，ROut为0时R0中的数据无法输出到B端。
![在这里插入图片描述](https://img-blog.csdnimg.cn/202105171933091.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

==缺点==：性能较高，基本不存在数据冲突现象，但结构复杂，硬件量大，不易实现。

## 内部单总线方式
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517193847829.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

- 暂存寄存器：用于暂存从主存读来的数据，这个数据不能存放在通用寄存器中，否则会破坏其原有内容。
- ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517194041957.png)


==缺点==： 结构简单，容易实现，但数据传输存在，较多冲突的现象，性能较低。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517194138783.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
## 运算器功能拓展
- 暂存寄存器
- 移位寄存器 : 对运算结果进行移位运算
- 累加寄存器 ：它是一个通用寄存器，用于暂时存放ALU运算的结果信息，用于实现加法运算。
- 程序状态字寄存器：保留由算术逻辑运算指令或测试指令的结果而建立的各种状态信息，如溢出标志（OP）、符号标志（SF）、零标志（ZF）、进位标志（CF）等。PSW中的这些位参与并决定微操作的形成。

计数器：控制乘除运算的操作步数。

# 控制器的基本功能

- 基本功能： 取指令，分析指令，执行指令

## 各类器介绍

 - `程序计数器（PC）`: 用于指出下一条指令在主存中的存放地址。CPU就是根据PC的内容去主存中取指令的。因程序中指令（通常）是顺序执行的，所以PC有自增。
 - `指令计数器 （IR）` 用于保存当前正在执行的那条指令。
 - `指令译码器（ID）`：仅对操作码字段进行译码，向控制器提供特定的操作信号。
 - `微操作信号发生器`：根据IR的内容（指令）、PSW的内容（状态信息）及时序信号，产生控制整个计算机系统所需的各种控制信号，其结构有组合逻辑型和存储逻辑型两种。
 - `时序系统`：用于产生各种时序信号，它们都是由统一时钟（ CLOCK）分频得到
 - `存储器地址寄存器`：用于存放所要访问的主存单元的地址。
 - `存储器数据寄存器`：用于存放向主存写入的信息或从主存中读出的信息。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517210906242.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

## 全局图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517210959785.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
## 寄存器分类
可以分为用户可以使用（可见）与用户不可以使用

- 用户可见（下图红色标注），可以进行编程
- 用户不可见（透明），不能使用，为硬件方便而存在

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517211549715.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

# 总结
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021051721195187.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

