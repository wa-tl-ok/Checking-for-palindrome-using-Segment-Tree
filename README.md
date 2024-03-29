# Checking-for-palindrome-using-Segment-Tree
Let us be given a string and some queries:

    First type: change string character with number x to a new one (c).
    Second type: check that the substring [l: r] is a palindrome.

This problem has many solutions and one of them is using a Segment Tree and hashes. 

Let's build a Segment Tree and at each node we will store the length, forward and reverse hash of the corresponding substring. To make change and search queries easier, we will add symbols to the string so that its length is 2^k. 

Build query: we will build Segment Tree from the bottom. I mean that if the string is of size n then vector<int> tree is 2*n. 
tree[1] contains the root of the tree and the first floor is tree[n:2*n-1]: each forward hash in it is equal to the reverse, and the length of the corresponding substring is 1. To fill other floors, just use the merge of two strings to get a new hash. 

Query of the first type: to update our segment tree, find (on the first floor) the index of the element you need to change, 
update this node and then simply climb up to the root, updating the current branch of the Segment Tree (usinge merge with hashes).

Query of the second type: to check a substring for a palindrome, it is enough to use merge for those substrings that are completely within the query limit in your Segment Tree. There will be logn such nodes.

! Total costs by time: qlog(n). The memory costs are also not large; you need to store two hashes and the length of the substring in each of the 4n nodes.
