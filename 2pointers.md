##1
Debug

Home
Courses
Grokking the Coding Interview Patterns
Problem: Valid Palindrome
75
easy
15 min
Hint
Explore how to efficiently validate if a string is a palindrome using the two pointers technique. Learn to ignore non-alphanumeric characters and case differences while solving this common coding interview problem. This lesson helps you break down the problem and implement a clear solution in a hands-on coding environment.
Statement
Given a string, s, return TRUE if it is a palindrome; otherwise, return FALSE.

A phrase is considered a palindrome if it reads the same backward as forward after converting all uppercase letters to lowercase and removing any characters that are not letters or numbers. Only alphanumeric characters (letters and digits) are taken into account.

Constraints:

1
≤
1≤
 s.length 
≤
3000
≤3000

s consists only of printable ASCII characters.

Hint 1
As we only care about alphanumeric characters, can we first process the string to remove everything else and convert it all to lowercase? That will simplify our comparisons.

Hint 2
Instead of building a new reversed string, try using two pointers: one starting from the left and one from the right. Compare characters at both ends and move the pointers inward.

Hint 3
When should the comparison stop? Think about the stopping condition when the two pointers meet or cross each other.



def is_palindrome(s):
  left, right = 0, len(s) - 1

  while left < right:
      while left < right and not s[left].isalnum():
        left += 1

      while left < right and not s[right].isalnum():
        right -= 1

      if s[left].lower() != s[right].lower():
        # Replace this placeholder "pass" statement with your code
        pass
      
      left += 1
      right -= 1

  return True

  ##2

  Problem: Sum of Three Values
med
30 min
Hint
Explore the 3Sum problem to identify all unique triplets in an array that sum to zero. Learn to apply the two pointers technique effectively to handle linear data structures and avoid duplicates, preparing you for coding interviews with efficient problem-solving strategies.
Statement
Given an integer array nums, find all unique triplets [nums[i], nums[j], nums[k]] where i, j, and k are distinct indices, such that the three elements sum to zero.

The result must not contain any duplicate triplets. The order of the output and the order of elements within each triplet does not matter.

Note: The solution set must only include unique triplets. Two triplets are considered duplicates if they contain the same elements regardless of ordering.

Constraints:

3
≤
3≤
 nums.length 
≤
3000
≤3000

−
1
0
5
≤
−10 
5
 ≤
 nums[i] 
≤
1
0
5
≤10 
5
 

Hint 1
Can we reduce the problem to something simpler?

We’re looking for three numbers—say x, y, and z—such that x + y + z = 0. What if we fix one number, say x, and then search for two numbers that sum to -x? That turns the problem into a familiar Two Sum!

Hint 2
In the Two Sum problem, once you fix one number (say x), you must look for another number (y) such that y = target - x. Typically, you’d have to scan the entire array to find y. Can we sort or transform the array to allow us to search more efficiently?

Hint 3
Duplicates can lead to repeated triplets!

After sorting, how can we skip over duplicate values to ensure each triplet is unique? Maybe we should skip the same number if it reappears after a match.

def three_sum(nums):
    
    # Replace this placeholder return statement with your code
    return [[]]

##3

Home
Courses
Grokking the Coding Interview Patterns
Problem: Remove nth Node from End of List
med
30 min
Hint
Explore how to remove the nth node from the end of a singly linked list using the two pointers approach. This lesson helps you understand and implement an efficient single-pass solution, apply linear data structure manipulation, and practice coding in a hands-on environment.
Statement
Given the head of a singly linked list, remove the 
n
t
h
n 
th
 
 node from the end of the list and return the head of the modified list.

Note: Could you solve this in a single pass through the list?

Constraints:

The number of nodes in the list is sz

1
≤
1≤
 sz 
≤
30
≤30

0
≤
0≤
 Node.val 
≤
100
≤100

1
≤
1≤
 n 
≤
≤
 sz
≤
k
≤k

Hint 1
Can we avoid two passes through the linked list?

Counting the length 
(
L
)
(L)
 and removing the 
(
L
−
n
+
1
)
th
(L−n+1) 
th
 
 node takes two traversals. Is there a way to remove the node in just one pass?

Hint 2
What if we use two pointers?

Suppose you have two pointers. If you move the first pointer n steps ahead of the second, how does that help you know which node to remove when you reach the end?

