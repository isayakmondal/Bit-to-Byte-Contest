# Bit to Byte Contest
## _Problem4-GNIT, JISCE and Strings_


GNIT and JISCE are making news after JIS Group's fabulous performance of students in placement 2021, GNIT decided to celebrate with JISCE at Sydney. GNIT gifted a string of characters, but to his surprise, he received a string of characters from JISCE too, of same length. To decide over their future they consult you to check the percentage match between them. Percentage Match is given by:

###### y= (Number of characters in the string gifted by GNIT that are also present in JISCE's gift)/(Length of the string)*100

They consulted an Astrologist, according to him if percentage match (y) is more than or equal to x then, they are compatible, otherwise not.

#### Input Format
First line contains T, the number of testcases.
Each testcase consists of 4 lines, First line contains N,the length of the two strings.
Next two lines contain GNIT and JISCE's string respectively.
The 4th line contains the minimum compatibility factor.

#### Constrains
1≤T≤10
1≤N(|S1|,|S2|)≤10^6
0≤x≤100
|S1|=|S2|
S1,S2 are in lowercase.

#### Output Format

Output for each testcase will consists of only one line,
Compatible or Incompatible. (output should exactly match, case sensitive) .


#### Sample Input 0



```
3
5
abcde
edcba
50
4
wing
ding
75
4
love
type
50
```

#### Sample Output 0

```
Compatible
Compatible
Incompatible
```

#### Explaination 0
In 2nd Case: The characters in the first string, that are also present in the second string are i,n,g. percentage match: (3/4)*100= 75%,hence compatible.

In 3rd Case: Only 'e' of the first string is present in the second string .percentage match: (1/4)*100= 25%, hence compatible.


# Best Solution:-
The question requires to do simple job,find number of characters of first string which is also present in second string.

To do that,we use the fact that all characters are in lowercase and ranges from a-z.we simply iterate over both the string and store in two 26 sized array(only 26 alphabets in english).

Then we iterate over 26 characters.let A[i] be number of characters of i character present in first string,example A[0] number of characters of 'a' character present on first string.Similarly for second string,B[i].

now if A[i]>0 and B[i]>0,then the number of characters present in first string which is also present in second string (sum) = A[i]+sum. which is iterated over i=0 to 25.

Example: for riig as first string and ixyz as second string,

A[17]=1,A[8]=2,A[6]=1;

B[8]=1,B[23]=1,B[24]=1,B[25]=1.

Hence i is common,so number of characters of first string which is also present in second string =2.(2 i's).
```
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;
public class Solution {
    public static void main(String[] args)
        {
        Scanner sc=new Scanner(System.in);
        int t,n,r,i,x;
        String str1,str2;
        float ans;
        int count1[]=new int[26];
        int count2[]=new int[26];
        t=sc.nextInt();
        while(t!=0)
            {
            n=sc.nextInt();
            str1=sc.next();
            str2=sc.next();
            r=sc.nextInt();
            for(i=0;i<26;i++)
                {
                count1[i]=count2[i]=0;
            }
            for(i=0;i<n;i++)
                {
                count1[str1.charAt(i)-'a']++;
                count2[str2.charAt(i)-'a']++;
            }
            x=0;
            for(i=0;i<26;i++)
                {
                if(count1[i]>0 && count2[i]>0)
                    x+=count1[i];
            }
            ans=(float)x*100;
            ans=ans/n;
            if(ans>=r)
                System.out.println("Compatible");
            else
                System.out.println("Incompatible");
            t--;
        }   
    }
}
```
[Download Test Cases](#)
