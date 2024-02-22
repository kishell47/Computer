# 文件的物理结构/文件的分配方式(上)



## 01 知识总览

*  [03 计算机系统的层次结构 240220](..\..\01 知识卡片\01 已归档\03 计算机系统的层次结构 240220) 

*   [09 文件物理结构 文件分配方式 240221](..\..\01 知识卡片\01 已归档\09 文件物理结构 文件分配方式 240221) 

### 01 文件物理结构

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202402210917224.png" alt="02 文件物理结构 文件分配方式" style="zoom:50%;" />



### 02 文件的物理结构/文件的分配方式(上) 知识总览

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202402210843478.png" alt="image-20240221084308249" style="zoom:50%;" />



## 02 文件块 磁盘块



### 01 内存分页/分页存储

*  [01 基础视频 基本分页存储管理的基本概念 240221](..\..\03 第三章 内存管理大题\01 基础视频 基本分页存储管理的基本概念 240221) 

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202402211054880.png" alt="image-20240221105446493" style="zoom:50%;" />



### 02 文件块 磁盘块



#### 01 磁盘块 扇区

*  [10 磁盘块 扇区 240221](..\..\01 知识卡片\01 已归档\10 磁盘块 扇区 240221) 

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202402211502667.png" alt="01 磁盘块 扇区" style="zoom:50%;" />

#### 02 文件块 磁盘块



##### 01 磁盘分块 磁盘块

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202402212047454.png" alt="image-20240221204753246" style="zoom:50%;" />



##### 02 磁盘的磁盘块大小=内存的内存块大小=进程的页面大小的好处

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202402212050179.png" alt="image-20240221205052058" style="zoom:50%;" />

##### 03 外存管理 文件逻辑地址空间分块 文件块

* 01 外存管理 文件逻辑地址空间分块 文件块
* 02 进程的逻辑地址 文件的逻辑地址
* 03 文件块大小=物理块大小

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202402212135506.png" alt="image-20240221213553375" style="zoom:50%;" />

##### 04 文件块 VS 磁盘块



##### 05 进程为什么需要在逻辑上划分为一个个等大的页/页面

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202402220916611.png" alt="image-20240222091653406" style="zoom:50%;" />
