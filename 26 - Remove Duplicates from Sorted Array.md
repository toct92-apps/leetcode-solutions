### Using two pointers
Pointer i keeps track of the last unique element, pointer j iterates through the array<br>
If num[i] ≠ num[j], increment i and add num[j]. <>br>
If them num[i] = num[j], move forward
```java
public int removeDuplicates(int[] nums) {
    int l = 0;
    for(int r = 0; r < nums.length; r++){
        if (nums[r] != nums[l]){
            nums[++l] = nums[r];
        }
    }
    return l+1;
}
```
