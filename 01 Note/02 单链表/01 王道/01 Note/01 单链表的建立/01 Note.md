# 1 知识总览

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307011557192.png" alt="image-20230701155749100" style="zoom: 67%;" />

* 有很多数据元素（ElemType），把他们存放在一个单链表中
  * step 1：初始化一个单链表
  * step 2：每次取一个数据元素，插入到表尾/表头



# 2 尾插法建立单链表



## 2.1 初始化单链表

* ~~~C++
  typedef struct LNode{	//定义单链表结点类型
      ElemType data;		//每个结点存放一个数据元素
      struct LNode *next;	//指针指向下一个结点
  }LNode, *LinkList;
  
  //初始化一个单链表(带头结点)
  bool InitList(LinkList &L){
      L=(LNode *)malloc(sizeof(LNode));	//分配一个头结点
      if(L==NULL)		//内存不足，分配失败
          return false;
      L->next = NULL;	//头结点之后暂时还没有结点
      return true;
  }
  void test(){
      LinkList L;	//声明一个指向单链表的指针
      //初始化一个空表
      InitList(L);
      //……后续代码……
  }
  ~~~



### 2.1.1 图解初始化单链表

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307041527473.png" alt="image-20230704152747374" style="zoom:200%;" />



## 2.2 在第i个位置插入元素e（带头结点）

* ~~~C++
  bool ListInsert(LinkList &L, int i, ElemType e){
      if(i<1)
          return false;
      LNode *p; //指针p指向当前扫描到的结点
      int j=0;  //当前p指向的是第几个结点
      p = L;    //L指向头结点，头结点是第0个结点(不存数据)
      while(p!=NULL && j<i-1){	//循环找到第i-1个结点
          p=p->next;
          j++;
      }
      if(p==NULL)	//i值不合法
          return false;
      LNode *s = (LNode *)malloc(sizeof(LNode));
      s->data = e;
      s->next=p->next;
      p->next=s;	//将结点s连到p之后
      return true;
  }
  ~~~

  * `i=0`：在头结点处插入，返回`false`



### 2.2.1 图解在第i个位置插入元素e(带头结点)

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307041723526.png" alt="image-20230704172302306" style="zoom:200%;" />



## 2.3  尾插法建立单链表 -- 伪代码

* ~~~pascal
  尾插法建立单链表：
  
  初始化单链表
  
  设置变量length记录链表长度
  
  while 循环{
  	每次取一个数据元素e;
  	ListInsert(L,length+1,e); //插到尾部
  	length++;
  }
  ~~~



### 2.3.1 图解尾插法建立单链表 -- 伪代码

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307041842705.png" alt="image-20230704184247624" style="zoom: 67%;" />



## 2.4 尾插法建立单链表的时间复杂度——O（n^2^)

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307041927883.png" alt="image-20230704192703809" style="zoom:80%;" />



## 2.5 设置表尾指针 后插操作：在p结点之后插入元素e



### 2.5.1 后插操作：在p结点之后插入元素e

* ~~~C++
  //后插操作：在p结点之后插入元素e
  bool InsertNextNode(LNode *p, ElemType e)
  {
      if(p==NULL)
          return false;
      LNode *s = (LNode *)malloc(sizeof(LNode));
      if(s==NULL)	//内存分配失败
          return false;
      s->data=e;	//用结点s保存数据元素e
      s->next=p->next;
      p->next=s;  //将结点s连到p之后
      return true;
  }
  ~~~



### 2.5.2 图解后插操作：在p结点之后插入元素e

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307061546379.png" alt="image-20230706154629282" style="zoom: 60%;" />



### 2.5.3 设置一个表尾指针

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307061547924.png" alt="image-20230706154715871" style="zoom:50%;" />



### 2.5.4 在尾指针r之后插入数据元素e

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307061552372.png" alt="image-20230706155258256" style="zoom: 60%;" />



## 2.6 尾插法正向建立单链表 设置尾指针——时间复杂度O(n)

* ~~~C++
  LinkList List_TailInsert(LinkList &L){	//正向建立单链表
      int x;	//设ElemType为整型
      L=(LinkList)malloc(sizeof(LNode));	//建立头结点
      LNode *s,*r=L;	//r为表尾指针
      scanf("%d",&x); //输入结点的值
      while(x!=9999){	//输入9999表示结束
          s=(LNode *)malloc(sizeof(LNode));
          s->data=x;
          r->next=s;
          r=s;	//r指向新的表尾结点
          scanf("%d",&x);
      }
      r->next=NULL;	//尾结点指针置空
      return L; 
  }
  ~~~

* 



## 2.6.1  尾插法正向建立单链表 设置尾指针——时间复杂度O(n)

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307061708906.png" alt="image-20230706170855771" style="zoom:150%;" />



# 3 头插法建立单链表



## 3.1 对头结点的后插操作

* ~~~C++
  //后插操作：在p结点之后插入元素e
  bool InsertNextNode(LNode *p,ElemType e)
  {
      if(p==NULL)
          return false;
      LNode *s = (LNode *)malloc(sizeof(LNode));
      if(s==NULL) //内存分配失败
          return false;
      s->data = e; //用结点s保存数据元素e
      s->next=p->next;
      p->next=s;	//将结点s连到p之后
      return true;
  }
  ~~~



## 3.2 图解对头结点的后插操作

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307061725058.png" alt="image-20230706172516991" style="zoom: 60%;" />



## 3.2 头插法逆向建立单链表

* ~~~C++
  初始化单链表
  
  while 循环
  {
      每次取一个数据元素e;
      InsertNextNode(L,e);
  }
  ~~~

* ~~~C++
  LinkList List_HeadInsert(LinkList &L){	//逆向建立单链表
      LNode *s;
      int x;
      L=(LinkList)malloc(sizeof(LNode)); 	//创建头结点
      L->next=NULL;	//初始为空链表
      scanf("%d",&x);	//输入结点的值
      while(x!=9999)	//输入9999表示结束
      {
          s=(LNode*)malloc(sizeof(LNode)); //创建新结点
          s->data=x;
          s->next=L->next;
          L->next=s;	//将新结点插入表中，L为头指针
          scanf("%d",&x);
      }
      return L;
  }
  ~~~

* ~~~C++
  //后插操作：在p结点之后插入元素e
  bool InsertNextNode(LNode *p,ElemType e)
  {
      if(p==NULL)
          return false;
      LNode *s = (LNode *)malloc(sizeof(LNode));
      if(s==NULL)	//内存分配失败
          return false;
      s->data=e;  //用结点s保存数据元素e
      s->next=p->next;
      p->next=s; //将结点s连到p之后
      return true;
  }
  ~~~



## 3.3 图解头插法逆向建立单链表

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307061809276.png" alt="image-20230706180930163" style="zoom:50%;" />





## 3.4 头插法建立单链表，头结点的后插操作，代码复用

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307061742688.png" alt="image-20230706174244587" style="zoom: 50%;" />



## 3.5 头插法重要应用——链表的逆置

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307041418535.png" alt="image-20230704141839310"  />



# 4 头插法逆向链表 尾插法正向链表

* <img src="https://cvp.oss-cn-shanghai.aliyuncs.com/picgo/202307062023982.png" alt="image-20230706202334905" style="zoom: 67%;" />



# 5 知识回顾与重要考点

* 头插法、尾插法：核心就是初始化操作、指定结点的后插操作
* 尾插法：注意设置一个指向表尾结点的指针

* 头插法的重要应用：链表的逆置