Hint 3
After moving the first pointer 
n
n
 steps, try moving both pointers together—one node at a time—until the first pointer reaches the end. Where is the second pointer now, relative to the node you want to delete?

 # Definition for a Linked List node
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
from ds_v1.LinkedList.LinkedList import ListNode

def remove_nth_last_node(head, n):
    
    # Replace this placeholder return statement with your code
    return None


##4

Home
Courses
Grokking the Coding Interview Patterns
Problem: Sort Colors
med
30 min
Hint
Explore how to efficiently sort an array containing red, white, and blue colors represented by 0, 1, and 2 using the two pointers approach. Understand how to implement this one pass algorithm without extra space and apply it to coding interview problems involving linear data structures.
Statement
You are given an array nums of length n, where each element represents an object colored either red, white, or blue. The integers 0, 1, and 2 are used to represent red, white, and blue, respectively.

Sort the array in place so that all objects of the same color are grouped together, arranged in the order: red (0), white (1), and blue (2).

You must solve this problem without using any library sort function.

Note: Could you come up with a one pass algorithm using only constant extra space?

Constraints:

n
n
 
=
=
==
 colors.length

1
≤
1≤
 
n
n
 
≤
300
≤300

colors[i] is either 0, 1, or 2

Hint 1
Suppose your scan pointer meets a 0, i.e., a red color, at index i. What is the earliest index that 0 could safely live in once the array is fully sorted?

The earliest safe spot is whatever index the left boundary currently marks.

Swap the 0 into that slot immediately; then bump the left boundary forward so the next 0 has a new home.

Bonus insight: this guarantees every 0 crosses each index at most once.

Hint 2
When you swap a 2 with the value at the right boundary, the cursor stays on the same index. Why bother re-examining that index instead of moving on?

Because the value you just pulled in from the right is still unknown—it might be a 0 that needs another move.

By re-checking, the algorithm ensures each element is handled exactly once without missing any rescues.

Hint 3
Your pointers move left → right, the right boundary moves right → left, and eventually they’ll meet.

Which condition tells you every element has been placed and it’s safe to stop?

Stop when the cursor is > right boundary. At that instant, everything left of the cursor holds only 0s and 1s, everything right of the boundary holds only 2s, and the region between them has been fully processed.

def sort_colors(colors):
    
    # Replace this placeholder return statement with your code
    return colors

##5


Problem: Reverse Words in a String
med
30 min
Explore the two pointers technique to reverse the order of words in a string without altering the characters within each word. Learn to manage spaces effectively by removing leading, trailing, and extra spaces, and return a clean, properly spaced sentence.
Statement
You are given a string sentence that may contain leading or trailing spaces, as well as multiple spaces between words. Your task is to reverse the order of the words in the sentence without changing the order of characters within each word. Return the resulting modified sentence as a single string with words separated by a single space, and no leading or trailing spaces.

Note: A word is defined as a continuous sequence of non-space characters. Multiple words separated by single spaces form a valid English sentence. Therefore, ensure there is only a single space between any two words in the returned string, with no leading, trailing, or extra spaces.

Constraints:

The sentence contains English uppercase and lowercase letters, digits, and spaces.

There is at least one word in a sentence.

1
≤
1≤
 sentence.length 
≤
1
0
4
≤10 
4

def reverse_words(sentence):

    # Replace this placeholder return statement with your code
    return ""

##6
Problem: Valid Word Abbreviation
easy
15 min
Explore how to determine if an abbreviation correctly represents a given word by applying the two pointers technique. This lesson helps you handle numeric skips and letter matches, ensuring full coverage without leading zeros or missing characters.
Statement
A string can be abbreviated by replacing any number of non-adjacent, non-empty substrings with their respective lengths. The numeric replacements must not contain leading zeros.

Given a string word and an abbreviation abbr, determine whether abbr is a valid abbreviation of word.

The abbreviation abbr consists of lowercase English letters and numeric values. Each numeric value in abbr represents the number of characters skipped in word. Letters in abbr must match the corresponding characters in word exactly. The abbreviation is valid if and only if it fully accounts for every character in word from left to right with no characters remaining or missing.

Note: A numeric value in abbr must not have leading zeros (e.g., "01" is invalid). A value of "0" is also invalid since it would represent replacing an empty substring.

Constraints:

1
≤
1≤
 word.length 
