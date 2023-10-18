# stl_practice
关于STL标准模板库的知识积累

## list
**底层数据结构：** ```带头节点的双向循环列表```\
**begin:** ```迭代器返回第一个数据节点```\
**end:** ```返回最后一个数据节点的下一个节点```\
**push_back/push_front:** ``` 尾部插入/头部插入 无返回```\
**pop_back/pop_front:** ``` 尾部删除/头部删除 无返回``` \
**max_size:** ```表示当前系统最多可以存储多少个节点```
**empty:** ```表示当前节点是否为空```
**front/back:** ```返回第一个节点的引用/返回最后一个节点的引用```
**assign:** ```赋值函数，可以将N个number赋值给list,赋值是覆盖式的，会删除之前的节点，重新开辟```
```c++
#include <iostream>
#include <list>
int main(){
    std::list<int> myList(10,1);
    std::list<int> youList;
    //通过迭代器赋值
    youList.assign(myList.begin(),myList.end());
	for(auto i = youList.begin(); i != youList.end();i++){
		std::cout<<"--->"<<*i;
	}
    return 0;
}
```
**insert:** ```插入元素，在迭代器所指向对象的前部插入```
**erase:** ```删除元素，删除当前迭代器所指向的元素，可以根据迭代器的区间进行区间删除```
**clear:** ```清除元素```
```c++
#include <iostream>
#include <list>
int main(){
	std::list<int> array(10,2);
	array.clear();
	//size是0
	std::cout<<array.size()<<std::endl;
	return 0;
}
```
**swap:** ```交换两个list的内容```
**reverse:** ```逆转方法，将list内容倒置```
**sort:** ```按照升序的方式排序```
**unique:** ```去重函数，比较前一个和后一个是否重合，重合则删除一个```
**remove_if:** ```条件删除，和仿函数有关系```
**splice:** ```拼接，是将某个list或者元素拼接到当前list的前边，原来的list就不存在了```
**merge:** ```合并list，合并是往尾部合并，合并之后的原先的列表就被删除了```

**常方法是应对常对象来做的适配，一般方法是对一般的对象的适配，list的迭代器分为正向迭代器和反向迭代器**





