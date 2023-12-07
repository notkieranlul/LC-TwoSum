# LeetCode - TwoSum Problem

### Approach
I first started with the two-pass hash table which worked great however I saw this can be improved by just looking back on the hash table to see if the elements complement already exists within there.

Overall I was able to sumbit with the below stats.

Beats: 99.41%
Memory: 43 MB

Complexity
Time complexity: O(n)

Space complexity: O(n)

### Code
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[] { map.get(complement), i };
            }
            map.put(nums[i], i);
        }
        return null;
    }
}
```
