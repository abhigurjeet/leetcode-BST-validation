# leetcode-BST-validation

## Problem link - [https://leetcode.com/problems/validate-binary-search-tree](https://leetcode.com/problems/validate-binary-search-tree)

## Solution - 
<pre>
        <code>
class Solution {
public:
    bool check(TreeNode* root, TreeNode* mini, TreeNode* maxi) {
        if (root == NULL)
            return true;
        if ((mini != NULL && root->val <= mini->val) || (maxi != NULL && root->val >= maxi->val))
            return false;
        return check(root->left, mini, root) &&check(root->right, root, maxi);  
    }
    bool isValidBST(TreeNode* root) {
        if (root->left == NULL && root->right == NULL)
            return true;        
        return check(root, NULL, NULL); 
    }
};
        </code>
</pre>
