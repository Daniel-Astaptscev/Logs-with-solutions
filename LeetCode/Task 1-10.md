
## 412. Fizz Buzz

Given an integer `n`, return a string `array` answer (1-indexed) where:

`answer[i] == "FizzBuzz"` if `i` is divisible by `3` and `5`.

`answer[i] == "Fizz"` if `i` is divisible by `3`.

`answer[i] == "Buzz"` if `i` is divisible by `5`.

`answer[i] == i` (as a string) if none of the above conditions are true.

#### Code: 

```bash
  class Solution:
    def fizzBuzz(self, n: int) -> List[str]:
        a = []
        for i in range(1, n+1):
            if i%3==0 and i%5==0:
                a.append('FizzBuzz')
            elif i%3==0:
                a.append('Fizz')
            elif i%5==0:
                a.append('Buzz')
            else:
                a.append(str(i))
        return a
```

## 349. Intersection of Two Arrays

Given two integer arrays `nums1` and `nums2`, return an array of their 
intersection. Each element in the result must be unique and you may return the result in any order.

#### Code: 

```bash
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        return list(set(nums1) & set(nums2))
```

## 344. Reverse String

Write a function that reverses a string. The input string is given as an array of characters `s`.
You must do this by modifying the input array in-place with `O(1)` extra memory.

#### Code: 

```bash
class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        s.reverse()
        return s   
```

## 27. Remove Element

Given an integer array `nums` and an integer `val`, remove all occurrences of `val` in `nums` in-place. The order of the elements may be changed. Then return the number of elements in `nums` which are not equal to `val`.

Consider the number of elements in `nums` which are not equal to `val` be `k`, to get accepted, you need to do the following things:

- Change the array `nums` such that the first `k` elements of nums contain the elements which are not equal to `val`. The remaining elements of `nums` are not important as well as the size of `nums`.
- Return `k`.

#### Code: 

```bash
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        for _ in range(nums.count(val)): 
            nums.remove(val)
        return len(nums)
```

## 66. Plus One

You are given a large integer represented as an integer array `digits`, where each `digits[i]` is the `i^th` digit of the integer. The digits are ordered from most significant to least significant in left-to-right order. The large integer does not contain any leading `0's`.

Increment the large integer by one and return the resulting array of digits.

#### Code: 

```bash
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        k = int(''.join([str(i) for i in digits]))
        k += 1
        return [int(i) for i in str(k)]
```

## 58. Length of Last Word

Given a string `s` consisting of words and spaces, return the length of the last word in the string.

A word is a maximal substring consisting of non-space characters only.

#### Code: 

```bash
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        for i in s.split()[::-1]:
            return len(i)
```

## 35. Search Insert Position

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with `O(log n)` runtime complexity.

#### Code: 

```bash
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        if target in nums:
            return nums.index(target)
        else:
            nums.append(target)
            nums.sort() 
            return nums.index(target)
```

## 28. Find the Index of the First Occurrence in a String

Given two strings `needle` and `haystack`, return the index of the first occurrence of `needle` in `haystack`, or `-1` if `needle` is not part of `haystack`.

#### Code: 

```bash
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        return haystack.find(needle)
```

## 69. Sqrt(x)

Given a non-negative integer `x`, return the square root of `x` rounded down to the nearest integer. The returned integer should be non-negative as well.

You must not use any built-in exponent function or operator.

- For example, do not use `pow(x, 0.5)` in c++ or `x ** 0.5` in python.

#### Code: 

```bash
class Solution:
    def mySqrt(self, x: int) -> int:
        import math
        return math.floor((math.sqrt(x)))
```

## 268. Missing Number

Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

#### Code: 

```bash
  class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        res = [i for i in range(len(nums)+1)]
        for i in res:
            if i not in nums:
                return i
```


