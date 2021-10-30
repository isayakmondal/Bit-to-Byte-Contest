# Bit to Byte Contest
## _Problem2-Bit2Byte Triangles_


Bit2Byte is the coding club of GNIT. Coding club mentors of Bit2Byte like the shape of triangle very much. Ofcourse there is reason behind it, that is for a unique set of length of 3 sides of a Triangle, there is only one possible triangle.

Right Triangles are considered Cool in Coding Club, because it is a triangle with a right angle (Don't Argue).
Now Mentors are given two side lengths and wish to know if these two sides belong to any possible cool triangle

NOTE: In a cool triangle all three sides are integers.

#### Input Format
First line contains a single integer T, denoting number of test cases
Next T lines contains two integers (A,B) each denoting to two sides of a triangle.

#### Constrains
T <= 1000

1 <= A, B <= 104

#### Output Format

For each test case output the following on a seperate line:

"yes" or "no"



#### Sample Input 0



```
3
3 5
3 4
2 5
```

#### Sample Output 0

```
yes
yes
no
```

#### Explanation 0

(3,5) and (3,4) can be side of a cool triangle 

while (2,5) cannot.

It is simple, given two sides of a triangle. We either have two non-hypotenuse side or one hypotenuse side and other non-hypotenuse side

If it is case 1: then sum of square of two sides must be a perfect square

If it is case 2: then difference of sum of square of two sides must be a perfect square


# Best Solution:-
```
#include<iostream>
#include<cmath>
using namespace std;
int main()
{
	int testcase;
	cin >> testcase;
	while(testcase--){
		int a,b;
		cin >> a >> b;
		int cc = a*a + b*b;
		int c = sqrt(cc);
		int x = max(a,b);
		int y = min(a,b);
		int dd = x*x - y*y;
		int d = sqrt(dd);
		if(c*c == cc || d*d == dd)
		cout << "yes\n";
		else
		cout << "no\n";
	}
	return 0;
}
```
[Download Test Cases](#)
