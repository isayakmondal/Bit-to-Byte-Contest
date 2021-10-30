# Bit to Byte Contest
## _Problem3-NIT and Lucy_


You must be aware of the humanoid robot Lucy developed by NIT few years back. It will be used now for delivering dishes to his customers. The faculty members of NIT started testing Lucy by letting it move on a line.

Initially, Lucy is placed at the coordinate x=X Then, it should execute a sequence of N commands, described by a string S with length N. Each character of this string is either 'L' or 'R', denoting that the robot should walk one step to the left (decreasing x by 1) or to the right (increasing x by 1), respectively.

How many distinct points are visited by the robot when it has executed all the commands? A point p is visited by the robot if p is an integer and the robot's position before or after executing some command is x=p.

#### Input Format
+ The first line of each test case contains two space-separated integers N and X.
+ The second line contains a single string S with length N.

#### Constrains
1≤N≤1001
|X|≤1,000,000
SS contains only characters 'L' and 'R'

#### Output Format

For each test case, print a single line containing one integer ― the number of points visited by Lucy.


#### Sample Input 0



```
6 10
RRLLLL
```

#### Sample Output 0

```
5 
```




# Best Solution:-
```
#include<iostream>
#include<math.h>
using namespace std;
main()
{
        int N, X, min=0, max=0;
        string c;
        cin>>N>>X;
        min=max=X;
        cin>>c;
        for(int i=0; i<N; i++)
        {
            if(c[i]=='L' || c[i]=='l')
            {
                X--;
                if(X<=min)
                    min=X;
            }
            else if(c[i]=='R' || c[i]=='r')
            {
                X++;
                if(X>=max)
                    max=X;
            }
        }
        cout<<max-min+1<<endl;
    return 0;
}
```
[Download Test Cases](#)
