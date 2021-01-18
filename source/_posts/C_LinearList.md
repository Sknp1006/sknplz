---
title: 【C数据结构】线性表
date: 2020-07-07 21:07:22
tags: [C语言, 数据结构, 学习]
categories: C语言数据结构
---
## 一、线性表的定义和基本操作
### 1.线性表的定义
线性表是具有 **相同数据类型** 的n(n>=0)个数据元素的 **有限序列** ，其中n为表长，当n=0时，线性表是一个空表。
若用L命名，则其一般表示为 L = (a<sub>1</sub>, a<sub>2</sub>, a<sub>3</sub>, a<sub>4</sub> ... a<sub>n</sub>)

### 2.线性表的特点：
- 表中元素个数有限。
- 表中元素具有逻辑上的顺序结构，有先后次序。
- 表中元素都是数据元素，，每个元素都是单个元素。
- 表中元素的数据类型都相同，每个元素占用相同大小的存储空间。

### 3.线性表的基本操作
- InitList(&L);           //初始化表，空表
- Length(L);              //求表长，返回顺序表的长度 
- LocateElem(L, e);       //按值查找操作，在表L中查找具有给定关键字值的元素 
- GetElem(L, e);          //按位查找，获取L中第e个位置的值 
- ListInsert(&L, i, e);   //插入操作，在L中第i个位置插入指定元素e 
- ListDelete(&L, i, &e);  //删除操作，删除表L中第i个位置的元素，并用e返回删除元素的值 
- PrintList(L);           //输出操作，按前后顺序输出L的所有元素值 
- Empty(L);               //判空操作，若空返回true，否则false 
- DestoryList(&L);        //销毁操作，销毁顺序表L并释放空间

<!-- more -->

## 二、线性表的顺序表示
线性表的顺序表示又称 **顺序表**。
### 1.线性表的实现
```c
typedef struct{
	int data[Maxsize];
	int length;
}Sqlist;

typedef struct{
  int *data;
  int Maxsize, length;
}Sqlist;
L.data = (Elemtype*)malloc(sizeof(ElenType)*InitSize)  // 初始化（C）
L.data = new ElemType(InitSize)  // 初始化（C++）
```
### 2.顺序表的基本操作的实现
```c
#include<stdio.h>
#include<stdbool.h>
#include<malloc.h>

#define Initsize 100
#define Maxsize 50

typedef struct{
	int data[Maxsize];
	int length;
}Sqlist;

//typedef struct{
//	int *data;
//	int Maxsize, length;
//}Sqlist;


Sqlist InitList(Sqlist &L);  //初始化表，空表
int Length(Sqlist L);  //求表长，返回顺序表的长度 
int LocateElem(Sqlist L, int e);  //按值查找操作，在表L中查找具有给定关键字值的元素 
int GetElem(Sqlist L, int e);  //按位查找，获取L中第e个位置的值 
bool ListInsert(Sqlist &L, int i, int e);  //插入操作，在L中第i个位置插入指定元素e 
bool ListDelete(Sqlist &L, int i, int &e);  //删除操作，删除表L中第i个位置的元素，并用e返回删除元素的值 
bool PrintList(Sqlist L);  //输出操作，按前后顺序输出L的所有元素值 
bool Empty(Sqlist L);  //判空操作，若空返回true，否则false 
void DestoryList(Sqlist &L);  //销毁操作，销毁顺序表L并释放空间

Sqlist InitList(Sqlist &L){
	L.data[Maxsize];
	L.length = 0;  //初始为0，如果越界会无法插入 
}


bool ListInsert(Sqlist &L, int i, int e){
	if(i<1 || i>L.length+1)
	    return false;
	if(L.length>=Maxsize)  // 当前长度和总长度之间 
	    return false;
	for(int j=L.length; j>=i; j--)  //向后挪，留出插入的位置 
	    L.data[j] = L.data[j-1];
	L.data[i-1] = e;
	L.length++;
	return true;
}


bool PrintList(Sqlist L){
	if(L.length == 0)
	    return false;
	for(int i=0; i<L.length; i++){
		printf("%d ", L.data[i]);
	}
}

int Length(Sqlist L){
	return L.length;
}


int LocateElem(Sqlist L, int e){
	int i;
	for(i=0; i<L.length; i++)
	    if(L.data[i]==e)
	        return i+1;
    return 0;
}

int GetElem(Sqlist L, int e){
	if(e<1 || e>L.length)  // 不能大于顺序表长度 
	    return -999;
	return L.data[e-1];
}

bool ListDelete(Sqlist &L, int i, int &e){
	if(i<1 || i>L.length)  // 不能大于顺序表长度 
	    return false;
	e = L.data[i-1];
	for(int j=i; j<L.length; j++)
	    L.data[j-1] = L.data[j];
	L.length--;
	return true; 
}

bool Empty(Sqlist L){
	if(L.length == 0)
	    return true;
	return false; 
}

void DestoryList(Sqlist &L){
//	free(L);  //动态分配时使用
    L.length = 0;
    printf("是否为空：%d\n", Empty(L));  // 1 means true
}
```
<details><summary>main函数</summary>

