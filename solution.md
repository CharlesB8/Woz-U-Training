
# Reverse Words Solution  


```java
import java.util.*;

class Solution {
    public String reverseWords(String s) {
        String[] words = s.trim().replaceAll(" +", " ").split(" ");
        StringBuilder sb = new StringBuilder();
        
        for(String word : words){
            sb.insert(0, word + " ");
        }
        return sb.toString().trim();
        
    }
}
```

# Alternate Caps Solution


```java
class Solution{
    public static String[] capitalize(String s){
        // Gorillaz - Do Ya Thing (2010)
      StringBuilder even = new StringBuilder();
      StringBuilder odd = new StringBuilder();

      for (int i = 0; i < s.length(); i++){
        if (i % 2 == 0) {
          String ch = s.substring(i, i+1);
          even.append(ch.toUpperCase());
          odd.append(ch.toLowerCase());
        }
        else {
          String ch = s.substring(i, i+1);
          even.append(ch.toLowerCase());
          odd.append(ch.toUpperCase());
        }
      }
      
      String[] answer = new String[2];
      answer[0] = even.toString();
      answer[1] = odd.toString(); 
      
      return answer;
    }
}
```
