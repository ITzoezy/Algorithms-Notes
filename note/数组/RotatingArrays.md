# 给你一个数组，将数组中的元素向右轮转 k 个位置，其中 k 是非负数
```java
class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length
        int i = 0,pos = 0, pre = nums[pos],temp = nums[pos];

        if(k%n == 0) return;

        while (n-- != 0) {
            pos =  (pos + k) % len;
            temp = nums[pos];
            nums[pos] = pre;
            pre = temp;
            if (pos == i) {
                pos = ++i;
                pre = nums[pos];
                temp = nums[pos];
            }
        }
    }
}
```