```c
int main(){
	Sqlist L;
	InitList(L);  //修改了L，不用再绑定返回值 
	printf("线性表的地址%p:\n", L);
	int e = 1;
//	printf("%d\n", L.length);  // 0
//	L.data = (int *)malloc(sizeof(int)*Initsize); 动态分配顺序表空间 
    for(int i=1; i<=50; i++){
    	ListInsert(L, i, e);  // 循环插入50次 
		e++;
	}
	PrintList(L);  // 遍历打印L 
	printf("元素个数：%d\n", Length(L));  // 50
	printf("%d\n", LocateElem(L, 5));  // 5在数组的第5号位置
	printf("%d\n", GetElem(L, 45));  // 第45号位置是45 
    ListDelete(L, 10, e);  //用e绑定，稍有违和感 
    printf("%d\n", e);  // 10
    printf("元素个数：%d\n", Length(L));  // 49 
    printf("是否为空：%d\n", Empty(L));  // 0 means false
    DestoryList(L);  // 销毁顺序表 
}
```

</details>

## 三、线性表的链式表示
### 1.单链表的定义
线性表的链式存储又称单链表。它是通过一组任意的存储单元来存储线性表中的数据元素。
为了建立数据元素之间的线性关系，对每个结点，除了存放自身的信息之外，还需要存放一个指向其后继的指针。
```c
typedef struct LNode{
	int data;  // 数据域 
	struct LNode *next;  // 指针域 
}LNode, *LinkList;
```

### 2.单链表上基本操作的实现
```c
#include<stdio.h>
#include<malloc.h>

typedef struct LNode{
	int data;  // 数据域 
	struct LNode *next;  // 指针域 
}LNode, *LinkList;

LinkList List_HeadInsert(LinkList &L);
LinkList List_TailInsert(LinkList &L);
LNode *GetElem(LinkList L, int i);
LNode *LocateElem(LinkList L, int e);


LinkList List_HeadInsert(LinkList &L){  // 逆向建立单链表 
	LNode *s; int x;
	L = (LinkList)malloc(sizeof(LNode));  // 创建头节点，LinkList是指针类型，不用加*
	L->next = NULL;  //初始为空结点
	scanf("输入结点的值: %d", &x);  // 输入结点的值 
	while(x!=9999){
		s = (LNode *)malloc(sizeof(LNode));  // 创建新结点，s为指向LNode的指针 
		s->data = x;  
		s->next = L->next;
		L->next = s;  // 将新结点插入到表中
		scanf("%d", &x);
	}
	return L;
}


LinkList List_TailInsert(LinkList &L){  // 正向建立单链表 
	int x;
	L = (LinkList)malloc(sizeof(LNode));
	LNode *s, *r = L;  // r为尾指针
	scanf("输入结点的值: %d", &x);  // 输入尾结点的值
	while(x!=9999){
		s = (LNode *)malloc(sizeof(LNode));
		s->data = x;
		s->next = s;
		r = s;  // r指向新的尾结点
		scanf("%d", &x); 
	} 
	r->next = NULL;  // 尾结点指向空指针
	return L; 
} 


LNode *GetElem(LinkList L, int i){  // 返回的是一个结点的指针 
	int j = 1;  // 计数，初始为1 
	LNode *p = L->next;  // 头结点赋给p，这是把第一个结点给了p 
	if(i==0){
		return L;  // 若i等于0，返回头头结点 
	}
	if(i<1)
	    return NULL;  // 若i无效，返回NULL 
	while(p&&j<i){  // 从第一个结点开始找，查找到第i个结点， 
		p = p->next;  // p移动到p的下一个位置
		j++;
	}
	return p;  // 返回第i个结点的指针，查找失败时p是NULL 
}


LNode *LocateElem(LinkList L, int e){  // 返回的是一个结点的指针
	LNode *p = L->next;  // p绑定头结点
	while(p!=NULL&&p->data!=e)
	    p = p->next;
	return p;  // 找到返回该指针，找不到返回NULL 
}
```

<details><summary>main函数</summary>

```c

int main(){
	LinkList L;
	LNode *p;
    List_HeadInsert(L);
	p = GetElem(L, 4);
	p = LocateElem(L, 888);
	
	printf("%d", p->data);
} 
```

</details>

## 总结