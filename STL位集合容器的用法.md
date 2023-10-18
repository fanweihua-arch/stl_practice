## bitset
> bitset是针对二进制流来处理的，比如10，0b 0000 1010,bitset不支持越界操作，操作会返回异常

```c++
#include <iostream>
#include <bitset>
using namespace std;
int main(){
    //定义一个10bit的数据，并输出
    bitset<10> bt;
    cout<<"bt:"<<bt<<endl;
    //输出bt所占的小bit的个数
    cout<<"bt size"<<bt.size()<<endl;
    //统计所有的1的个数
    cout<<"bt count"<<bt.count()<<endl;
    //赋值为1
    bt[1] = 1; //等价于bt.set(1) 给1bit处设置1,bt.set(1,0)给第一bit置为0

    bt[2] = 0;
    cout<<"bt count"<<bt.count()<<endl;
    //对各个位按位取反
    bt.flip();
    cout<<"bt:"<<bt<<endl;
    cout<<"bt count"<<bt.count()<<endl;
    //判断是否存在为1的bit 返回1或者0
    cout<<"bt.none()"<<bt.none()<<endl;

    //测试某一位，如果是1返回1如果是0返回0
    cout<<"bt.test(2)"<<bt.test(2)<<endl;
    //全部置为0或者将某位置零
    bt.reset();


    //假设存在一个数，
    int a = 10; // 1010
    a = ~a;     // 0101 = 5
    std::cout<<a<<endl; //-11 ?????

    //针对一个二进制数1010 由于其最高位(符号位为1)，表示其为一个负数，根据二进制补码表示法，
    // 求取源码(按位取反+1) 0101 取反 1010 + 1 = 1011 = (8+2+1) = 11 加符号位 = -11

    //左移补位 右移补位 <<= >>=

    bitset<10> left;
    left>>=5;   //left右移5位并部位

    return 0;
}

```