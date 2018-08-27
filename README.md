# Hackerearth_Basic_Programing
Hackerearth Basic Programing question answer in different languages to help others understand the different execution of different language  

## Basic Programming

### 1 Input/Output 
#### Basics of Input/Output
 
##### Problem - [Seating Arrangment](https://www.hackerearth.com/practice/basic-programming/input-output/basics-of-input-output/practice-problems/algorithm/seating-arrangement-1/)

`C++`

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

`R`

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

