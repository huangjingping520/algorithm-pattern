# 二叉树

## 二叉树遍历

**前序遍历：** 先访问根节点，再前序遍历左子树，再前序遍历右子树

**中序遍历：** 先中序遍历左子树，再访问根节点，再中序遍历右子树

**后序遍历：** 先后序遍历左子树，再后序遍历右子树，再访问根节点

**注：**

- 以根的访问确定顺序
- 左子树总是优先右子树

## 树结构

```js
function TreeNode(val) {
  this.val = val
  this.left = null
  this.right = null
}
```

## 根据数组构建二叉树

```js
const buildTreeByArray = function (array, index) {
  let tn = null;
  if (index < array.length) {
      const value = array[index];
      if (value !== null) {
          tn = new TreeNode(value);
          tn.left = buildTreeByArray(array, 2 * index + 1);
          tn.right = buildTreeByArray(array, 2 * index + 2);
      }
      return tn;
  }
  return tn;
}

const binaryTree = function (array) {
  return buildTreeByArray(array, 0);
}

const arr = [1,2,3,null,4,5,null,null,null,6,7];
let root = binaryTree(arr);
```
