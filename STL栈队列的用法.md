## stack_queue

#### 容器适配器
> 容器适配器的意思是对已有的容器的一些特性进行再封装，形成的新的容器，被称之为容器适配器

**栈:** ```先进后出的一种数据结构(FILO)```\
**队列:** ```先进后出的一种数据结构(FIFO)```
> 栈和队列是操作受限制的一种线性结构,适配器本身不提供迭代器操作
```c++
#include <QCoreApplication>
#include <iostream>
#include <stack>
#include <queue>
int main(int argc, char *argv[])
{
    QCoreApplication a(argc, argv);
    std::stack<int> s;
    s.push(1);      //使用双端队列的头插和尾插都可以
    s.push(2);
    s.push(3);
    s.push(4);
    //如何取到出栈的元素
    std::cout<<"s.top():"<<s.top()<<std::endl;
    //拿到元素之后再pop,执行出栈操作
    s.pop();

    //打印栈内部的所有元素
    while(!s.empty()){
        std::cout<<"pop:"<<s.top()<<std::endl;
        s.pop();
    }

    std::queue<int> q;
    q.push(1);
    q.push(2);
    q.push(3);

    while(!q.empty()){
        std::cout<<"q.front()"<<q.front()<<std::endl;
        //最先进去的最先被删除
        q.pop();
    }


    return a.exec();

}

```