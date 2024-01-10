# 基本分页存储管理



## 01 基本分页存储管理的基本概念



### 01 分页存储

![image-20240106153313135](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202401061533546.png)



### 02 页表

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202401081040745.png" alt="image-20240108104000579" style="zoom: 40%;" />

### 03 计算页表占多少字节内存空间

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202401101109849.png" alt="03 计算页表占多少字节内存空间" style="zoom: 33%;" />



### 04 如何实现地址转换

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202401101428941.png" alt="image-20240110142803532" style="zoom:50%;" />



#### 04_1 子问题：如何确定一个逻辑地址对应的页号、页内偏移量

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202401101111889.png" alt="image-20240110111159748" style="zoom:50%;" />