### Approach 1: Using Hash Map
```java
public int majorityElement(int[] nums) {
    Map<Integer, Integer> freq = new HashMap<>();

    for (int num : nums) {
        if (freq.get(num) == null) {
            freq.put(num, 0);
        }
        freq.put(num, freq.get(num) + 1);
    }

    int majorElement = -1;
    int maxFreq = 0;
    for (Integer key : freq.keySet()) {
        System.out.println(key + " " + freq.get(key));
        if (freq.get(key) > maxFreq){
            maxFreq = freq.get(key);
            majorElement = key;
        }
    }
    return majorElement;

}
```

