> 一研为定，万山无阻

@[toc]

# 解决问题
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021051216214597.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
# 局部性原理
**时间局部性**：在最近的未来要用到的信息，很可能是现在正在使用的信息。

**空间局部性**：在最近的未来要用到的信息（指令和数据）很可能与现在正在使用的信息在存储空间上是邻近的。

# Cache 的工作原理
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210512162753444.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)


==注意==：
1、 M >> C ,因为主存容量远远大于缓存容量
2、标记块用于说明 主存块与Cache块的对应关系（如果主存中有块写进Cache 中，则在Cache 进行标记是否保存）
3、两者的块内地址是相同的

## 命中与未命中
- ==命中== ： 主存块调入缓存，主存块与缓存块建立了对应关系，用标记记录与某缓存块建立了对应关系的主存块号。

- ==未命中== ：  主存块未调入缓存，主存块与缓存块未建立对应关系。

## Cache 的命中率
- CPU欲访问的信息在 Cache中的比率 
- 设一个程序执行期间， Cache的总命中次数为N，访问主
存的总次数为Nm，则命中率 H = $${ \frac { Nc } { Nc + Nm }}$$

### 命中率的相关性

- 命中率与 Cache的==容量==与==块长==有关

**块长的大小** ：
- ==过小== ：一段时间后，块内信息会被用光，则需要到主存当中读，没有充分利用局部性原理，命中率降低
- ==过大==  ： 由于容量有限，则导致块数较小， 则大快长内部分信息有用，则需要到主存中读取，命中率降低
- ---

一般每块可取4~8个字，块长取一个存取周期内从主存调出的信息长度


# 性能分析
## Cache 与主存储系统效率
- 并行情况下
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513083709573.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
==注意==： 上述平均访问时间的计算

- `数据带宽 = 数据量 / 平均访问时间`

## 例题
- 并行
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513084953848.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
- 非并行
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513085221493.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
# 总结
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513085241101.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
# Cache 工作原理
预测策略
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513090346788.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513090726902.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
# 地址映射方式（重要）
## 主存中的块放于Cache的位置
(1)   ==空位随意放==：全相联映射
(1)   ==对号入座==：直接映射
(3)   ==按号分组，组内随意放==：组相联映射

### 直接映射
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513094458385.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
==映射关系==： 每个主存块只能和一个缓存对应，一个缓存块可以与多个主存块对应。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513103849961.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)


- `j`   cache 的块号
- `i`   主存的块号
- `c`   cache  的总的块号


### 全相联映射
- 与上面的直接映射思路正好相反，是另外的一个极端
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513104205134.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
### 组相连映射
以上两种方式的折中处理策略

- ==组间直接映射，组内全相连映射==
- 即为，主存储器的数据只能放在==特定组==内，但是可以在该组的==任意位置==
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513104744704.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513105724158.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
上述图为 2 - 路组相连映射

- `j`   cache 的组号
- `i`   主存的块号
- `Q`  为 Cache  的组数

## 总结
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513112149610.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)

## 例题
### 地址映射
#### 直接映射
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513164317776.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)


#### 全相连映射
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210513162512790.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)
#### 组相联映射
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021051316344754.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1F1YW50dW1Zb3U=,size_16,color_FFFFFF,t_70)




