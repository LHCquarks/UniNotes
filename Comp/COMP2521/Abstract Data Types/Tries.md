# Overview
Tries are efficient search tree data structures used to store strings. 

**Usage**
Tries are particularly effective for:
- storing strings in a dictionary
- autocomplete/auto-correct
- spell checking
- IP routing


- Tries are stored as trees where the root node is an empty string, and each letter in the string is a child of the previous letter (the first letter being a child of the root note)

- Each node's children share a common prefix 


- Average and Worst-Case Time complexity for searching for a string in the trie is O(m), where m is the length of the string.
- The `kth` level of the tree represents the `kth` character in the string (subsequent letters of string are children of a node)
- The end of a string is marked with a finishing node.

**Implementation Details**
- A trie is implemented using arrays of size 26 (one entry for each letter of the alphabet).
- Each array entry is an array, containing a children array, a finish bool, and the data associated with the string
- The end of a string is marked with a finishing node (a node where the finish bool is set to true)