≤
20
≤20

word consists of only lowercase English letters.

1
≤
1≤
 abbr.length 
≤
10
≤10

abbr consists of lowercase English letters and digits.

All integers in abbr will fit in a 
32
32
-bit integer.

def valid_word_abbreviation(word, abbr):

    # Replace the following return statement with your code
    return True


##7

Debug

Home
Courses
Grokking the Coding Interview Patterns
Problem: Valid Palindrome II
easy
15 min
Explore how to verify if a given string can become a valid palindrome by removing at most one character. This lesson teaches you to apply the two-pointer technique to solve the problem efficiently, with linear time complexity and constant space. By practicing this approach, you'll enhance your skills in handling string and linear data structure problems relevant for coding interviews.
Statement
Write a function that takes a string as input and checks whether it can be a valid palindrome by removing at most one character from it.

Constraints:

1
≤
1≤
 string.length 
≤
≤
 
1
0
5
10 
5
 

The string only consists of English letters.


def is_palindrome(string):
  
  # Replace this placeholder return statement with your code
  
  return False

##8

Home
Courses
Grokking the Coding Interview Patterns
Problem: Lowest Common Ancestor of a Binary Tree III
med
30 min
Understand how to find the lowest common ancestor of two nodes in a binary tree when parent pointers are available. This lesson helps you apply two-pointer strategies to navigate upward through the tree and determine the common ancestor, even without a root reference, enhancing your problem-solving skills for coding interviews.
Statement
You are given two nodes, p and q. The task is to return their lowest common ancestor (LCA). Both nodes have a reference to their parent node. The tree’s root is not provided; you must use the parent pointers to find the nodes’ common ancestor.

Note: The lowest common ancestor of two nodes, p and q, is the lowest node in the binary tree, with both p and q as descendants.

In a tree, a descendant of a node is any node reachable by following edges downward from that node, including the node itself.

Constraints:

−
1
0
4
≤
−10 
4
 ≤
Node.data 
≤
1
0
4
≤10 
4
 

The number of nodes in the tree is in the range 
[
2
,
500
]
.
[2,500].

All Node.data are unique.

p != q

Both p and q are present in the tree.

# Definition for a binary tree node
# class EduTreeNode:
#     def __init__(self, data):
#         self.data = data
#         self.left = None
#         self.right = None
#         self.parent = None

from EduTreeNode import *

def lowest_common_ancestor(p, q):

    # Replace this placeholder return statement with your code
    return q

##9

Grokking the Coding Interview Patterns
Problem: Strobogrammatic Number
easy
15 min
Explore how to use the two-pointer approach to determine if a given number is strobogrammatic, meaning it appears the same when rotated 180 degrees. This lesson helps you apply logical steps to verify these numbers in strings while practicing efficient problem-solving strategies.
Statement
Given a string num representing an integer, determine whether it is a strobogrammatic number. Return TRUE if the number is strobogrammatic or FALSE if it is not.

Note: A strobogrammatic number appears the same when rotated 
180
180
 degrees (viewed upside down). For example, “69” is strobogrammatic because it looks the same when flipped upside down, while “962” is not.

Constraints:

1
<
=
1<=
 num.length 
<
=
50
<=50

num contains only digits.

num has no leading zeros except when the number itself is zero.

def is_strobogrammatic(num):
  
    # Replace this placeholder return statement with your code
    return False
##10

Problem: Minimum Number of Moves to Make Palindrome
hard
40 min
Explore how to use the two-pointer approach to determine the minimum number of adjacent character swaps needed to convert a given string into a palindrome. Understand problem constraints and implement an efficient solution that guarantees transforming any valid input into a palindrome.
Statement
Given a string s, return the minimum number of moves required to transform s into a palindrome. In each move, you can swap any two adjacent characters in s.

Note: The input string is guaranteed to be convertible into a palindrome.

Constraints:

1
≤
1≤
 s.length 
≤
2000
≤2000

s consists of only lowercase English letters.

s is guaranteed to be converted into a palindrome in a finite number of moves.

def min_moves_to_make_palindrome(s):
    
    # Replace this placeholder return statement with your code
    return -1

##11

