# 2026_DeepLearning_HW1
Course Homework 1

# 深度学习 HW1：三层 MLP 图像分类

---

## 项目说明
基于 NumPy 手动实现**三层 MLP**，完成 EuroSAT 遥感图像 10 分类任务。

包含：数据加载、前向传播、反向传播、SGD 优化、L2 正则、超参数搜索、模型保存、测试评估与可视化。

数据集目录应当位于：
```
EuroSAT_RGB/
```

该目录已经按照类别分类子文件夹，可以直接读取用于训练

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
2. 打开 `code_for_hw1.ipynb`
3. 依次运行所有 cell，直到 **训练最终模型** 模块，final model的参数也已经手动设置好，无需导入，可直接运行
4. 训练完成自动保存：`final_best_model.pkl`

---

## 3. 超参数配置
#### （1）超参数搜索范围
| 超参数名称       | 搜索范围                  |
|------------------|---------------------------|
| 初始学习率       | [0.01, 0.005]      |
| 隐藏层 1 维度    | [256, 512]            |
| 隐藏层 2 维度    | [128, 256]            |
| L2 正则化强度    | [1e-3, 1e-4]        |

#### （2）最优超参数（最终采用）
| 超参数名称       | 采用值                  |
|------------------|---------------------------|
| 初始学习率       | 0.01                       |
| 隐藏层 1 维度    | 512                        |
| 隐藏层 2 维度    | 256                        |
| L2 正则化强度    | 0.001                      |
| 激活函数         | ReLu                       |
| 批次大小        | 64                          |
| 学习率衰减系数   | 0.95（固定）                |
| 学习率衰减步长   | 10 epoch（固定）            |
|训练总轮数        |  100                       |
---

## 4. 运行测试与评估
1. 确保 `final_best_model.pkl` 在当前目录
2. 运行 Notebook 中 **评估分析与可视化** 模块
3. 可得到：
   - 训练曲线和验证集上的accuracy曲线 `training_curves.png`
   - 测试集准确率
   - 混淆矩阵 `confusion_matrix.png`
   - 第一层权重可视化 `first_layer_weights.png`
   - 错例分析图 `error_analysis/error_examples[].png`

---

## 5. 模型权重下载
Google Drive 下载链接：
https://drive.google.com/drive/folders/1pMxUmYUyt4Xc6Bq2GP2cGc4Tvxc4QXr1?usp=drive_link

---

## 6. 模型说明
- 网络结构：输入层 → 隐藏层1(512) → 隐藏层2(256) → 输出层(10类)
- 激活函数：ReLU
- 优化器：SGD + 学习率阶梯衰减
- 正则：L2 正则
- 最优验证准确率：**0.6481**
- 测试集准确率：**0.6706**
