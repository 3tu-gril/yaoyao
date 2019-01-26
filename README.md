28：implement strStr(),这里strStr()是一个函数，意思是在str1里面找str2，若找到，则返回位置，若是没找到，则返回null,可以采用kmp算法，和暴力循环来做）
（思路1  从haystack的第一个位置，开始逐个判断是不是子串。如果整个子串都匹配了，那么就返回，否则继续往下挪位置，注意要看，haystack剩余的长度跟needle比足不足够多，不够的话也就不用往后比了）
public class t0104 {
public static int strStr(String haystack, String needle) {
        int m = haystack.length();
        int n = needle.length();
        for(int i = 0 ;i<=m-n;i++){
        	int j;
        	for(j=0;j<n;j++){
        		if(haystack.charAt(i+j) != needle.charAt(j))
        			break;
        	}
        	if(j==n)
        		return i;
        }
        return -1;
    }
public static void main(String [] args){
	String haystack = "hello";
	String needle = "ll";
	System.out.print(strStr(haystack,needle));
}
}


