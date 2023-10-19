## set
> 与之前的序列式容器相比，关联式容器更注重数据的快速查询能力，这一类成员在初始化的时候一般都是排好序的，set在插入时，如果已经有值了，那当前值是不能被插入。

- 无重复元素：std::set 中的元素是唯一的，不允许重复。

- 元素自动排序：std::set 中的元素默认按照严格弱排序的方式进行排列。这意味着元素将按照其自身的 < 运算符进行排序，或者通过传入的比较函数对象进行排序。

- 高效查找：由于内部实现使用红黑树，std::set 提供了高效的查找操作。插入、删除和查找元素的平均时间复杂度为 O(log n)。

- 迭代器支持：std::set 提供了正向迭代器和反向迭代器，可以方便地遍历集合中的元素。

- 动态修改集合：可以在运行时添加、删除元素，并且集合会自动维护有序性质。


**set和map的底层数据结构都是rb tree 即动态平衡树，且为二叉排序树**
``` c++
#include <iostream>
#include <set>
#include <string.h>
#include <cstring>


using namespace std;

/*
class Student{
public:
    explicit Student(const string name,int age)
        :name(name),age(age){

    }
    bool operator<(const Student& s) const
    {
        return age < s.age;
    }
    friend std::ostream& operator<<(std::ostream& os, const Student& obj) {
            os<<"name:"<<obj.name.c_str()<<"age:"<<obj.age<<endl;
            return os;
        }
private:
    int age;
    string name;

};

int main(){

    Student s1("whfan",28),s2("ajp",27),s3("ajf",32);
    set<Student> s;
    s.insert(s1);
    s.insert(s2);
    s.insert(s3);

    auto it = s.begin();
    while(it != s.end()){
        cout<<*it<<endl;
        ++it;
    }


    return 0;
}
*/

int main(){
    int arr[]={1,6,2,8,9,7,25,36,6};
    set<int> s;
    for(int i = 0; i < sizeof(arr)/sizeof(int);i++){
        s.insert(arr[i]);
    }
    auto it = s.begin();
    while(it != s.end()){
        cout<<(*it)<<endl;
        ++it;
    }
    //打印之后，数据默认被排序了，从小到大排序

    //求某个值的个数,返回值只能是0或者1
    cout<<s.count(100)<<endl;

    //lower_bound(): 这个函数返回一个迭代器，指向第一个不小于（大于等于）给定值的元素。如果指定的值存在于集合中，则返回指向该元素的迭代器；否则，返回指向第一个大于该值的元素的迭代器。

    //upper_bound(): 这个函数返回一个迭代器，指向第一个大于给定值的元素。无论指定的值是否存在于集合中，它总是返回指向第一个大于该值的元素的迭代器。


    //是根据排序后的结果进行输出
    cout<<"lower_bound:"<<*s.lower_bound(2)<<endl;

    cout<<"upper_bound:"<<*s.upper_bound(2)<<endl;
    return 0;
}


```