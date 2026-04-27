# 2026_DeepLearning_HW1
Course Homework 1

# 深度学习 HW1：三层 MLP 图像分类

---

## 项目说明
基于 NumPy 手动实现**三层 MLP**，完成 EuroSAT 遥感图像 10 分类任务。
包含：数据加载、前向传播、反向传播、SGD 优化、L2 正则、超参数搜索、模型保存、测试评估与可视化。

---

## 1. 环境依赖
```
Python 3.8+
```

安装命令：
```bash
pip install numpy matplotlib pillow scikit-learn tqdm jupyter
```

---

## 2. 运行训练
1. 启动 Jupyter Notebook
```bash
jupyter notebook
```
2. 打开 `Code for HW1.ipynb`
3. 依次运行所有 cell，直到 **训练最终模型** 模块，final model的参数也已经手动设置好，无需导入，可直接运行
4. 训练完成自动保存：`final_best_model.pkl`

---

## 3. 运行测试与评估
1. 确保 `final_best_model.pkl` 在当前目录
2. 运行 Notebook 中 **评估分析与可视化** 模块
3. 可得到：
   - 训练曲线 `training_curves.png`
   - 测试集准确率
   - 混淆矩阵 `confusion_matrix.png`
   - 第一层权重可视化 `first_layer_weights.png`
   - 错例分析图 `error_analysis/error_examples.png`

---

## 4. 模型权重下载
Google Drive 下载链接：
https://drive.google.com/drive/folders/1pMxUmYUyt4Xc6Bq2GP2cGc4Tvxc4QXr1?usp=drive_link

---

## 5. 模型说明
- 网络结构：输入层 → 隐藏层1(512) → 隐藏层2(256) → 输出层(10类)
- 激活函数：ReLU
- 优化器：SGD + 学习率阶梯衰减
- 正则：L2 正则
- 最优验证准确率：**0.6481**
- 测试集准确率：**0.6706**
