# 基本分页存储管理的基本概念



# 知识总览

![image-20230726092808949](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307260928149.png)



# 1 什么是“地址空间”

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307211457892.png" alt="image-20230721145730731" style="zoom:50%;" /> 



# 2 什么是分页存储

![image-20230726103340940](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307261033301.png)



# 3 重要的数据结构——页表

![image-20230726104449582](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307261044819.png)



## 3.1 问题一 每个页表项占多少字节?

![](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307241125037.png)



## 3.2 问题二: 如何实现地址的转换

![image-20230724121500790](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307241215951.png)



### 3.2.1 子问题: 如何确定一个逻辑地址对应的页号、页内偏移量?

![image-20230724143903048](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307241439278.png)

![image-20230724145453541](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307241454695.png)



## 3.3 子问题：为何页面大小要取2的整数幂？

![image-20230724151024792](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307241510969.png)



# 4 逻辑地址结构

![image-20230724152233406](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307241522573.png)



# 5 知识回顾与重要考点

![image-20230724153700844](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307241537944.png)
