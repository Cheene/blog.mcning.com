# #1619 [二叉树的镜像](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)

## 题目

````
请完成一个函数，输入一个二叉树，该函数输出它的镜像。
````

## **示例**

````
例如输入：

     4
   /   \
  2     7
 / \   / \
1   3 6   9
镜像输出：

     4
   /   \
  7     2
 / \   / \
9   6 3   1

输入：root = [4,2,7,1,3,6,9]
输出：[4,7,2,9,6,3,1]
````

## **限制**

````
0 <= 节点个数 <= 1000
````

## 思路

````
需要交换左右子树的位置而不仅仅是元素
判断当前节点的子树行为
	如果只有左子树
		右子树设置为左子树，左子树为空
		递归修改右子树
	如果只有右子树
		左子树设置为右子树，右子树为空
		递归修改左子树
	否则
		左右子树调换
		左右子树递归
````

## 实现

````go
func mirrorTree(root *TreeNode) *TreeNode {
    if root == nil {
        return root
    }
    /**
    如果是空子树要注意
    */
    if root.Left == nil && root.Right == nil {
        return root
    } else if root.Left == nil {
        root.Left, root.Right = root.Right,nil
        mirrorTree(root.Left)
    } else if root.Right == nil {
        root.Left, root.Right = nil, root.Left
        mirrorTree(root.Right)
    } else {
        root.Left, root.Right = root.Right, root.Left
        mirrorTree(root.Left)
        mirrorTree(root.Right)
    }
    return root
}
````