Problem: Next Palindrome Using Same Digits
hard
40 min
Explore how to solve the problem of finding the next smallest palindrome larger than a given numeric palindrome by rearranging its digits. This lesson teaches you to apply two-pointer techniques and understand constraints to implement an efficient solution, preparing you for similar coding interview challenges.
Statement
Given a numeric string, num_str, representing a palindrome (composed only of digits). Return the smallest palindrome larger than num_str that can be created by rearranging its digits. If no such palindrome exists, return an empty string "".

Consider the following example to understand the expected output for a given numeric string:

input string = "123321"

The valid palindromes made from the exact digits are "213312", "231132", "312213", "132231", "321123".

We return the palindrome "132231" because it is the smallest palindrome larger than the input string "123321".

Constraints:

1
≤
1≤
 num_str.length 
≤
1
0
5
≤10 
5
 

num_str is a palindrome.

def find_next_palindrome(num_str):
  
    # Replace the following return statement with your code
    return ""
##12

Problem: Count Subarrays With Fixed Bounds
hard
40 min
Explore how to count fixed-bound subarrays in integer arrays by identifying subarrays where the minimum equals minK and maximum equals maxK. Understand the problem constraints and apply the two pointers technique to solve it efficiently, strengthening your skills for coding interviews.
Statement
Given an integer array, nums, and two integers minK and maxK, return the number of fixed-bound subarrays.

A subarray in nums is called a fixed-bound subarray if it satisfies the following conditions:

The smallest value in the subarray equals minK.

The largest value in the subarray equals maxK.

Note: A subarray is a contiguous sequence of elements within an array.

Constraints:

2
≤
2≤
 nums.length 
≤
1
0
3
≤10 
3
 

1
≤
1≤
 nums[i], minK, maxK 
≤
1
0
3
≤10 
3

def countSubarrays(nums, minK, maxK):
    
    # Replace this placeholder return statement with your code
    return -1

##13
Problem: Find the Lexicographically Largest String From Box II
hard
40 min
Explore how to solve substring splitting problems by applying the two-pointer approach. Learn to generate unique splits and identify the lexicographically largest substring among them, enhancing your skills in string manipulation and efficient problem-solving.
Statement
You are given a string, word, and an integer numFriends, representing the number of friends participating in a game organized by Alice.

The game consists of multiple rounds, and in each round:

The string word is split into exactly numFriends non-empty substrings.

The split must be unique; no previous round has produced the same sequence of splits.

All resulting substrings from the split are placed into a box.

When all rounds are over and all possible unique splits have been performed, determine the lexicographically largest string among all the substrings in the box.

A string 
a
a
 is considered lexicographically larger than a string 
b
b
 if:

At the first position where 
a
a
 and 
b
b
 differ, the character in 
a
a
 comes later than the corresponding character in 
b
b
 in the alphabet.

If 
a
a
 is a prefix of 
b
b
, the longer string is considered larger.

Constraints:

1
≤
1≤
 word.length 
≤
1
0
3
≤10 
3
 

word consists only of lowercase English letters.

1
≤
1≤
 numFriends 
≤
≤
 word.length

 def answerString(word, numFriends):
    # Replace this placeholder return statement with your code
    return ""

##14

Problem: Get the Maximum Score
hard
40 min
Explore how to use the two pointers technique to find the maximum possible score from traversing two sorted arrays. Learn to handle switching between arrays at common elements and apply constraints to optimize your solution for coding interviews.
Statement
You are given two sorted arrays of distinct integers, nums1 and nums2.

A valid path is constructed according to the following rules:

You start at the index 
0
0
 of either nums1 or nums2.

From there, you must traverse the chosen array from left to right.

Suppose you encounter a number in both arrays (a common element, not necessarily at the same index). In that case, you may choose to switch to the other array at that element and continue the traversal from that point forward.

A common element can only be counted once in the total path score, regardless of the array it appears.

The score of a path is defined as the sum of all unique elements visited during traversal. Your task is to return the maximum possible score achievable by any valid path. As the answer may be too large, return the maximum score modulo 
1
0
9
+
7
10 
9
 +7
.

Constraints:

1 
≤
≤
 nums1.length, nums2.length 
≤
≤
 
1
0
5
10 
5
 

1 
≤
≤
 nums1[i], nums2[i] 
≤
≤
 
1
0
7
10 
7
 

All elements in nums1 and nums2 are strictly increasing.

def maxSum(nums1, nums2):
    # Replace this placeholder return statement with your code
    return -1

##15

