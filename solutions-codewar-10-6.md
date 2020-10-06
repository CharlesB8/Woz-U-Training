# Remove String spaces

```java
class Kata {
    static String noSpace(final String x) {
return x.replaceAll("\\s", "");
    }
}
```


# Convert String to an array
```java 
public class Solution {

    public static String[] stringToArray(String s) {
      //your code;
      
        return s.split("\\s");
    }

}
```
