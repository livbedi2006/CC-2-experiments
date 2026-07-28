### Experiment 1.1 - Contain Duplicate (LEETCODE 217) 
AIM - Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.
ALGORITHM - 
1. Start.
2. Create an empty HashSet to store the elements of the array.
3. Traverse each element num in the array nums.
4. Check if num is already present in the HashSet.
5. If it is present, return true because a duplicate is found.
6. Otherwise, add num to the HashSet.
7. Repeat Steps 4 to 6 until all elements are processed.
8. If no duplicate is found after traversing the entire array, return false.
9. Stop.

Code - 

import java.util.HashSet;

class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashSet<Integer> set = new HashSet<>();

        for (int num : nums) {
            if (set.contains(num)) {
                return true;
            }
            set.add(num);
        }

        return false;
    }
}


###Experiment 1.1 - Contain Duplicate II (LEETCODE 219) 

AIM - Given an integer array nums and an integer k, return true if there are two distinct indices i and j in the array such that nums[i] == nums[j] and abs(i - j) <= k.
ALGORITHM - 
1. Start.
2. Create a HashMap to store each element and its latest index.
3. Traverse the array from index 0 to n - 1.
4. For each element:
    * Check if it already exists in the HashMap.
    * If it exists, calculate the difference between the current index and the previous index.
    * If the difference is less than or equal to k, return true.
5. Update the current element’s index in the HashMap.
6. Continue until all elements are processed.
7. If no such pair is found, return false.
8. Stop.

Code - 

import java.util.HashMap;

class Solution {
    public boolean containsNearbyDuplicate(int[] nums, int k) {
        HashMap<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            if (map.containsKey(nums[i])) {
                int prevIndex = map.get(nums[i]);

                if (i - prevIndex <= k) {
                    return true;
                }
            }

            map.put(nums[i], i);
        }

        return false;
    }
}
