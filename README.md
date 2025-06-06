# machinelearning
重新学习深度学习各种算法<br>
1.1960年，感知机最早的一个神经网络模型，模型结构如下图所示<br>
![image](https://github.com/user-attachments/assets/aa143add-ef0a-42b9-addf-194717cf060d)<br>
伪代码<br>
![image](https://github.com/user-attachments/assets/b0c3625e-a904-4d0e-b3ba-99079a329234)<br>
收敛定理<br>
![image](https://github.com/user-attachments/assets/039cb0ad-81e7-47a0-b683-073d82d383a7)<br>
## 感知机收敛性分析

### 🔸 1. 数据在半径 \( r \) 内

这意味着所有输入特征向量 \( \mathbf{x} \) 都被约束在一个以原点为中心、半径为 \( r \) 的球体内：

\[
\|\mathbf{x}\| \leq r
\]

这是对输入数据大小的一个约束，有助于分析算法的收敛性。

---

### 🔸 2. 余量 \( \rho \) 分类两类

假设数据是线性可分的，并且存在一个线性分类器 \( \mathbf{w}, b \)，使得所有数据点满足：

\[
y(\mathbf{x}^\top \mathbf{w} + b) \geq \rho
\]

其中：

- \( y \in \{+1, -1\} \) 是样本标签；
- \( \rho \) 是**几何间隔（margin）**或称“分类余量”，表示数据点距离决策边界的最小间隔；

这个条件说明所有样本不仅被正确分类，而且分类间隔不小于 \( \rho \)。

---

### 🔸 3. 对于 \( \|\mathbf{w}\|^2 + b^2 \leq 1 \)

这是对分类器参数的归一化假设——为分析方便，通常假设权重向量 \( \mathbf{w} \) 和偏置 \( b \) 满足一定的范数约束，这样余量 \( \rho \) 可以看作是**规范化后的几何间隔**。

---

### 🔸 4. 感知机保证在 \( \frac{r^2 + 1}{\rho^2} \) 步后收敛

这是一条经典的**感知机收敛定理**：

> 如果数据线性可分，且满足：
> - 所有输入数据 \( \|\mathbf{x}\| \leq r \)
> - 存在一个分类器使得 \( y(\mathbf{x}^\top \mathbf{w} + b) \geq \rho \)，同时 \( \|\mathbf{w}\|^2 + b^2 \leq 1 \)
>
> 那么感知机算法最多在：
> \[
> \frac{r^2 + 1}{\rho^2}
> \]
> 步之后收敛。

