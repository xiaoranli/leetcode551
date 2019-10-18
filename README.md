# 19、leetcode551. 学生出勤记录 I
解法一：
--  
思路：
--
    String提供的方法。   
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/18 12:33
 * @descriptor
 */
public class CheckRecord_551 {
   public static boolean checkRecord(String s) {
        return !s.contains("LLL") && s.indexOf('A') == s.lastIndexOf('A');
    }
    public static void main(String[] args) {
        String s = "PPALLP";
        boolean b = checkRecord(s);
        System.out.println(b);
    }
}
</pre>
解法二：
--  
思路：
--
    用两个变量, 标记A出现的个数和L连续出现的个数。  
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/18 12:33
 * @descriptor
 */
public class CheckRecord_551 {
   public static boolean checkRecord(String s) {
        int aCount = 0,lCount = 0;
        for (char c:s.toCharArray()) {
            if(c == 'A')
                aCount++;
        }
        if(s.contains("LLL"))
            lCount = 3;
        System.out.println(aCount+" "+lCount);
        if(aCount > 1 || lCount > 2)
            return false;
        else
            return true;
    }
    public static void main(String[] args) {
        String s = "PPALLP";
        boolean b = checkRecord1(s);
        System.out.println(b);
    }
}
</pre>
解法三：
--  
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/18 12:33
 * @descriptor
 */
public class CheckRecord_551 {
    public static boolean checkRecord2(String s) {
        int aCount = 0,lCount = 0;
        for (char c:s.toCharArray()) {
            if(c == 'A'){
                if(++aCount == 2)
                    return false;
                lCount = 0;
            }else if(c == 'L'){
                if(++lCount == 3)
                    return false;
            }else{
                lCount = 0;
            }
        }
        return true;
    }
    public static void main(String[] args) {
        String s = "PPALLP";
        boolean b = checkRecord1(s);
        System.out.println(b);
    }
}
</pre>
