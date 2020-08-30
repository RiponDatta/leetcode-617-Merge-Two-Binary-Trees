# leetcode 617 - Merge Two Binary Trees

```C#
public static TreeNode MergeTrees(TreeNode t1, TreeNode t2)
{
    if (t1 == null) return t2;
    if (t2 == null) return t1;
    if (t1.left != null && t2.left != null)
        t1.left = MergeTrees(t1.left, t2.left);
    if (t1.right != null && t2.right != null)
        t1.right = MergeTrees(t1.right, t2.right);
    if (t1.left == null)
        t1.left = t2.left;
    if (t1.right == null)
        t1.right = t2.right;
    t1.val = t1.val + t2.val;
    return t1;
}
```
#### Complexity Analysis
* Time complexity : O(m). A total of m nodes need to be traversed. Here, m represents the minimum number of nodes from the two given trees.
* Space complexity : O(h). h is the height of the tree.
