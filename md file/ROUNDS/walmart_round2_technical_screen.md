# Walmart AI/ML Engineer - Round 2: Technical Phone Screen
## Complete DSA Problem Bank with Solutions & Approach

**Duration:** 60 minutes
**Format:** Live coding on CoderPad/HackerRank with an engineer
**Difficulty:** Medium
**Problems:** 1-2 LeetCode Medium level problems
**Pass Rate:** ~50%

---

## 🎯 WHAT IS ROUND 2?

This is your first **real coding interview**. You'll write code in a shared editor while being watched by an engineer. They'll observe:
- How you think
- How you communicate
- Code quality
- Problem-solving approach
- Handling of edge cases
- Time complexity awareness

---

## ⏰ TIME BREAKDOWN (60 minutes)

```
Introduction & Problem Explanation:  3-5 minutes
  ├─ Greeter
  ├─ Problem description
  └─ Asking clarifying questions

Problem Solving & Coding:           40-45 minutes
  ├─ Problem 1: 25-30 min
  └─ Problem 2: 15-20 min

Discussion & Follow-up:              10-15 minutes
  ├─ Complexity analysis
  ├─ Trade-offs
  ├─ Follow-up questions
  └─ Feedback
```

---

## 🎨 APPROACH TO EVERY PROBLEM

### Step 1: CLARIFY (2-3 min)
Never start coding immediately!

**Ask These Questions:**
- "Can I clarify the problem? So we need to [repeat problem in your words]?"
- "What's the size of input? (constraints like N ≤ 10^5)"
- "What about edge cases? (empty input, single element, negatives, duplicates)"
- "Can I modify the input array/structure?"
- "What should I return exactly?"

**Example:**
```
Interviewer: "Given an array of integers, find two numbers that add up to a target."
You: "Got it. So we have an array of integers and a target number. 
     We need to find TWO numbers that sum to the target. 
     Can there be duplicates? What's the max size of the array? 
     Can I use extra space? Should I return indices or values?"
```

### Step 2: THINK OUT LOUD (3-5 min)
Explain your approach before coding!

**Say This:**
"Let me think about this. My initial approach would be:
1. [Brute force explanation]
2. Time complexity: O(n²), Space: O(1)

But we can optimize this:
1. [Optimized approach]
2. Time complexity: O(n), Space: O(n)

Let me code the optimized solution using a hash map..."

### Step 3: CODE CLEANLY (20-25 min)
- Write readable code with good variable names
- Add comments for complex logic
- Test as you go
- Don't worry about perfection - focus on correctness

### Step 4: TEST (5-10 min)
**Always test with examples:**
- Simple/normal case
- Edge cases (empty, single element, min, max)
- Special cases (duplicates, negatives, zeros)

### Step 5: EXPLAIN COMPLEXITY (2-3 min)
"Time complexity: O(n) because we iterate through the array once.
Space complexity: O(n) for the hash map storing up to n elements."

### Step 6: OPTIMIZE IF TIME (5 min)
"Could we improve this further? What are the trade-offs?"

---

## 🎯 TOP 20 PROBLEMS WALMART ACTUALLY ASKS

### **ARRAYS & STRINGS (4 problems)**

---

### **Problem 1: Two Sum** ⭐ Very Common

**Difficulty:** Easy-Medium
**Topics:** Hash Map, Two Pointers

**Problem Statement:**
```
Given an array of integers nums and an integer target, 
return the indices of the two numbers that add up to target.

You may assume each input has exactly one solution, 
and you cannot use the same element twice.

Example 1:
Input: nums = [2, 7, 11, 15], target = 9
Output: [0, 1]
Explanation: nums[0] + nums[1] == 9, so we return [0, 1]

Example 2:
Input: nums = [3, 2, 4], target = 6
Output: [1, 2]

Constraints:
- 2 <= nums.length <= 10^4
- -10^9 <= nums[i] <= 10^9
- -10^9 <= target <= 10^9
```

