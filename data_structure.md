## 一、链表

### 1. 单链表

各元素之间通过一个指针彼此链接，每个元素包含两部分：数据成员和一个称为next的指针。最后一个元素的next置空。

抽象数据类型：

```c
/* Define a structure for linked list elements. */
typedef struct ListElmt_
{
    void *data;
  	struct ListElmt_ *next;
} ListElmt;

/* Define a structure for linked lists. */
typedef struct list_
{
    int size;
  	/* match函数并不是由链表自身使用，而是由链表派生而来的新类型所使用　*/
  	int (*match)(const void *key1, const void *key2);
  	/* destroy是封装之后传递给list_init函数的析构函数 */
  	void (*destroy)(void *data);
  	ListElmt *head;
  	ListElmt *head;
} List;
```

