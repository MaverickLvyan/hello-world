#include<iostream>
#include<cstdlib>
#include<cmath>
#include<iomanip>
using namespace std;
class Calculate
{
public:
     void func(double a,double b);
};
 
class Add:public Calculate
{
public:
    double func(double a,double b)
    {
        return a+b;
    }
};
 
class Reduce:public Calculate
{
public:
    double func(double a,double b)
    {
        return a-b;
    }
};
 
class Ride:public Calculate
{
public:
    double func(double a,double b)
    {
        return a*b;
    }
};
 
class Div:public Calculate
{
public:
    double func(double a,double b)
    {
        if(b!=0)
            return a/b;
        else
            cout<<"输入错误"<<endl;
    }
};
 
class Mod:public Calculate
{
public:
    double func(double a,double b)
    {
        return (int)a%(int)b;
    }
};
//十进制转换二进制
void shizhuaner(double n)
{
	int i=0,j,m,m1,m2=0,a[100],n0;
	int b0[100],b=0,b1,n2;
	double n1,n3=0,n4;
	n0=(n*10)/10;//整数 
	n1=n-n0;//小数 
	while(n1!=0)
	{
		n1=n1*2;	
		n2=n1*10/10;
		b0[b++]=n2;
		n1=n1-n2;
	
	} 
	n4=b-1;
	b1=b;
	for(b=0;b<b1;b++)
	{
		if(n4>=0)
		{
		n3+=b0[b]*pow(10.0,n4--);
	   }
	   else break;
	}
	n3=n3*pow(0.1,b);
	j=n0%2; 
    while((j==1)||(j==0)){
 	    a[i++]=j;
    	n0=n0/2;
    	if(n0!=0){j=n0%2;	}
		else break;
     }
    m=i-1; m1=m;
    for(;m>=0;m--){
       if(m1>=0){
       	m2+=a[m]*pow(10.0,m1--);
       }
    }
    double m4=m2+n3;
    cout<<"转换成二进制是："<<setiosflags(ios::fixed)<<setprecision(5) <<m4; 
    cout<<endl;  
} 
int main()
{
    double a,b;
	double k;
    char operator1;
    int q=1; 
    while(q)
    {
    	cout<<"请输入三个参数，十进制数值a，运算符c ，十进制数值b"<<endl;
        cin>>a>>operator1>>b;
        switch(operator1)
        {
        case '+':
                {Add Over;cout<<a<<"+"<<b<<"="<<Over.func(a,b)<<endl; 
				k=a+b;
				char c;
				cout<<"是否转换成二进制？y/n"<<endl;
				cin>>c;
				if(c=='y'){
				shizhuaner(k);}}break;
        case '-':
                { Reduce Over;cout<<a<<"-"<<b<<"="<<Over.func(a,b)<<endl;
                k=a+b;
				char c;
				cout<<"是否转换成二进制？y/n"<<endl;
				cin>>c;
				if(c=='y'){
				shizhuaner(k);}}break;
        case '*':
                {Ride Over;cout<<a<<"*"<<b<<"="<<Over.func(a,b)<<endl;
				k=a+b;
				char c;
				cout<<"是否转换成二进制？y/n"<<endl;
				cin>>c;
				if(c=='y'){
				shizhuaner(k);}}break;
        case '/':
                {Div Over;cout<<a<<"/"<<b<<"="<<Over.func(a,b)<<endl;
				k=a+b;
				char c;
				cout<<"是否转换成二进制？y/n"<<endl;
				cin>>c;
				if(c=='y'){
				shizhuaner(k);}}break;
        case '%':
               {Mod Over; cout<<a<<"%"<<b<<"="<<Over.func(a,b)<<endl;
			   k=a+b;
				char c;
				cout<<"是否转换成二进制？y/n"<<endl;
				cin>>c;
				if(c=='y'){
				shizhuaner(k);}}break;
            default: cout<<"输入有误！"<<endl;
        }
         cout<<"输入1继续，输入0退出"<<endl;
         cin>>q;
         system("CLS");
    }
    return 0;
}
