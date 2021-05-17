> 一研为定，万山无阻！

@[toc]
# 概述
## CISC
- `CISC`: Complex Instruction Set Computer 复杂指令系统计算机
- 设计思路： 一条指令完成一个复杂的基本架构
- 代表： x86 架构，主要用于笔记本、台式机等 
- 80-20规律：典型程序中80%的语句仅仅使用处理机中20%的指令
- 中间过程难以拆分，不利于优化

## RISC

- `RISC`: Reduced Instruction Set Computer 精简指令系统计算机
- 设计思路：一条指令完成一个基本“动作”，多条指令组合完成一个复杂的基本功能。
- 代表：ARM架构，主要用于手机、平板等


==举例==：
 - 比如设计一套能输出单词的指令集：
- **CISC 思路** ： 每个单词的输出由一条指令完成，一条指令可以由一个专门的电路完成：17万个单词=17万个电路，采用“存储程序”的设计思想，由一个比较通用的电路配合存储部件完成一条指令。
- **RISC 思路**：每个字母的输出由一条指令完成，多条指令组合完成一个单词，26个字母=26个电路 “并行”，流水线思想
- 由操作组合而成，易于改变顺序，易于优化


## 两者异同
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517154751310.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
# 本章小结
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210517160326808.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

