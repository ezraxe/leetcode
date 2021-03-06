## 题目

给定一个包含 m × n 个格子的面板，每一个格子都可以看成是一个细胞。每个细胞具有一个初始状态 live（1）即为活细胞， 或 dead（0）即为死细胞。每个细胞与其八个相邻位置（水平，垂直，对角线）的细胞都遵循以下四条生存定律：

1. 如果活细胞周围八个位置的活细胞数少于两个，则该位置活细胞死亡；
2. 如果活细胞周围八个位置有两个或三个活细胞，则该位置活细胞仍然存活；
3. 如果活细胞周围八个位置有超过三个活细胞，则该位置活细胞死亡；
4. 如果死细胞周围正好有三个活细胞，则该位置死细胞复活；

根据当前状态，写一个函数来计算面板上细胞的下一个（一次更新后的）状态

## 解答

如果直接在原矩阵上做0和1的变换，会影响后面的细胞的状态分析

### 方法一（需要一个额外的矩阵空间）

创建一个 m × n 的辅助空间，将下一个状态保存在辅助矩阵中，然后利用辅助矩阵更新原矩阵

### 方法二（原地修改）

如果要在原矩阵上修改，那么需要保留原来的状态，使得后面的分析不受影响，因此可以利用int右起第2位作为新的状态，当分析完所有细胞的新的状态后，再遍历一遍数组，每个元素右移一位得到新状态