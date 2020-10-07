# Two Sum



```java
import java.util.HashMap;
import java.util.Scanner;
import java.util.Map;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        
        //intialize map
        Map<Integer, Integer> numMap = new HashMap<>();
        
        //loop though nums to find integers
        for (int i = 0; i < nums.length; i++) {
            int numbers = target - nums[i];
            if (numMap.containsKey(numbers)) {
                return new int[] { numMap.get(numbers), i };
            } else {
                numMap.put(nums[i], i);
            }
        }
        return new int[] {};
    }
  }
```


# Top K

```java
class Solution {
    public List<String> topKFrequent(String[] words, int k) {
        List<String> res = new LinkedList<>(); 
        Map<String, Integer> map = new HashMap<>();
        for(int i = 0; i < words.length; i++){
            if(map.containsKey(words[i])){
                map.put(words[i], map.get(words[i])+ 1);
            }
            else{
                map.put(words[i], 1);
            }
        }

        //not sure how this part works, but found it online
        PriorityQueue<Map.Entry<String, Integer>> items = new PriorityQueue<>(
            (a,b) -> a.getValue() == b.getValue() ? b.getKey().compareTo(a.getKey()) :a.getValue() - b.getValue()
        );

        for (Map.Entry<String, Integer> entry: map.entrySet()){
            items.offer(entry);
            if(items.size()> k) items.poll();
        }

        while(!items.isEmpty()){
            res.add(0, items.poll().getKey()); 
        }

        return res;
    }
}
```
