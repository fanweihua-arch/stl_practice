# deque

**基础数据结构:** ```双端队列，在底层数据结构上，和vector一样，但又比vector复杂，双端队列的底层数据结构是多个定长数组用链表链接起来的一种数据结构```
```c++
#include <QCoreApplication>
#include <iostream>
#include <list>
#include <vector>
#include <deque>
int main(int argc, char *argv[])
{
    QCoreApplication a(argc, argv);

    std::deque<int> d;
    for(int i = 0; i < 10;i++){
        if(i % 2 == 0){
            d.push_back(i);
        }else{
            d.push_front(i);
        }
    }
    std::deque<int>::iterator it = d.begin();
    while(it != d.end()){
        std::cout<<*it<<std::endl;
        ++it;
    }

    //随机访问
    std::cout<<"d[5]:"<<d[5]<<std::endl;

    std::cout<<"d.at(5)"<<d.at(5)<<std::endl;
    return a.exec();

}

```

**双端队列没有容量的说法**