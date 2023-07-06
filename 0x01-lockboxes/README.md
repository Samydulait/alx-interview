# 0x01 Lockboxes

Given a list of locked boxes, where each box is numbered sequentially from 0 to n - 1, the lockbox principle states that a box can be opened if there exists a key with the same number as the box. In other words, for box i, if there is a key i in any of the other boxes, the box can be opened.

To determine if all boxes can be opened, you can implement the canUnlockAll function following the provided prototype. The function should take the boxes list as input, where each box is represented as a sublist containing the keys it holds.

The function should perform a traversal of the boxes using a breadth-first search (BFS) algorithm. It starts with the first box (boxes[0]), which is initially unlocked. The BFS algorithm explores the boxes by examining the keys in each box and marking the corresponding boxes as visited.

The lockbox principle guides the traversal by ensuring that for each box, if there is a key i, the box i is marked as visited. The algorithm continues until all reachable boxes have been visited.

Finally, the function returns True if all boxes have been visited (indicating that all boxes can be opened), or False if there are any unvisited boxes.
