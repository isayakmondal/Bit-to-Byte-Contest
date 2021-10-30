# Bit to Byte Contest
## _Problem1-GNIT Ranking_



Ayush is a student of GNIT. He scored x marks in his 2nd Semester. He would have been happy if he got a rank in top 10. However, he is busy with his internship at a product based company and asks you to tell his rank. You have to tell if Ayush will be happy or not.

Note: In case of multiple same score, Ayush will be ranked on top of them.

#### Input Format

First line of each test case contains integers (total number of students in his class) and , marks Ayush Scored. Second line of each test case contains integers denoting marks of every individual student.

#### Constrains

20 <= n <= 1000

0 <= marksofstudents <= 109

#### Output Format

A single line output is expected (without quotes),

"Happy", if Ayush got a rank in top 10.

"Not Happy", if Ayush did not get a rank in top 10



#### Sample Input 0



```
23 82
67 398 318 322 40 30 110 340 133 113 51 123 468 235 483 377 32 233 149 455 137 457
```

#### Sample Output 0

```
Not Happy
```

#### Explanation 0

As rank of Ayush would have been 18, therefore we would not have been happy.


# Best Solution:-
```
#include<iostream>
using namespace std;
int main()
{
	int no, marks, rank= 1;
	cin >> no >> marks;
	for(int x=0; x<no; x++){
		int a;
		cin >> a;
		if(a>marks)
		rank++;
	}
	if(rank<=10)
	cout<<"Happy";
	else
	cout<<"Not Happy";
	return 0;
}
```
[Download Test Cases](https://github.com/prithvirajbytes/Bit-to-Byte-Contest/tree/master/Test%20Cases)
