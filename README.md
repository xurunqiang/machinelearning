# machinelearning
重新学习深度学习各种算法<br>
1.1960年，感知机最早的一个神经网络模型，模型结构如下图所示<br>
![image](https://github.com/user-attachments/assets/aa143add-ef0a-42b9-addf-194717cf060d)<br>
伪代码<br>
![image](https://github.com/user-attachments/assets/b0c3625e-a904-4d0e-b3ba-99079a329234)<br>
收敛定理<br>
![image](https://github.com/user-attachments/assets/039cb0ad-81e7-47a0-b683-073d82d383a7)<br>
## 感知机收敛性分析

### 🔸 1. 数据在半径 r 内

所有输入特征向量 x 都满足：

||x|| ≤ r

也就是说，数据都被包含在以原点为中心、半径为 r 的球体中。

---

### 🔸 2. 余量 ρ 分类两类

假设数据线性可分，存在某个线性分类器 (w, b)，使得所有数据点满足：

y (xᵀw + b) ≥ ρ

其中：

- y ∈ {+1, -1} 是样本标签；
- ρ 是最小间隔（margin），表示样本到分类边界的最小距离。

---

### 🔸 3. 对于 ||w||² + b² ≤ 1

这是对分类器参数的归一化假设，用于简化理论分析。

---

### 🔸 4. 感知机最多在 (r² + 1) / ρ² 步后收敛

这是感知机收敛定理的结论：

- 如果所有样本满足：
  - ||x|| ≤ r
  - 存在分类器使得 y(xᵀw + b) ≥ ρ 且 ||w||² + b² ≤ 1

- 则感知机算法将在最多 (r² + 1) / ρ² 次更新后收敛。

