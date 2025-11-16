# 实验三：逻辑回归模型

## 实验目的：
- 理解逻辑回归的基本原理
- 学习MindSpore的使用
- 掌握模型训练、预测和评估流程


## 实验环境：
- MindSpore 2.2
- 华为云ModelArts
- 主要库：
  - MindSpore
  - numpy
  - matplotlib 

## 实验内容：
使用MindSpore在2分类数据集上进行逻辑回归实验，分析自变量和因变量（概率）之间的关系，即求得一个概率函数。
### 1. 数据准备
- Iris数据集是模式识别最著名的数据集之一。数据集包含3类，每类50个实例，其中每个类都涉及一种鸢尾植物。 第一类与后两类可线性分离，后两类之间不能线性分离，所以本实验取前两类数据，做一个2分类数据集。
  下载链接：https://ascend-professional-construction-dataset.obs.cn-north-4.myhuaweicloud.com/MachineLearning/iris.data
  
### 2. 数据读取与处理
- 导入MindSpore中nn, Tensor, ops, ms_function, dataset, train 等模块
- 读取Iris数据集，并查看部分数据（取40-60部分数据）
- 取前两类样本（共100条），将数据集的4个属性作为自变量X。将数据集的2个类别映射为{0, 1}，作为因变量Y。
- 取样本的前两个属性进行2维可视化并输出
- 分割数据集，将数据集按8:2划分为训练集和验证集，划分的随机种子为 11。
- 使用MindSpore的GeneratorDataset接口将numpy.ndarray类型的数据转换为Dataset

### 3. 模型建立与训练
- 使用MindSpore提供的nn.Dense算子作为线性部分。
- 自定义loss,使用SigmoidCrossEntropyWithLogits算子作为非线性部分。
- 使用2分类的Iris数据集对模型进行几代（Epoch）训练(epoch=10)

### 4. 模型评估
- 计算模型在测试集上精度
- 可视化决策边界，展示分类结果。
- 绘制PR曲线、ROC曲线并计算$F_1$值


## 要求：
- **实验报告**：完成实验后，撰写实验报告，实验报告中应包含实验主要步骤的Python代码，可注释说明。
- **结果可视化**：使用matplotlib对模型的预测结果进行可视化处理，展示结果和决策边界并绘制对应图表。


## 需提交：
- **实验报告**：详细描述实验过程、结果和分析的文档。
