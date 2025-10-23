### Approach 1: Using Hash Map
```java
public int majorityElement(int[] nums) {
    Map<Integer, Integer> freq = new HashMap<>();

    int majorityElement = -1, maxCount  = 0;

    for (int num : nums) {
        int count = 1;
        if (freq.get(num) != null) {
            count = freq.get(num) + 1;
        }
        freq.put(num, count);
        if(count > maxCount){
            majorityElement = num;
            maxCount = count;
        }
    }

    return majorityElement;
}
```
<br>

### Approach 1: Bayer Moore's Algorithm - O(1) Space Complexity
Refer: https://www.youtube.com/watch?v=7pnhv842keE 

Set count and majorityElement as 0, now move forward. If count is zero, increment the count and set majorityElement as the i-th element
If count is not zero, and i-th element is not majorityElement, decrement the count.
This approach always works as long as the array is valid and has a majority element
The core logic is the there will be one element which is present in more than n/2 times in the array

```java
public int majorityElement(int[] nums) {
    int majorityElement = -1, count = 0;
    for (Integer num : nums) {
        if (count == 0) {
            majorityElement = num;
        }
        if (num == majorityElement) {
            count += 1;
        } else {
            count -= 1;
        }
    }
    return majorityElement;
}
```

