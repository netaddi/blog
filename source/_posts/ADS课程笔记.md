---
title: ADS课程笔记
date: 2017-02-28 10:18:57
tags:
---

## AVL Tree -- Adelson-Velski-Landis Tree

###height balanced tree T:

1. Tl and Tr are height balanced
2. | hL - hR | <= 1

### BF (balance factor):
BF = hL - hR

in AVL Tree, BF is -1, 0 or 1.

### rotation of AVL tree:
1. single rotation: LL RR
2. double rotation: LR RL

插入新节点时，如果需要旋转，则从root开始跟踪新插入的节点。前两个方向就决定了旋转类型。

### 删除节点
在工程中实际上并不删除节点，而只进行lazy delete。


##Splay Tree

目的：从空树开始的M次操作消耗时间不超过O(M log N) 
即摊还时间（amortized time）为log N

###基本思想
每当访问一个节点，通过zigzag和zigzig旋转将其变为根节点。

###删除节点
首先访问该节点，将其变为root，删除后剩下两棵子树。
从左子树寻找最大节点，将其旋转为root，然后将整个右子树接上。