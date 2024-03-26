## Example for JS
Sure, here are a few JavaScript coding interview questions that are similar to problems you might find on LeetCode:

Two Sum:
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
javascript
Copy code
function twoSum(nums, target) {
    const map = new Map();
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (map.has(complement)) {
            return [map.get(complement), i];
        }
        map.set(nums[i], i);
    }
}
Reverse Integer:
Given a 32-bit signed integer, reverse digits of an integer.
javascript
Copy code
function reverseInteger(x) {
    const limit = 2 ** 31;
    const sign = x < 0 ? -1 : 1;
    let result = 0;
    x = Math.abs(x);
    while (x > 0) {
        result = result * 10 + x % 10;
        if (result > limit || result < -limit) return 0;
        x = Math.floor(x / 10);
    }
    return result * sign;
}
Palindrome Number:
Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.
javascript
Copy code
function isPalindrome(x) {
    if (x < 0 || (x % 10 === 0 && x !== 0)) return false;
    let reversed = 0;
    while (x > reversed) {
        reversed = reversed * 10 + x % 10;
        x = Math.floor(x / 10);
    }
    return x === reversed || x === Math.floor(reversed / 10);
}
Valid Parentheses:
Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
javascript
Copy code
function isValid(s) {
    const stack = [];
    const pairs = { ')': '(', '}': '{', ']': '[' };
    for (let char of s) {
        if (char in pairs) {
            if (stack.pop() !== pairs[char]) return false;
        } else {
            stack.push(char);
        }
    }
    return stack.length === 0;
}
Merge Two Sorted Lists:
Merge two sorted linked lists and return it as a sorted list.
javascript
Copy code
function mergeTwoLists(l1, l2) {
    if (!l1) return l2;
    if (!l2) return l1;
    if (l1.val < l2.val) {
        l1.next = mergeTwoLists(l1.next, l2);
        return l1;
    } else {
        l2.next = mergeTwoLists(l1, l2.next);
        return l2;
    }
}
These are just a few examples of JavaScript coding interview questions that are similar to those found on LeetCode. They cover a range of topics including arrays, strings, linked lists, and mathematical operations.





