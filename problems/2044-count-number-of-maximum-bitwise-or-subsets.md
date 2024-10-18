## Problem
Given an integer array nums, find the maximum possible bitwise OR of a subset of nums and return the number of different non-empty subsets with the maximum bitwise OR.

An array a is a subset of an array b if a can be obtained from b by deleting some (possibly zero) elements of b. Two subsets are considered different if the indices of the elements chosen are different.

The bitwise OR of an array a is equal to a[0] OR a[1] OR ... OR a[a.length - 1] (0-indexed).

#### Examples
| Input | Output | Explanation |
|---|---|---|
| nums = [3,1] | 2 |  The maximum possible bitwise OR of a subset is 3. There are 2 subsets with a bitwise OR of 3 |
| nums = [2,2,2] | 7 | All non-empty subsets of [2,2,2] have a bitwise OR of 2. There are 23 - 1 = 7 total subsets |
| nums = [3,2,1,5] | 6 | The maximum possible bitwise OR of a subset is 7. There are 6 subsets with a bitwise OR of 7 |
 
#### Constraints:
-  1 <= nums.length <= 16
- -1 <= nums[i] <= 10 ** 5

## Solution
Its not a optimal solution but it works well and passed all submissions without problems.
```ts
function countMaxOrSubsets(nums: number[]): number {
    let maxOrValue = 0;
    for (const num of nums) {
        maxOrValue |= num;
    }
    return countSubsets(nums, 0, 0, maxOrValue)
};

function countSubsets(nums: number[], index: number, currentOr: number, targetOr: number): number { // Recursive function
    if (index == nums.length) {
        return currentOr === targetOr ? 1 : 0;
    }

    const countWithout = countSubsets(nums, index + 1, currentOr, targetOr);
    const countWith = countSubsets(nums, index + 1, currentOr | nums[index], targetOr);

    return countWithout + countWith
}
```
