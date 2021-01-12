# GFG-DSA
// STRING 

Form a palindrome 
Medium Accuracy: 43.35% Submissions: 38298 Points: 4
Given a string, find the minimum number of characters to be inserted to convert it to palindrome.
For Example:
ab: Number of insertions required is 1. bab or aba
aa: Number of insertions required is 0. aa
abcd: Number of insertions required is 3. dcbabcd

Input:

The first line of input contains an integer T denoting the number of test cases.
The first line of each test case is S.


Output:

Print the minimum number of characters.

CODE
/*package whatever //do not write package name here */

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		//code
		Scanner sc=new Scanner(System.in);
		int t=sc.nextInt();
		while(t>0){
		    String s=sc.next();
		    int len=s.length();
		    int dp[][]=new int[len][len];
		    for(int i=0;i<len;i++){
		        for(int j=0;j<len;j++){
		            dp[i][j]=-1;
		        }
		    }
		     int res= pal(s,0,len-1,dp);
		     System.out.print(res);
		      System.out.println();
		    t--;
		}
	}
	static int	pal(String s,int i,int j,int dp[][]){
		      if(i>j)
		      return 0;
		      if(dp[i][j]!=-1)
		          return dp[i][j];
		      if(s.charAt(i)==s.charAt(j))
		      {dp[i][j]=pal(s,i+1,j-1,dp);
		      return dp[i][j];
		      }
		      else{
		          int d1=1+pal(s,i+1,j,dp);
		          int d2=1+pal(s,i,j-1,dp);
		      dp[i][j]=Math.min(d1,d2);
		      return dp[i][j];
		      }
		}
		
	
}
