>## Reverse Words in a String III
>```
>Given a string s, reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.
>```
>### Example 1:
>```
>Input: s = "Let's take LeetCode contest"
>Output: "s'teL ekat edoCteeL tsetnoc"
>```
>### Example 2:
>```
>Input: s = "God Ding"
>Output: "doG gniD"
>```
>### Solution `Java`
```
class Solution {
    
    public String reverseWords(String s) {
      
      char[] str = s.toCharArray();
      int start = 0;
      String result;

      for (int i = 0; i < str.length; i++) {
          if (str[i] == ' ') {
            reverse(str, start, i - 1);
            start = i + 1;
          } else if (i == str.length - 1) {
              reverse(str, start, i);
          }
      }
      result = new String(str);
      return result;
    }
    
    public void reverse(char[] s, int start, int end) {
      while (start < end) {
        char temp = s[start];
        s[start] = s[end];
        s[end] = temp;
        start++;
        end--;
      }
    }

}
```
