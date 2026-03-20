
| # Kth Smallest Integer in BST                        | implement iterative approach                                                               |
| ---------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| construct binary tree with pre and inorder traversal | i thought i could use visited approach but no its more like boundaries                     |
| max path sum                                         | i thought of trying to first memorise the paths.. instead try to just solve by calculating |


Tree DP Pattern:

1. dfs returns value to parent

2. ignore negative contributions

3. compute local answer (left + right + node)

4. maintain global max