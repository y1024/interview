## 二叉树

**二叉树**：二叉树是有限个结点的集合，这个集合或者是空集，或者是由一个根结点和两株互不相交的二叉树组成，其中一株叫根的做左子树，另一棵叫做根的右子树。

**二叉树的性质**：

* 性质1：在二叉树中第 i 层的结点数最多为2^(i-1)（i ≥ 1）
* 性质2：高度为k的二叉树其结点总数最多为2^k－1（ k ≥ 1）
* 性质3：对任意的非空二叉树 T ，如果叶结点的个数为 n0，而其度为 2 的结点数为 n2，则：`n0 = n2 + 1`

**满二叉树**：深度为k且有2^k －1个结点的二叉树称为满二叉树

**完全二叉树**：深度为 k 的，有n个结点的二叉树，当且仅当其每个结点都与深度为 k 的满二叉树中编号从 1 至 n 的结点一一对应，称之为完全二叉树。（除最后一层外，每一层上的节点数均达到最大值；在最后一层上只缺少右边的若干结点）

* 性质4：具有 n 个结点的完全二叉树的深度为 log2n + 1

**注意**：

* 仅有前序和后序遍历，不能确定一个二叉树，必须有中序遍历的结果

## 堆

如果一棵完全二叉树的任意一个非终端结点的元素都不小于其左儿子结点和右儿子结点（如果有的话）
的元素，则称此完全二叉树为最大堆。
        
同样，如果一棵完全二叉树的任意一个非终端结点的元素都不大于其左儿子结点和右儿子结点（如果
有的话）的元素，则称此完全二叉树为最小堆。

**最大堆的根结点中的元素在整个堆中是最大的；**

**最小堆的根结点中的元素在整个堆中是最小的。**

## 哈弗曼树

* 定义：给定n个权值作为n的叶子结点，构造一棵二叉树，若带权路径长度达到最小，称这样的二叉树为最优二叉树，也称为哈夫曼树(Huffman tree)。

* 构造：

    假设有n个权值，则构造出的哈夫曼树有n个叶子结点。 n个权值分别设为 w1、w2、…、wn，则哈夫曼树的构造规则为：
    
    1. 将w1、w2、…，wn看成是有 n 棵树的森林(每棵树仅有一个结点)；
    2. 在森林中选出两个根结点的权值最小的树合并，作为一棵新树的左、右子树，且新树的根结点权值为其左、右子树根结点权值之和；
    3. 从森林中删除选取的两棵树，并将新树加入森林；
    4. 重复(2)、(3)步，直到森林中只剩一棵树为止，该树即为所求得的哈夫曼树。

    
## 二叉排序树

二叉排序树（Binary Sort Tree）又称二叉查找树（Binary Search Tree），亦称二叉搜索树。

二叉排序树或者是一棵空树，或者是具有下列性质的二叉树：

1. 若左子树不空，则左子树上所有结点的值均小于它的根结点的值；
2. 若右子树不空，则右子树上所有结点的值均大于或等于它的根结点的值；
3. 左、右子树也分别为二叉排序树；
4. 没有键值相等的节点

二分查找的时间复杂度是O(log(n))，最坏情况下的时间复杂度是O(n)（相当于顺序查找）

## 平衡二叉树

平衡二叉树（balanced  binary  tree）,又称 AVL 树。它或者是一棵空树,或者是具有如下性质的二叉树：

1. 它的左子树和右子树都是平衡二叉树，
2. 左子树和右子树的深度之差的绝对值不超过1。

平衡二叉树是对二叉搜索树(又称为二叉排序树)的一种改进。二叉搜索树有一个缺点就是，树的结构是无法预料的，随意性很大，它只与节点的值和插入的顺序有关系，往往得到的是一个不平衡的二叉树。在最坏的情况下，可能得到的是一个单支二叉树，其高度和节点数相同，相当于一个单链表，对其正常的时间复杂度有O(log(n))变成了O(n)，从而丧失了二叉排序树的一些应该有的优点。


## B-树

**B-树**：B-树是一种非二叉的查找树， 除了要满足查找树的特性，还要满足以下结构特性：

一棵 m 阶的B-树：

1. 树的根或者是一片叶子(一个节点的树),或者其儿子数在 2 和 m 之间。
2. 除根外，所有的非叶子结点的孩子数在 m/2 和 m 之间。
3. 所有的叶子结点都在相同的深度。   

B-树的平均深度为logm/2(N)。执行查找的平均时间为O(logm)；

## Trie 树

Trie 树，又称前缀树，字典树， 是一种有序树，用于保存关联数组，其中的键通常是字符串。与二叉查找树不同，键不是直接保存在节点中，而是由节点在树中的位置决定。一个节点的所有子孙都有相同的前缀，也就是这个节点对应的字符串，而根节点对应空字符串。一般情况下，不是所有的节点都有对应的值，只有叶子节点和部分内部节点所对应的键才有相关的值。

Trie 树查询和插入时间复杂度都是 O(n)，是一种以空间换时间的方法。当节点树较多的时候，Trie 树占用的内存会很大。

Trie 树常用于搜索提示。如当输入一个网址，可以自动搜索出可能的选择。当没有完全匹配的搜索结果，可以返回前缀最相似的可能。
### 参考资料

* [百度百科：哈弗曼树](http://baike.baidu.com/view/127820.htm)
* [百度百科：二叉排序树](http://baike.baidu.com/view/647462.htm)
* [百度百科：平衡二叉树](http://baike.baidu.com/view/593144.htm)
* [平衡二叉树及其应用场景](http://blog.csdn.net/huiguixian/article/details/6360682)
* [百度百科：B-树](http://baike.baidu.com/view/2228473.htm)
* [前缀树](http://www.iteye.com/topic/1132573)
* [百度百科：前缀树](http://baike.baidu.com/view/9875057.htm)