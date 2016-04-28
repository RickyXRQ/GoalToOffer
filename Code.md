#*Template*

# X. Problem Name

> The content of the Problem

要求： 中文版的题目的具体要求

## 1.Solution:
```C++
C++ code here
```
## 2.Analysis:
My analysis here.

# 一. 二叉树的深度

>输入一课二叉树，求该树的深度。从根结点到叶结点依次经过的节点（含根、叶结点）形成树的一条路径，最长路径的长度为树的深度。

## 1.Solution:
```C++
/*
struct TreeNode {
	int val;
	struct TreeNode *left;
	struct TreeNode *right;
	TreeNode(int x) :
			val(x), left(NULL), right(NULL) {
	}
};*/
class Solution {
public:
    int max(int a, int b)
    {
    	return a>b?a:b;    
    }
    int TreeDepth(TreeNode* pRoot)
    {
        if(pRoot == NULL)
            {
            	return 0;
        	}
        else return 1 + max(TreeDepth(pRoot->left),TreeDepth(pRoot->right));
    }
};
```

## 2.Analysis:
采用递归的思路，并且递归的逻辑为前序遍历。
我们知道递归的三个条件为：1.可以把要解决的问题转化为一个新问题，并且这个新问题的解决办法仍与原来的解决方法相同，只是所处理的对象有规律的递增或递减；2.可以应用这个转化过程使问题得到解决；3.必定要有一个明确的结束递归的条件。对于这道题，满足上述递归的三个条件对应的具体条件为：1.树中存在子树，可以先求子树的深度；2.对于一个树，其深度为根节点加上左右节点为根节点的树的最大值；3.结束条件为：若根节点为空则树的深度为0。