Problem: Append Characters to String to Make Subsequence
med
30 min
Explore how to determine the minimum characters to append to a source string to make a target string its subsequence. Learn to apply two-pointer techniques efficiently for solving linear string problems while understanding subsequence concepts and constraints.
Statement
You’re given two strings, source and target, made up of lowercase English letters. Your task is to determine the minimum number of characters that must be appended to the end of the source so that the target becomes a subsequence of the resulting string.

Note: A subsequence is formed by deleting zero or more characters from a string without changing the order of the remaining characters.

Constraints:

1
≤
1≤
 source.length, target.length 
≤
1
0
3
≤10 
3
 

source and target consist only of lowercase English letters.


def appendCharacters(source, target):
    i = j = 0

    while i < len(source) and j < len(target):

        # If characters match, we found one target character.
        if source[i] == target[j]:
            j += 1

        # Always move through source.
        i += 1

    # j = number of target characters already found.
    # The remaining target characters must be appended.
    return len(target) - j

##16

Problem: Squares of a Sorted Array
easy
15 min
Explore how to apply the two pointers approach to transform a sorted integer array by squaring its elements and maintaining sorted order. Understand the problem constraints and develop a solution that handles edge cases efficiently, preparing you for coding interview challenges.
Statement
You are given an integer array, nums, sorted in non-decreasing order. Your task is to return a new array containing the squares of each number, also sorted in non-decreasing order.

Constraints:

1
≤
1≤
 nums.length 
≤
1
0
3
≤10 
3
 

−
1
0
4
≤
−10 
4
 ≤
 nums[i] 
≤
1
0
4
≤10 
4
 

nums is sorted in non-decreasing order.

def sortedSquares(nums):
    
    for i in range(len(nums) ):
        nums [i ] = nums[i] * nums[i]
        
    
    nums.sort()
    
    return nums

##17

Problem: Reverse String
easy
15 min
Explore how to reverse a string in-place by applying the two pointers technique to modify the original character array without additional memory. This lesson helps you understand and implement an efficient solution for linear data structures, reinforcing concepts useful in coding interviews.
Statement
You are given a character array, s, representing a string. Write a function that reverses the array in-place.

The reversal must be done by modifying the original array directly.

You cannot use extra memory beyond a constant amount 
O
(
1
)
O(1)
.

Constraints

1
1
 
<
=
<=
 s.length 
<
=
<=
 
1000
1000

Each s[i] is a printable ASCII character.

def reverseString(s):
    
    left, right = 0, len(s) - 1
    while left < right:
        s[left], s[right] = s[right], s[left]
        left += 1
        right -= 1


##18

Problem: Intersection of Two Linked Lists
easy
15 min
Explore how to identify the intersection point of two singly linked lists by using the two-pointer approach. This lesson helps you understand the problem constraints, assess if two lists share nodes in memory, and implement an efficient solution to return the intersection node or null if none exists.
Statement
You are given the heads of two singly linked lists, headA and headB, to determine whether the two lists intersect. If they intersect, return the node where the intersection begins. Otherwise, return NULL.

Note: Linked lists intersect if they share a common node in memory, not just a node with the same value.

Constraints:

1
≤
1≤
 node.val 
≤
1
0
5
≤10 
5
 

The number of nodes of 
l
i
s
t
A
listA
 is in the 
m
m
.

The number of nodes of 
l
i
s
t
B
listB
 is in the 
n
n
.

1
≤
m
,
n
≤
1
0
3
1≤m,n≤10 
3

# Input Format (As handled by the judge. Your program is not given these inputs )
# listA – The first linked list.
# listB – The second linked list.
# skipA – The number of nodes to skip in listA (starting from the head) to reach the intersection node.
# skipB – The number of nodes to skip in listB (starting from the head) to reach the intersection node.
# intersectVal – The value of the node where the intersection begins. Set to 0 if the two linked lists do not intersect.
# Using these inputs, the judge constructs the linked lists and connects them at the intersection point, if one exists.
# The two list heads, headA and headB, are then passed to your function.
# If your function correctly identifies and returns the intersecting node, the solution is accepted.
def getIntersectionNode(headA, headB):

    # Replace this placeholder return statement with your code
    return None

##19

