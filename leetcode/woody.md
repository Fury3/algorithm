>答案示例

**132. 分割回文串 II**  
---
[https://leetcode-cn.com/problems/palindrome-partitioning-ii/](https://leetcode-cn.com/problems/palindrome-partitioning-ii/) 

摘要  

本文适用于初学者。  


```java  

class Solution {
    	public int minCut(String s) {
        int[][] dp=new int[s.length()][s.length()];
        int[] count=new int[s.length()+1];
        for(int i=s.length()-1;i>=0;i--){
            count[i]=Integer.MAX_VALUE;
            for(int j=i;j<s.length();j++){
                if(s.charAt(i)==s.charAt(j)&&(j-i<2||dp[i+1][j-1]==1)){
                	dp[i][j]=1;
                	count[i]=Math.min(1+count[j+1],count[i]);
                }
            }
        }
        return count[0]-1;       
    }
}
```  

   

---


**参考资料**  

* 本题leetCode官方题解：  


* 本题leetCode英文官方题解：  
