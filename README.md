# C-p43-4-
C语言学习笔记 p43 指针笔试面试题详解(4)
#include<stdio.h>
int main()
{
    int aa[2][5]={1,2,3,4,5,6,7,8,9,10};
    int* ptr1=(int*)(&aa+1);
    int* ptr2=(int*)(*(aa+1));
    printf("%d%d",*(ptr1-1),*(ptr2-1));
    return 0;
}//输出为10，5

int main()
{
    int arr[10]={1,2,3,4,5};
    int* p=arr;
    *(p+2)==p[2]==>*(arr+2)==arr[2];//arr[2]
    arr[2];//==>*(arr+2)
    return 0;
}

int main()
{
    char* a[]={"work","at","alibaba"};//这里是一个指针数组，有3个元素分别存3个元素的首字母
    char** pa=a;//char*说明他是一个char*的变量，*pa说明他是一个指针
    pa++;//pa++说明他跳过一个char*，所以就指向第二个元素的a，解引用打印at
    printf("%s\n",*pa);
    return 0;
}//输出at

int main()
{
    char* c[]={"ENTER","NEW","POINT","FIRST"};
    char** cp[]={c+3,c+2,c+1,c};
    char***cpp=cp;
    printf("%s\n",**++cpp);//POINT
    printf("%s\n",*--*++cpp+3);//ER
    printf("%s\n",*cpp[-2]+3);//ST
    printf("%s\n",cpp[-1][-1]+1);//EW 代码等价于*(*(cpp-1)-1)+1
    return 0;
}
