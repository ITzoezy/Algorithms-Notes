## 给定一个字符串 s ，你需要反转字符串中每个单词的字符顺序，同时仍保留空格和单词的初始顺序。
```java
class Solution {
    public String reverseWords(String s) {
         // 结果集数组
        char[] chars = s.toCharArray();
        int left = 0;
        for (int i = 0; i < s.length(); i++) {
            // 当前操作的字母
            char currentChar = s.charAt(i);
            if (currentChar == ' ') {
                reverse(chars, left, i - 1);
                // 下一个单词的起始坐标
                left = i + 1;
            } else if (i == s.length() - 1) {
                reverse(chars, left, i);
            }
        }

        return String.valueOf(chars);
    }
     private static void reverse(char[] chars, int start, int end){
        while (start < end) {
            char temp = chars[start];
            chars[start] = chars[end];
            chars[end] = temp;
            end --;
            start ++;
        }
    }
}
```