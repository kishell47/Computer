# 知识总览

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307070615963.png" alt="image-20230707061559817" style="zoom: 38%;" />

  

# 1 队列的顺序实现（队列的顺序存储）



## 1.1 队列的顺序实现（队列的顺序存储）代码

* ~~~C++
  #define MaxSize 10	//定义队列中元素的最大个数
  typedef struct{
      ElemType data[MaxSize];	//用静态数组存放队列元素
      int front,rear;	//队头指针和队尾指针
  } SqQueue;
  
  void testQueue(){
      SqQueue Q;	//声明一个队列(顺序存储)
      //……后续操作……
  }
  ~~~



## 1.2 图解队列的顺序实现（队列的顺序存储）

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307070725011.png" alt="image-20230707072543772"  />



# 2 队列初始化操作 队列判空操作



## 2.1 队列初始化操作 队列判空操作 代码

~~~C++
#define MaxSize 10	//定义队列中元素的最大个数
typedef struct{
    ElemType data[MaxSize];	//用静态数组存放队列元素
    int front,rear; //队头指针和队尾指针
} SqQueue;

//初始化队列
void InitQueue(SqQueue &Q)
{
    //初始时 队头、队尾指针指向0
    Q.rear=Q.front=0;
}

void testQueue(){
    //声明一个队列(顺序存储)
    SqQueue Q;
    InitQueue(Q);
    //……后续操作……(增删查)
}

//判断队列是否为空
bool QueueEmpty(SqQueue Q){
    if(Q.rear==Q.front)	//队空条件
        return true;
    else
        return false;
}
~~~



## 2.2 队列初始化操作 队列判空操作 图解

* ![image-20230707153335816](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307071533114.png)



# 3 入队操作



## 3.1 入队操作 代码

* ~~~C++
  #define MAxSize 10//定义队列中元素的最大个数
  typedef struct{
      ElemType data[MaxSize]; //用静态数组存放队列元素
      int front,rear; //队头指针和队尾指针
  } SqQueue;
  
  //入队
  bool EnQueue(SqQueue &Q, ElemType x){
      if(队列已满)
          return false;	//队满则报错
      Q.data[Q.rear]=x;   //将x插入队尾
      Q.rear = Q.rear+1;	//队尾指针后移
      return true;
  }
  ~~~



## 3.2 入队操作 图解

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307071102227.png" alt="image-20230707110208064" style="zoom:67%;" />



## 3.2 顺序队列判满操作



### 3.2.1 `rear == MaxSize `   ❌假溢出

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307071135848.png" alt="image-20230707113508703" style="zoom:50%;" />



### 3.2.2 取余解决"假溢出" 



#### 3.2.2.1 取余解决"假溢出" 代码

* ~~~C++
  #define MaxSize 10 //定义队列中元素的最大个数
  typedef struct{
      ElemType data[MaxSize]; //用静态数组存放队列元素
      int float,rear; //队头指针和队尾指针
  } SqQueue;
  
  //入队
  bool EnQueue(SqQueue &Q,ElemType x){
      if(队列已满)
          return false;	//队满则报错
      Q.data[Q.rear]=x;   //新元素插入队尾
      Q.rear=(Q.rear+1)%MaxSize;  //队尾指针加1取模
      return true;
  }
  ~~~



#### 3.2.2.2 取余解决"假溢出" 图解

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307071415010.png" alt="image-20230707141542910" style="zoom:50%;" />



# 4 循环队列



## 4.1 循环队列

* <font color='red'>**用模运算将存储空间在逻辑上变成了”环状“，本质上还是顺序存储**</font>



## 4.2 循环队列代码实现

* ~~~C++
  Q.data[Q.rear]=x;	//新元素插入队尾
  Q.rear=(Q.rear+1)%MaxSize; //队尾指针加1取模
  ~~~



## 4.3 循环队列 队列已满条件

* ![image-20230707154910465](https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307071604984.png)



## 4.4 循环队列 队列判空



### 4.4.1 循环队列 队列判空 代码

* ~~~C++
  bool QueueEmpty(SqQueue Q)
  {
      if(Q.rear==Q.front) //队空条件
  		return true;
      else
          return false;
  }
  ~~~



### 4.4.2 循环队列 队列判空 图解

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307071649159.png" alt="image-20230707164951999" style="zoom:67%;" />



### 4.4.3 循环队列 入队 代码

* ~~~C++
  //入队
  bool EnQueue(SqQueue &Q,ElemType x)
  {
      if((Q.rear+1)%MaxSize==Q.front) //判断队满
          return false; //队满则报错
      Q.data[Q.rear]=x; //新元素插入队尾
      Q.rear=(Q.rear+1)%MaxSize; //队尾指针加1取模
      return true;
  }
  ~~~



### 4.4.4 循环队列 入队 图解

* 
