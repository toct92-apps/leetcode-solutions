## Approach 1: Brute Force 
Shift the elements to the right when zero is encountered and add zero to the last zero position.
```java
public void moveZeroes(int[] nums) {
    int i = 0;
    int k = nums.length-1;
    while (i < k){
        if(nums[i] == 0){
            for(int j = i; j < k; j ++){
                nums[j] = nums[j+1];
            }
            nums[k] = 0;
            k--;
        }
        else {
            i++;
        }
    }
}
```

<br>

## Approach 2: Using in-place swaps using two pointers 
Have left and right pointer starting with 0.
The left pointer keeps track of the last zero position, and right pointer iterates through the elements.
Whenever right pointer encounters a non-zero element, swap it with the left pointer and increment the left pointer
This will seggregate the array in two halves (similar to Quick Sort / Quick Select)
```java
public void moveZeroes(int[] nums) {
    int l = 0;
    for(int r = 0; r < nums.length; r++){
        if(nums[r] != 0){
            int temp = nums[r];
            nums[r] = nums[l];
            nums[l] = temp;

            l++;
        }
    }
}
```
