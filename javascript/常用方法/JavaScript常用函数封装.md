# js 常用方法封装

## 数组 <=> 树形 互转

```javascript {.line-numbers}
//数组转树形
export const treeToArray = (tree) => {
  const arr = [];
  const getChildren = (tree) => {
    tree.forEach((item) => {
      let p = {
        fatherId: item.fatherId,
        id: item.id,
        name: item.name,
      };
      if (item.children && item.children > 0) {
        getChildren(item.children);
      }
      arr.push(p);
    });
  };
  getChildren(tree);
  return arr;
};
//树形转数组
export const arrayToTree = (arr, rootId) => {
  let arr2 = arr.filter((item) => item.fatherId === rootId);
  let tree = arr2.map((e) => ({
    ...e,
    children: arrayToTree(arr, e.id),
  }));
  return tree;
};
```
