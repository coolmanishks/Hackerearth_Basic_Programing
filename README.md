# Hackerearth_Basic_Programing
Hackerearth Basic Programing question answer in different languages to help others understand the different execution of different language  

## Basic Programming

### 1 Input/Output 
#### Basics of Input/Output
 
##### Problem - [Seating Arrangment](https://www.hackerearth.com/practice/basic-programming/input-output/basics-of-input-output/practice-problems/algorithm/seating-arrangement-1/)

***
`**C++**`

``` C++

//C++
#include <iostream>
using namespace std;
#define lli long long int 
#define MAX(x,y) ((x) > (y) ? (x) : (y))

int main()
{
   int t,s;
   cin>>t; //no of test cases
   int a[] = {-11,11,9,7,5,3,1,-1,-3,-5,-7,-9};
   string b[] = {"WS","WS","MS","AS","AS","MS"};
   while(t--)
   {
       cin>>s; // input seat no 
       int i = s%12;
       cout<<s+a[i]<<" ";
       int j = s%6;
       cout<<b[j]<<"\n";
       
   }
    return 0; 
}

```

**Best Answer**

``` C++

#include<stdio.h>
#include<iostream>
int main()
{
	int s,t,ch;
		scanf("%d",&t);  // t is testcase s is seatno. and ch is choiceside
	for(int i=1;i<=t;i++)
	{
		scanf("%d",&s);
		ch=s%12;
		switch(ch)
		{
			case 0: s=s-11;
					printf("%d WS\n",s);
					break;
			case 1: s=s+11;
					printf("%d WS\n",s);
					break;
			case 2: s=s+9;
					printf("%d MS\n",s);
					break;
			case 11: s=s-9;
					printf("%d MS\n",s);
					break;
			case 3: s=s+7;
					printf("%d AS\n",s);
					break;
			case 10: s=s-7;
	 				printf("%d AS\n",s);
					break;
			case 4: s=s+5;
					printf("%d AS\n",s);
					break;
			case 9: s=s-5;
					printf("%d AS\n",s);
					break;
			case 5: s=s+3;
					printf("%d MS\n",s);
					break;
			case 8: s=s-3;
					printf("%d MS\n",s);
					break;
			case 6: s=s+1;
					printf("%d WS\n",s);
					break;
			case 7: s=s-1;
					printf("%d WS\n",s);
					break;		
			}
	}
	return 0;
}

```
***

`**R**`

``` R

#R
input<-file('stdin', 'r')
test.case <- as.integer(readLines(input, n=1))
while(test.case>0)
{
    test.case = test.case - 1
    seat <- c(-11,11,9,7,5,3,1,-1,-3,-5,-7,-9)
    names(seat) <- c("WS","WS","MS","AS","AS","MS","WS","WS","MS","AS","AS","MS")
    seat.input <- as.integer(readLines(input, n=1))
    s <- seat.input %% 12
    cat(seat.input+seat[s+1],names(seat[s+1]))
    cat("\n")
}

```

**Best Answer**

``` R
#R
lv <-readLines("stdin", n = 1000001L)[-1]
isn<-1:108
osn<-isn+rep(rev(seq.int(-11,11,2)),9)
st<-rep(c("WS","MS","AS","AS","MS","WS"),9)
df<-data.frame(osn,st)
cat(paste(df[lv,1],df[lv,2]),sep = "\n")

```
***

##### Problem - [Prime Number](https://www.hackerearth.com/practice/basic-programming/input-output/basics-of-input-output/practice-problems/algorithm/prime-number-8/)

***
`**C++**`

```C++

#include<bits/stdc++.h>
using namespace std;
int prime(int n) // function to check whether number is prime or not
{
    // returns 0 if not prime
    // returns 1 if number is prime
    int square = sqrt(n);
    if(n%2==0&&n>2)
    return 0;
    else
    for(int i=3;i<=square;i=i+2)
    {
        if(n%i==0)
        return 0;
    }
    return 1;
}
int main()
{
    int p;
    cin>>p;
    if(p<2)
    cout<<0;
    else  
    {
        cout<<2<<" "; // if p is equal to 2 or greater than 2 then it will always as prime number
    for(int i=3;i<=p;i=i+2)
    {
        if(prime(i)) 
        cout<<i<<" ";
    }
    }
    
    return 0;
    
}

```

**Best Answer**

``` C++

#include <iostream>
#include <math.h>
using namespace std;
 
int main(void)
{
    int N;
    int primeCount;
    cin >> N;
    
   
        for (int i = 1; i < N; i++)
        {
            primeCount = 0;
            
            for (int j = 1; j <= i; j++)
            {
                if ( i % j == 0 )
                    primeCount++;
            }
            
            if (primeCount == 2)
                cout << i << " ";
        }
    
    
    return 0;
}

```
***

##### Problem - [Magical Word](https://www.hackerearth.com/practice/basic-programming/input-output/basics-of-input-output/practice-problems/algorithm/magical-word/description/)

***

`**C++**`

```C++

# include<bits/stdc++.h>
using namespace std;
int main()
{
    int t,n;
    string s;
    char a[] = {67,71,73,79,83,89,97,101,103,107,109,113};
    cin>>t;
    while(t--)
    {
        cin>>n;
        cin>>s;
        for(int i=0;i<s.length();i++)
        {
            int m = int(s[i]);
            if(m<67)
            {
                cout<<a[0];
            }
            else if(m>89&&m<94)
            {
                cout<<a[5];
            }
            else if(m>=113)
            {
                cout<<a[11];
            }
            else
            for(int j=0;j<11;j++)
            {
                if(m==a[j])
                {
                    cout<<s[i];
                    break;
                }
                else if(m>a[j]&&m<a[j+1])
               {
                   int d = abs(m-a[j])-abs(m-a[j+1]);
                   //cout<<"s : "<<s[i]<< " "<<" d : "<<d<<" i,j :"<<i<<","<<j<<endl;
                   if(d>0)
                   {
                       cout<<a[j+1];
                       break;
                   }
                   else
                   {
                       cout<<a[j];
                       break;
                   }
                   
                
               }
            }
        }
        cout<<endl;
    }
}

```

**Best Answer**

```C++
#include<iostream>
using namespace std;
int fun(int f)
{
	int i,j=0,k=0;
	static int f1=0;
	if(j==0)
	{
	if(f>=121)
	{
		cout<<"q";f1=0;
		return 0;
	}
	j++;
	}
	for(i=2;i<f;i++)
	{
		if(f%i==0)
		{
			k=1;
			if(f1%2==0)
			{
				f1++;
				return fun(f-f1);
			}
			else if(f1%2!=0)
			{
				f1++;   
				return fun(f+f1);
			}
			break;
		}
	}
	if(k==0)
	cout<<(char)f;
	f1=0;
	return 0;
}
main()
{
	int t,n,s;
	cin>>t;
	char a[10000];
	int i,j=0,k,f;
	for(i=0;i<t;i++)
	{
		cin>>n;                     // ABCD
		j=0;
		while(j<n)
		{
			cin>>a[j];
			f=a[j];
			if(f<65)
			{
				if(f>93 && f<97)
				{
					s=f-97;
					f-=s;
					goto g;
				}
				s=65-f;
				f+=s;	
			}
			g:fun(f);
			j++;
		}
		cout<<endl;
	}
}

```