Problem: Remove Element
easy
15 min
Understand how to use the two pointers pattern to remove all instances of a specific value from an array in place. This lesson teaches efficient array modification without extra memory allocation and returns the new length of the array excluding the target value. Practice this approach to prepare for coding interviews that test your mastery of array manipulation and pointers.
Statement
You are given an integer array, nums, and an integer, val. Your task is to remove all occurrences of val from nums in place, meaning no additional memory allocation should be used. The relative order of the elements in the array may be changed. After modifying the array, return the number of elements that are not equal to val.

Let 
k
k
 represent the number of elements in nums that are not equal to val. To successfully solve this problem, you need to ensure the following:

Modify the array, nums, such that the first 
k
k
 elements contain values that are not equal to val.

The remaining elements in the array do not matter, and the size of nums is irrelevant after the first 
k
k
 elements.

Return the value of 
k
k
.

Constraints:

0
≤
0≤
 nums.length 
≤
100
≤100

0
≤
0≤
 nums[i] 
≤
50
≤50

0
≤
0≤
 val 
≤
100
≤100

def removeElement(nums, val):
    k = 0  
    
    for j in range(len(nums)):
        if nums[j] != val:
            nums[k] = nums[j]
            k += 1


    return k

##20

Problem: Rotate Array
med
30 min
Understand how to apply the two pointers technique to rotate an integer array to the right by a given number of steps. This lesson helps you solve array rotation problems efficiently, reinforcing pattern recognition and algorithm implementation skills in Python.
Statement
Given an integer array, nums, shift its elements to the right by k positions. In other words, rotate the array to the right by k steps, where k is non-negative.

Constraints:

1
≤
1≤
 nums.length 
≤
1
0
3
≤10 
3
 

−
2
−
31
≤
−2 
−31
 ≤
 nums[i] 
2
31
−
1
2 
31
 −1

0
≤
0≤
 k 
≤
1
0
3
≤10 
3

def rotate(nums, k):
    n = len(nums)

    # If k is greater than the array length, only the remainder of k rotations matters
    k = k % n

    # Helper function to reverse a portion of the array
    def reverse(left, right):
        while left < right:
            # Swap the elements at left and right
            nums[left], nums[right] = nums[right], nums[left]

            # Move the pointers toward the center
            left += 1
            right -= 1

    # Step 1: Reverse the entire array
    reverse(0, n - 1)

    # Step 2: Reverse the first k elements
    reverse(0, k - 1)

    # Step 3: Reverse the remaining elements
    reverse(k, n - 1)

##21

Problem: Next Permutation
med
30 min
Explore how to find the next lexicographically greater permutation of an array by applying a two-pointer technique. Understand in-place rearrangement strategies and improve your problem-solving skills for coding interviews focused on array manipulation.
Statement
Your task is to rearrange an array, nums, containing positive integers to form the next lexicographically greater permutation. This means finding the next permutation in the sequence of all possible arrangements sorted in dictionary order.

For example, given the array 
[
4
,
5
,
6
]
[4,5,6]
, the next permutation is 
[
4
,
6
,
5
]
[4,6,5]
. In the same way, 
[
5
,
6
,
4
]
[5,6,4]
 becomes 
[
6
,
4
,
5
]
[6,4,5]
.

If the array is already in its highest possible order (sorted in descending order), such as 
[
6
,
5
,
4
]
[6,5,4]
, it’s not possible to find a lexicographically larger permutation. In this case, you must rearrange the array to its lowest possible order (sorted in ascending order), which would be 
[
4
,
5
,
6
]
[4,5,6]
.

The entire operation must be completed in-place while using only a constant amount of extra memory.

Constraints:

1
≤
1≤
 nums.length 
≤
100
≤100

0
≤
0≤
 nums[i] 
≤
100
≤100


def nextPermutation(nums):
    n = len(nums)

    # Find the pivot:

    i = n - 2

    while i >= 0 and nums[i] >= nums[i + 1]:
        i -= 1

    # 2. If pivot exists, find the smallest number from the right that is bigger than nums[i]
    if i >= 0:
        j = n - 1

        while nums[j] <= nums[i]:
            j -= 1

        # Swap pivot with that no
        nums[i], nums[j] = nums[j], nums[i]

    # 3. Reverse everything after the pivot,  This makes the suffix as small as possible
    left = i + 1
    right = n - 1

    while left < right:
        nums[left], nums[right] = nums[right], nums[left]
        left += 1
        right -= 1

    return nums


##22