**Approach 1: Brute Force (Don't use in interview)**
```
For each number, check all other numbers to find the pair.
Time: O(n²), Space: O(1)
```

**Approach 2: Hash Map (Optimal) ✅**
```
Use a hash map to store (number -> index)
As we iterate, check if (target - current_num) exists in map.

Intuition: If target = 9 and current = 2, we need 7.
Check: does 7 exist in our map?
```

**Solution:**
```python
def twoSum(nums, target):
    """
    Find two numbers that add up to target.
    
    Args:
        nums: List of integers
        target: Target sum
        
    Returns:
        List of indices [i, j] where nums[i] + nums[j] == target
    """
    # Hash map to store number -> index
    num_map = {}
    
    for i, num in enumerate(nums):
        # Check if complement exists
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]
        
        # Store current number and its index
        num_map[num] = i
    
    return []  # No solution found


# Test cases
print(twoSum([2, 7, 11, 15], 9))      # [0, 1]
print(twoSum([3, 2, 4], 6))           # [1, 2]
print(twoSum([3, 3], 6))              # [0, 1]
print(twoSum([1, 2, 3], 10))          # []
```

**Complexity Analysis:**
```
Time:  O(n) - single pass through array
Space: O(n) - hash map stores up to n elements
```

**Follow-up Questions (Likely to be asked):**

Q1: "What if no solution exists?"
A: "Return empty list or [-1, -1] depending on requirements"

Q2: "What if there are duplicates?"
A: "The hash map will overwrite, but since we process left-to-right, 
    we'll find the first valid pair"

Q3: "Can we do it in-place with O(1) space?"
A: "Not for unsorted array. But if array is sorted, we can use two pointers:
    - Start pointer at beginning (small)
    - End pointer at end (large)
    - If sum < target, move left pointer right
    - If sum > target, move right pointer left
    Time: O(n), Space: O(1)"

---

### **Problem 2: Longest Substring Without Repeating Characters**

**Difficulty:** Medium
**Topics:** Sliding Window, Hash Map

**Problem Statement:**
```
Given a string s, find the length of the longest substring 
without repeating characters.

Example 1:
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with length 3

Example 2:
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with length 1

Example 3:
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with length 3

Constraints:
- 0 <= s.length <= 5 * 10^4
- s consists of English letters, digits, symbols and spaces
```

**Approach: Sliding Window**
```
Use two pointers (left, right) to create a window.
Track characters in window with a hash map.
When we find a duplicate:
  - Shrink window from left until duplicate is removed
  - Update the position of the duplicate character
Keep track of max window size seen so far.
```

**Solution:**
```python
def lengthOfLongestSubstring(s):
    """
    Find length of longest substring without repeating characters.
    
    Args:
        s: Input string
        
    Returns:
        Length of longest substring without repeating characters
    """
    # Character to its most recent index
    char_index = {}
    max_length = 0
    left = 0  # Left pointer of sliding window
    
    for right in range(len(s)):
        # If character is already in current window
        if s[right] in char_index and char_index[s[right]] >= left:
            # Move left pointer to exclude the previous occurrence
            left = char_index[s[right]] + 1
        
        # Update character's most recent index
        char_index[s[right]] = right
        
        # Update max length
        max_length = max(max_length, right - left + 1)
    
    return max_length


# Test cases
print(lengthOfLongestSubstring("abcabcbb"))   # 3 ("abc")
print(lengthOfLongestSubstring("bbbbb"))      # 1 ("b")
print(lengthOfLongestSubstring("pwwkew"))     # 3 ("wke")
print(lengthOfLongestSubstring("au"))         # 2 ("au")
print(lengthOfLongestSubstring(""))           # 0
print(lengthOfLongestSubstring("abcdefg"))    # 7
```

**Trace Example: s = "abcabcbb"**
```
Index: 0 1 2 3 4 5 6 7
Char:  a b c a b c b b

Step-by-step:
right=0, char='a': char_index={'a':0}, left=0, length=1, max_length=1
right=1, char='b': char_index={'a':0,'b':1}, left=0, length=2, max_length=2
right=2, char='c': char_index={'a':0,'b':1,'c':2}, left=0, length=3, max_length=3
right=3, char='a': 'a' at index 0 >= left (0), so left=1
        char_index={'a':3,'b':1,'c':2}, length=3, max_length=3
right=4, char='b': 'b' at index 1 >= left (1), so left=2
        char_index={'a':3,'b':4,'c':2}, length=3, max_length=3
right=5, char='c': 'c' at index 2 >= left (2), so left=3
        char_index={'a':3,'b':4,'c':5}, length=3, max_length=3
right=6, char='b': 'b' at index 4 >= left (3), so left=5
        char_index={'a':3,'b':6,'c':5}, length=2, max_length=3
right=7, char='b': 'b' at index 6 >= left (5), so left=7
        char_index={'a':3,'b':7,'c':5}, length=1, max_length=3

Result: 3
```

**Complexity:**
```
Time:  O(n) - each character visited at most twice
Space: O(min(m, n)) - hash map size, m=charset size, n=string length
```

---

### **Problem 3: Valid Parentheses**

**Difficulty:** Easy
**Topics:** Stack

**Problem Statement:**
```
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']',
determine if the input string is valid.

An input string is valid if:
1. Open brackets must be closed by the same type of closing bracket.
2. Open brackets must be closed in the correct order.

Example 1:
Input: s = "()"
Output: true

Example 2:
Input: s = "()[]{}"
Output: true

Example 3:
Input: s = "(]"
Output: false

Example 4:
Input: s = "([)]"
Output: false

Example 5:
Input: s = "{[]}"
Output: true
```

**Approach: Stack**
```
Use a stack to track opening brackets.
For each character:
  - If opening bracket: push to stack
  - If closing bracket: 
    - Check if stack is empty (invalid)
    - Check if top of stack matches (invalid if not)
    - Pop from stack if match
At end, stack should be empty.
```

**Solution:**
```python
def isValid(s):
    """
    Check if string with brackets is valid.
    
    Args:
        s: String containing brackets
        
    Returns:
        True if valid, False otherwise
    """
    # Mapping of closing to opening brackets
    bracket_map = {')': '(', '}': '{', ']': '['}
    stack = []
    
    for char in s:
        if char in bracket_map:
            # It's a closing bracket
            # Check if stack is empty or top doesn't match
            if not stack or stack[-1] != bracket_map[char]:
                return False
            stack.pop()
        else:
            # It's an opening bracket
            stack.append(char)
    
    # Valid only if stack is empty (all brackets matched)
    return len(stack) == 0


# Test cases
print(isValid("()"))          # True
print(isValid("()[]{}"))      # True
print(isValid("(]"))          # False
print(isValid("([)]"))        # False
print(isValid("{[]}"))        # True
print(isValid(""))            # True
print(isValid("("))           # False
print(isValid(")"))           # False
```

**Complexity:**
```
Time:  O(n) - single pass through string
Space: O(n) - stack in worst case (all opening brackets)
```

---

### **Problem 4: Group Anagrams**

**Difficulty:** Medium
**Topics:** Hash Map, String

**Problem Statement:**
```
Given an array of strings strs, group the anagrams together.

An anagram is a word or phrase formed by rearranging the letters 
of a different word or phrase, using all the original letters exactly once.

Example 1:
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]

Example 2:
Input: strs = [""]
Output: [[""]]

Example 3:
Input: strs = ["a"]
Output: [["a"]]
```

**Approach 1: Sorted Key**
```
Anagrams have the same letters, so sorting gives same result.
Key idea: sorted("eat") = "aet" = sorted("tea")
Use hash map with sorted word as key.
```

**Approach 2: Character Count Key**
```
Count frequency of each character.
Use character counts as key: (a:1, e:1, t:1)
This is more efficient than sorting.
```

**Solution (Character Count Approach - Better):**
```python
def groupAnagrams(strs):
    """
    Group anagrams together.
    
    Args:
        strs: List of strings
        
    Returns:
        List of lists where each inner list contains anagrams
    """
    # Hash map: character count -> list of anagrams
    anagram_groups = {}
    
    for word in strs:
        # Create a key based on character frequency
        # Using sorted() is simpler but less efficient
        # Better: use character count tuple
        
        # Method 1: Sort (simpler to code)
        key = ''.join(sorted(word))
        
        # Method 2: Character count (more efficient)
        # char_count = [0] * 26
        # for char in word:
        #     char_count[ord(char) - ord('a')] += 1
        # key = tuple(char_count)
        
        if key not in anagram_groups:
            anagram_groups[key] = []
        anagram_groups[key].append(word)
    
    return list(anagram_groups.values())


# Test cases
print(groupAnagrams(["eat","tea","tan","ate","nat","bat"]))
# Output: [["eat","tea","ate"],["tan","nat"],["bat"]]

print(groupAnagrams([""]))
# Output: [[""]]

print(groupAnagrams(["a"]))
# Output: [["a"]]
```

**Complexity:**
```
Method 1 (Sorted):
Time:  O(n * k * log(k)) where n=num strings, k=max string length
Space: O(n * k) for hash map

Method 2 (Character Count):
Time:  O(n * k) where n=num strings, k=max string length
Space: O(n * k) for hash map
```

---

## 🌳 TREES & GRAPHS (4 problems)

---

### **Problem 5: Binary Tree Level Order Traversal**

**Difficulty:** Medium
**Topics:** Tree, BFS, Queue

**Problem Statement:**
```
Given the root of a binary tree, return the level order traversal of its nodes' values. 
(i.e., from left to right, level by level).

Example 1:
Input: root = [3,9,20,null,null,15,7]
Output: [[3],[9,20],[15,7]]

Tree structure:
    3
   / \
  9  20
    /  \
   15   7

Example 2:
Input: root = [1]
Output: [[1]]

Example 3:
Input: root = []
Output: []
```

**Approach: BFS with Queue**
```
Use a queue to process nodes level by level.
For each level:
  1. Get current queue size (number of nodes at this level)
  2. Process all nodes in queue
  3. Add their children to queue for next level
```

**Solution:**
```python
from collections import deque

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def levelOrder(root):
    """
    Return level order traversal of binary tree.
    
    Args:
        root: TreeNode - root of binary tree
        
    Returns:
        List[List[int]] - nodes at each level
    """
    if not root:
        return []
    
    result = []
    queue = deque([root])
    
    while queue:
        level_size = len(queue)  # Number of nodes at current level
        current_level = []
        
        # Process all nodes at current level
        for _ in range(level_size):
            node = queue.popleft()
            current_level.append(node.val)
            
            # Add children to queue for next level
            if node.left:
                queue.append(node.left)
            if node.right:
                queue.append(node.right)
        
        result.append(current_level)
    
    return result


# Test case
#     3
#    / \
#   9  20
#     /  \
#    15   7

root = TreeNode(3)
root.left = TreeNode(9)
root.right = TreeNode(20)
root.right.left = TreeNode(15)
root.right.right = TreeNode(7)

print(levelOrder(root))  # [[3], [9, 20], [15, 7]]
```

**Complexity:**
```
Time:  O(n) - visit each node once
Space: O(w) - w is max width (queue size at widest level)
```

---

### **Problem 6: Number of Islands**

**Difficulty:** Medium
**Topics:** Graph, DFS/BFS, Matrix

**Problem Statement:**
```
Given an m x n 2D binary grid grid which represents a map of '1's (land) and '0's (water),
return the number of islands.

An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically.
You may assume all four edges of the grid are surrounded by water.

Example 1:
Input: grid = [
  ["1","1","1","1","0"],
  ["1","1","0","1","0"],
  ["1","1","0","0","0"],
  ["0","0","0","0","0"]
]
Output: 1

Example 2:
Input: grid = [
  ["1","1","0","0","0"],
  ["1","1","0","0","0"],
  ["0","0","1","0","0"],
  ["0","0","0","1","1"]
]
Output: 3
```

**Approach: DFS**
```
For each unvisited land cell ('1'):
  1. Increment island count
  2. Do DFS to mark all connected land as visited
  3. Continue to next unvisited cell

DFS explores all 4 directions (up, down, left, right).
```

**Solution:**
```python
def numIslands(grid):
    """
    Count number of islands in grid.
    
    Args:
        grid: List[List[str]] - 2D grid with '1' (land) and '0' (water)
        
    Returns:
        int - number of islands
    """
    if not grid or not grid[0]:
        return 0
    
    def dfs(r, c):
        """Mark all connected land as visited using DFS."""
        # Base cases: out of bounds or water
        if r < 0 or r >= len(grid) or c < 0 or c >= len(grid[0]) or grid[r][c] == '0':
            return
        
        # Mark as visited
        grid[r][c] = '0'
        
        # Explore all 4 directions
        dfs(r + 1, c)  # Down
        dfs(r - 1, c)  # Up
        dfs(r, c + 1)  # Right
        dfs(r, c - 1)  # Left
    
    island_count = 0
    
    for r in range(len(grid)):
        for c in range(len(grid[0])):
            if grid[r][c] == '1':
                island_count += 1
                dfs(r, c)  # Mark entire island as visited
    
    return island_count


# Test cases
grid1 = [
    ["1","1","1","1","0"],
    ["1","1","0","1","0"],
    ["1","1","0","0","0"],
    ["0","0","0","0","0"]
]
print(numIslands(grid1))  # 1

grid2 = [
    ["1","1","0","0","0"],
    ["1","1","0","0","0"],
    ["0","0","1","0","0"],
    ["0","0","0","1","1"]
]
print(numIslands(grid2))  # 3
```

**Complexity:**
```
Time:  O(m * n) - visit each cell once
Space: O(m * n) - recursion stack in worst case
```

---

### **Problem 7: Binary Search Tree Validation**

**Difficulty:** Medium
**Topics:** Tree, DFS, BST

**Problem Statement:**
```
Given the root of a binary tree, determine if it is a valid binary search tree (BST).

A valid BST is defined as follows:
- The left subtree of a node contains only nodes with keys less than the node's key.
- The right subtree of a node contains only nodes with keys greater than the node's key.
- Both left and right subtrees must also be binary search trees.

Example 1:
Input: root = [2,1,3]
Output: true

Example 2:
Input: root = [5,1,4,null,null,3,6]
Output: false
Explanation: The root node's value is 5 but its right child's value is 4.
```

**Approach: Track Min/Max Bounds**
```
For each node, track valid range:
- Root can be anything
- Left child must be: min < value < node.val
- Right child must be: node.val < value < max

Pass valid bounds down the tree.
```

**Solution:**
```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def isValidBST(root):
    """
    Validate if binary tree is a valid BST.
    
    Args:
        root: TreeNode - root of binary tree
        
    Returns:
        bool - True if valid BST, False otherwise
    """
    def validate(node, lower_bound, upper_bound):
        """
        Validate subtree with given bounds.
        
        Args:
            node: Current node
            lower_bound: Minimum valid value for this node
            upper_bound: Maximum valid value for this node
            
        Returns:
            bool - True if subtree is valid BST
        """
        if not node:
            return True
        
        # Check if node violates bounds
        if node.val <= lower_bound or node.val >= upper_bound:
            return False
        
        # Left subtree: values must be between lower_bound and node.val
        # Right subtree: values must be between node.val and upper_bound
        return (validate(node.left, lower_bound, node.val) and
                validate(node.right, node.val, upper_bound))
    
    return validate(root, float('-inf'), float('inf'))


# Test cases
#   2
#  / \
# 1   3
root1 = TreeNode(2)
root1.left = TreeNode(1)
root1.right = TreeNode(3)
print(isValidBST(root1))  # True

#   5
#  / \
# 1   4
#    / \
#   3   6
root2 = TreeNode(5)
root2.left = TreeNode(1)
root2.right = TreeNode(4)
root2.right.left = TreeNode(3)
root2.right.right = TreeNode(6)
print(isValidBST(root2))  # False (4 is invalid right child of 5)
```

**Complexity:**
```
Time:  O(n) - visit each node once
Space: O(h) - recursion stack, h is height
```

---

### **Problem 8: Word Ladder**

**Difficulty:** Hard
**Topics:** Graph, BFS

**Problem Statement:**
```
Given two words, beginWord and endWord, and a dictionary wordList, 
return the number of words in the shortest transformation sequence 
from beginWord to endWord, or 0 if no such sequence exists.

You must change exactly one letter in each step, 
and each transformed word must exist in the word list.

Example 1:
Input: beginWord = "hit", endWord = "cog", wordList = ["hot","dot","dog","lot","log","cog"]
Output: 5
Explanation: One shortest transformation sequence is 
"hit" -> "hot" -> "dot" -> "dog" -> "cog", which is 5 words long.

Example 2:
Input: beginWord = "hit", endWord = "cog", wordList = ["hot","dot","dog","lot","log"]
Output: 0
Explanation: The endWord "cog" is not in wordList, therefore there is no valid transformation sequence.
```

**Approach: BFS**
```
Build graph where nodes are words, edges connect words 1 letter apart.
Use BFS from beginWord to find shortest path to endWord.

Optimization: Instead of checking all words, generate neighbors by
changing one letter at a time.
```

**Solution:**
```python
from collections import deque, defaultdict

def ladderLength(beginWord, endWord, wordList):
    """
    Find shortest transformation sequence length from beginWord to endWord.
    
    Args:
        beginWord: Starting word
        endWord: Target word
        wordList: List of allowed words
        
    Returns:
        int - length of shortest sequence, or 0 if impossible
    """
    # Early exit if endWord not in wordList
    if endWord not in wordList:
        return 0
    
    # Convert to set for O(1) lookup
    wordSet = set(wordList)
    
    # BFS
    queue = deque([(beginWord, 1)])  # (current_word, distance)
    visited = {beginWord}
    
    while queue:
        current_word, distance = queue.popleft()
        
        # If we reached the end word
        if current_word == endWord:
            return distance
        
        # Generate all neighbors (words 1 letter different)
        for neighbor in get_neighbors(current_word, wordSet):
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append((neighbor, distance + 1))
    
    return 0  # No path found


def get_neighbors(word, wordSet):
    """Get all words that differ by exactly one letter."""
    neighbors = []
    
    for i in range(len(word)):
        for c in 'abcdefghijklmnopqrstuvwxyz':
            if c != word[i]:  # Different letter
                neighbor = word[:i] + c + word[i+1:]
                if neighbor in wordSet:
                    neighbors.append(neighbor)
    
    return neighbors


# Test cases
print(ladderLength("hit", "cog", ["hot","dot","dog","lot","log","cog"]))  # 5
print(ladderLength("hit", "cog", ["hot","dot","dog","lot","log"]))        # 0
```

**Complexity:**
```
Time:  O(N * L * 26) where N = wordList length, L = word length
Space: O(N * L) for visited set and queue
```

---

## 🔗 LINKED LISTS (2 problems)

---

### **Problem 9: Reverse Linked List**

**Difficulty:** Easy
**Topics:** Linked List

**Problem Statement:**
```
Given the head of a singly linked list, reverse the list, and return the reversed list.

Example 1:
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]

Example 2:
Input: head = [1,2]
Output: [2,1]

Example 3:
Input: head = []
Output: []
```

**Approach: Iterative**
```
Use three pointers: prev, current, next
Traverse and reverse links:
  1. Save next node
  2. Reverse current node's link
  3. Move prev and current forward
```

**Solution:**
```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def reverseList(head):
    """
    Reverse a singly linked list iteratively.
    
    Args:
        head: ListNode - head of the list
        
    Returns:
        ListNode - head of reversed list
    """
    prev = None
    current = head
    
    while current:
        # Save next node
        next_temp = current.next
        
        # Reverse the link
        current.next = prev
        
        # Move pointers forward
        prev = current
        current = next_temp
    
    return prev  # New head


# Test case: 1 -> 2 -> 3 -> None
head = ListNode(1)
head.next = ListNode(2)
head.next.next = ListNode(3)

reversed_head = reverseList(head)
# reversed_head: 3 -> 2 -> 1 -> None
```

**Complexity:**
```
Time:  O(n) - visit each node once
Space: O(1) - only use pointers
```

---

### **Problem 10: Merge Two Sorted Lists**

**Difficulty:** Easy
**Topics:** Linked List

**Problem Statement:**
```
You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists into one sorted list. The list should be made by splicing 
together the nodes of the two lists.

Return the head of the merged linked list.

Example 1:
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]

Example 2:
Input: list1 = [], list2 = []
Output: []

Example 3:
Input: list1 = [], list2 = [0]
Output: [0]
```

**Approach: Two Pointers**
```
Use two pointers to traverse both lists.
Compare nodes and append smaller to result.
Handle remaining nodes after one list is exhausted.
```

**Solution:**
```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def mergeTwoLists(list1, list2):
    """
    Merge two sorted linked lists.
    
    Args:
        list1: First sorted linked list
        list2: Second sorted linked list
        
    Returns:
        ListNode - head of merged sorted list
    """
    # Create dummy node to simplify logic
    dummy = ListNode(0)
    current = dummy
    
    # Traverse both lists
    while list1 and list2:
        if list1.val <= list2.val:
            current.next = list1
            list1 = list1.next
        else:
            current.next = list2
            list2 = list2.next
        current = current.next
    
    # Attach remaining nodes
    if list1:
        current.next = list1
    if list2:
        current.next = list2
    
    return dummy.next


# Test case: [1,2,4] and [1,3,4]
list1 = ListNode(1)
list1.next = ListNode(2)
list1.next.next = ListNode(4)

list2 = ListNode(1)
list2.next = ListNode(3)
list2.next.next = ListNode(4)

merged = mergeTwoLists(list1, list2)
# Output: 1 -> 1 -> 2 -> 3 -> 4 -> 4
```

**Complexity:**
```
Time:  O(n + m) - visit each node once
Space: O(1) - only use pointers
```

---

## 🔌 OTHER MEDIUM PROBLEMS (Likely at Walmart)

---

### **Problem 11: Rotate Array**

**Difficulty:** Medium
**Topics:** Array, Two Pointers

**Problem Statement:**
```
Given an integer array nums, rotate the array to the right by k steps,
where k is non-negative.

Example 1:
Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]

Example 2:
Input: nums = [-1,-100,3,99], k = 2
Output: [99,-100,-1,3]

Follow-up: Try to come up with as many solutions as you can.
There are at least three different ways to solve this problem.
Constraints:
- 1 <= nums.length <= 10^5
- -2^31 <= nums[i] <= 2^31 - 1
- 0 <= k <= 10^5
```

**Approach: Array Reversal (Most Efficient)**
```
Key insight: rotating k steps = reversing three parts
1. Reverse entire array
2. Reverse first k elements
3. Reverse remaining elements

Example: [1,2,3,4,5] rotate by 2
Step 1: Reverse all: [5,4,3,2,1]
Step 2: Reverse [5,4]: [4,5,3,2,1]
Step 3: Reverse [3,2,1]: [4,5,1,2,3]
```

**Solution:**
```python
def rotate(nums, k):
    """
    Rotate array to the right by k steps in-place.
    
    Args:
        nums: List to rotate (modified in-place)
        k: Number of steps to rotate
    """
    # Handle k > length
    k = k % len(nums)
    
    if k == 0:
        return
    
    def reverse(start, end):
        while start < end:
            nums[start], nums[end] = nums[end], nums[start]
            start += 1
            end -= 1
    
    # Reverse entire array
    reverse(0, len(nums) - 1)
    # Reverse first k elements
    reverse(0, k - 1)
    # Reverse remaining elements
    reverse(k, len(nums) - 1)


# Test cases
nums1 = [1,2,3,4,5,6,7]
rotate(nums1, 3)
print(nums1)  # [5,6,7,1,2,3,4]

nums2 = [-1,-100,3,99]
rotate(nums2, 2)
print(nums2)  # [99,-100,-1,3]
```

**Complexity:**
```
Time:  O(n) - three passes through array
Space: O(1) - in-place, no extra space
```

---

### **Problem 12: Median of Two Sorted Arrays**

**Difficulty:** Hard ⭐
**Topics:** Binary Search, Array

**Problem Statement:**
```
Given two sorted arrays nums1 and nums2 of size m and n respectively,
return the median of the two sorted arrays.

The overall run time complexity should be O(log(min(m,n))).

Example 1:
Input: nums1 = [1,3], nums2 = [2]
Output: 2.0
Explanation: merged array = [1,2,3] and median is 2.0.

Example 2:
Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.5
Explanation: merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.
```

**Approach: Binary Search on Smaller Array**
```
Key insight: median is the point that splits arrays into left and right halves.
Binary search on the smaller array to find correct partition.
```

**Solution (Complex - Know conceptually):**
```python
def findMedianSortedArrays(nums1, nums2):
    """
    Find median of two sorted arrays.
    
    Args:
        nums1: First sorted array
        nums2: Second sorted array
        
    Returns:
        float - median of merged arrays
    """
    # Ensure nums1 is smaller (for binary search)
    if len(nums1) > len(nums2):
        nums1, nums2 = nums2, nums1
    
    low, high = 0, len(nums1)
    
    while low <= high:
        partition1 = (low + high) // 2
        partition2 = (len(nums1) + len(nums2) + 1) // 2 - partition1
        
        # Handle edge cases
        left1 = float('-inf') if partition1 == 0 else nums1[partition1 - 1]
        left2 = float('-inf') if partition2 == 0 else nums2[partition2 - 1]
        right1 = float('inf') if partition1 == len(nums1) else nums1[partition1]
        right2 = float('inf') if partition2 == len(nums2) else nums2[partition2]
        
        # Check if valid partition
        if left1 <= right2 and left2 <= right1:
            total = len(nums1) + len(nums2)
            if total % 2 == 0:
                return (max(left1, left2) + min(right1, right2)) / 2
            else:
                return max(left1, left2)
        elif left1 > right2:
            high = partition1 - 1
        else:
            low = partition1 + 1
```

**Complexity:**
```
Time:  O(log(min(m, n)))
Space: O(1)
```

---

## 🎯 HOW TO PRACTICE FOR ROUND 2

### **Daily Practice Routine (30 days)**

```
Week 1: Easy Problems (Build Confidence)
- Two Sum, Valid Parentheses, Reverse Linked List
- Do 3-4 per day, full solutions

Week 2: Medium Problems (Build Speed)
- Longest Substring, Number of Islands, Level Order
- Do 2-3 per day, aim for <30 min per problem

Week 3: Mixed Difficulty (Build Depth)
- Combine easy + medium
- Do mock interviews
- Practice explaining solutions

Week 4: Hard Problems + Mock Interviews
- Median of Two Sorted Arrays, Word Ladder
- Do 3-4 full mock interviews
- Get feedback on communication
```

### **Resources**

```
LeetCode: Medium problems
- https://leetcode.com/explore/interview/card/top-interview-questions/

GeeksforGeeks: DSA tutorials
- https://www.geeksforgeeks.org/

InterviewBit: Guided learning paths
- https://www.interviewbit.com/courses/programming/

Pramp: Free mock interviews
- https://www.pramp.com/
```

---

## ✅ ROUND 2 SUCCESS CHECKLIST

### **Before the Interview**
- [ ] Practice 40-50 LeetCode problems
- [ ] Do 3-4 mock interviews with real people
- [ ] Test your CoderPad/HackerRank setup
- [ ] Know time/space complexity analysis cold
- [ ] Practice explaining solutions out loud

### **During the Interview**
- [ ] Clarify problem with examples (2-3 min)
- [ ] Think out loud about approach (3-5 min)
- [ ] Code cleanly with comments (20-25 min)
- [ ] Test with examples including edge cases (5-10 min)
- [ ] Explain time/space complexity (2-3 min)
- [ ] Ask follow-up questions if given time

### **Communication Tips**
- [ ] Speak at normal pace, not too fast
- [ ] Explain "why" not just "what"
- [ ] Ask for clarification when unsure
- [ ] Think out loud (silence is bad)
- [ ] Code while explaining
- [ ] Test as you code

---

## ❌ COMMON MISTAKES IN ROUND 2

| Mistake | Impact | Fix |
|---------|--------|-----|
| **Jump to coding** | Wrong solution | Ask clarifying questions first |
| **No edge case testing** | Fails on test cases | Always test: empty, single, duplicates |
| **Wrong complexity** | Shows weak understanding | Practice calculating O(n) vs O(n²) |
| **Messy code** | Hard to read, errors | Use clear variable names |
| **Silence/Not thinking aloud** | Interviewer can't follow | Constantly explain your approach |
| **Not optimizing** | Misses optimization chance | Always ask "Can we do better?" |
| **Running out of time** | Incomplete solution | Practice speed, use templates |
| **Off-by-one errors** | Wrong answer | Test boundaries carefully |

---

## 🚀 WHAT HAPPENS AFTER ROUND 2

**If you pass:**
- Typically 1-2 weeks before Round 3 (coding onsite)
- Expect similar difficulty or slightly harder

**If you fail:**
- Usually no second chance immediately
- Can apply again after 6-12 months
- Learn from feedback if given

**Pass rate:** ~50%
**Common reason for failure:** Couldn't optimize solution, poor communication, edge case bugs

---

## 💡 FINAL TIPS FOR ROUND 2

✅ **Practice with someone watching**
- Mock interviews matter more than solo practice
- You need feedback on communication

✅ **Master one language deeply**
- Python, Java, or C++ (Python easiest)
- Know the libraries: collections, heapq, etc.

✅ **Know common patterns**
- Two pointers, sliding window, hash map
- DFS/BFS, binary search
- You'll see these patterns in 80% of problems

✅ **Time yourself**
- Aim to solve medium in <30 min
- Include testing and explanation

✅ **Learn from mistakes**
- After each problem, understand where you struggled
- Practice similar patterns

---

## 🎬 SAMPLE ROUND 2 WALKTHROUGH

**Interviewer:** "Hi! Let's start with a problem. Given an array of integers and a target, find two numbers that add up to the target."

**You:** "Got it. A few clarifying questions:
1. Can I modify the array?
2. Can there be duplicates?
3. Should I return indices or values?
4. What if no solution exists?"

**Interviewer:** "Return indices, array has no duplicates, no solution returns empty array."

**You:** "Got it. My approach: I'll use a hash map to store numbers I've seen with their indices. As I iterate, I check if the complement (target - current) exists.

Complexity would be O(n) time and O(n) space.

Let me code this..."

[You start coding cleanly]

"I'm using a dictionary to track numbers. For each number, I check if complement exists, then store the number for future lookups..."

[You test with examples]

"Let me test: [2,7,11,15], target 9. 
- Index 0, num 2: complement 7 not in map. Add 2->0
- Index 1, num 7: complement 2 is in map! Return [0, 1] ✓"

**Interviewer:** "Great! Can you think of any edge cases?"

**You:** "Empty array would return empty list. Single element would return empty. Duplicates - wait, you said no duplicates, so we're good."

**Interviewer:** "Nice! What's the space-time tradeoff here?"

**You:** "We're using O(n) space to achieve O(n) time. Alternative approach with O(1) space would be sorting + two pointers, but that's O(n log n) time. Our hash map approach is optimal."

**Interviewer:** "Perfect! Moving to problem 2..."

---

## 🎓 YOU NOW KNOW:

✅ The exact 12 most common Walmart problems
✅ Complete solutions with explanations
✅ How to approach each problem type
✅ Time/space complexity analysis
✅ Edge cases to consider
✅ Common mistakes to avoid
✅ Communication tips
✅ Practice strategy

**Next: Go solve 40-50 LeetCode problems with these approaches!** 💪
