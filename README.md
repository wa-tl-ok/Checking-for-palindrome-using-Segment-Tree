# Checking-for-palindrome-using-Segment-Tree
Let us be given a string and some queries:
First type: change string character with number x to a new one (c).
Second type: check that the substring [l: r] is a palindrome.

This problem has many solutions and one of them is using a Segment Tree and hashes. 

Let's build a Segment Tree and at each node we will store the length, forward and reverse hash of the corresponding substring. To make change and search queries easier, we will add symbols to the string so that its length is 2^k. 

