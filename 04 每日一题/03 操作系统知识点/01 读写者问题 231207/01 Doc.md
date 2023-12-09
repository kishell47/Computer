# 读写者问题



# 问题描述

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312080848273.png" alt="image-20231208084847405" style="zoom: 33%;" />



# 问题分析

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312080907622.png" alt="image-20231208090752366" style="zoom: 33%;" />



# 如何实现

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312081436167.png" alt="image-20231208143655965" style="zoom: 33%;" />



# 如何实现_1——各个进程对共享文件互斥访问

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312081453203.png" alt="image-20231208145356064" style="zoom: 33%;" />



# 如何实现_2——读者和读者之间可以同时共享文件

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312081600369.png" alt="image-20231208160015021" style="zoom: 33%;" />



# 如何实现_3——解决一气呵成的问题

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312091521247.png" alt="image-20231209152116835" style="zoom: 33%;" />



# 如何实现_4——写进程饿死

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312091541754.png" alt="image-20231209154119290" style="zoom: 33%;" />



# 如何实现_4——解决写进程饿死



# 情况1：两个读者进程并发运行

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312091554819.png" alt="image-20231209155420527" style="zoom: 33%;" />



# 情况2：两个写者进程并发运行

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312091727351.png" alt="image-20231209172728129" style="zoom: 33%;" />



# 情况3：读者写者进程并发运行

<img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202312091737622.png" alt="image-20231209173705383" style="zoom:33%;" />



# 情况4：读者写者读者并发运行

