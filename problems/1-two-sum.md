## Problem
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

#### Examples
| Input | Output | Explanation |
|---|---|---|
| nums = [2,7,11,15], target = 9 | [0,1] |  Because nums[0] + nums[1] == 9, we return [0, 1] |
| nums = [3,2,4], target = 6 | [1,2] | - |
| nums = [3,3], target = 6 | [0,1] | - |
 
#### Constraints:
-  2 <= nums.length <= 104
- -109 <= nums[i] <= 109
- -109 <= target <= 109

Only one valid answer exists.

## Solution
Its not a optimal solution but it works well and passed all submissions without problems.
```ts
function twoSum(nums: number[], target: number): number[] {
    let result = [];
    let entries = nums.entries();

    nums.forEach((value, index) => {
        nums.forEach((insideValue, insideIndex) => {
        if (insideIndex != index && ((insideValue + value) == target) && result.length == 0) {
                result = [index, insideIndex]
            }
        })
        if (result) {
            return;
        }
    })

    return result;
};
```
