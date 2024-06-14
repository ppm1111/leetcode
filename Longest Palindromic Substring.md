# 窮舉法

```java
class Solution {
    public String longestPalindrome(String s) {
        int max = Integer.MIN_VALUE;
        String maxStr = "";
        for (int i = 0; i < s.length(); i++) {
            for (int j = i; j < s.length(); j++) {
                if (vaild(s, i, j)) {
                    if (j-i > max) {
                        max = j-i;
                        maxStr = s.substring(i, j+1);
                    }
                }
            }
        }
        return maxStr;
    }
    private boolean vaild(String s, int start, int end) {
        while(start < end) {
            if (s.charAt(start) != s.charAt(end)) {
                return false;
            }
            start++;
            end--;
        }
        return true;
    }
}
```
