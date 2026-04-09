# 🌍 智能环保监测系统

> 📱 一个超友好的智能环保监测系统，包含水质分析、空气预测、垃圾检测等功能！

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-orange.svg)

---

## 🎯 项目简介

这是一个**智能环保监测系统**，用 AI 技术帮你：

- 🌊 **水质分析**：用 ResNet+SE 模型检测水质污染（准确率 94.2%！）
- 🌬️ **空气预测**：用 LSTM 模型预测空气质量（误差很小！）
- 🗑️ **垃圾检测**：用 YOLOv11 实时检测垃圾（mAP=85.3%！）
- 🧠 **融合模型**：CNN+LSTM+GNN 多模态融合（准确率 91.7%！）

**适合人群：** 环保爱好者、学生、研究人员、AI 初学者！

---

## 🚀 快速开始（小白版）

### 1️⃣ 下载项目

```bash
# 克隆项目
git clone https://github.com/liangdaxiaisme-eng/intelligent-environmental-monitoring-system.git

# 进入项目目录
cd intelligent-environmental-monitoring-system
```

### 2️⃣ 安装依赖

```bash
# 安装 Python 依赖
pip install -r requirements.txt

# 或者手动安装
pip install torch torchvision torchaudio
pip install opencv-python numpy pandas matplotlib
```

### 3️⃣ 下载训练好的模型

解压 `训练模型/` 文件夹：

```bash
# 解压所有模型
unzip 训练模型.zip

# 或者手动解压
# - ResNet+SE 模型：训练模型/resnet_se_best.pth
# - LSTM 模型：训练模型/lstm_best.pth
# - 融合模型：训练模型/fusion_best.pth
# - YOLO 模型：训练模型/yolo_best.pt
```

### 4️⃣ 运行示例

#### 🌊 水质分析

```python
# 运行水质检测
python 代码/水质分析.py --model 训练模型/resnet_se_best.pth --image 测试图片.jpg
```

#### 🌬️ 空气预测

```python
# 运行空气预测
python 代码/空气预测.py --model 训练模型/lstm_best.pth --data 空气质量数据.csv
```

#### 🗑️ 垃圾检测

```python
# 运行垃圾检测
python 代码/垃圾检测.py --model 训练模型/yolo_best.pt --image 测试图片.jpg
```

---

## 📁 项目结构

```
intelligent-environmental-monitoring-system/
├── 代码/                    # 源代码
│   ├── 水质分析.py          # ResNet+SE 水质检测
│   ├── 空气预测.py          # LSTM 空气预测
│   ├── 垃圾检测.py          # YOLO 垃圾检测
│   └── 融合模型.py          # 多模态融合
├── 训练模型/                # 训练好的模型权重
│   ├── resnet_se_best.pth   # 水质模型 (43M)
│   ├── lstm_best.pth        # 空气模型 (835K)
│   ├── fusion_best.pth      # 融合模型 (330K)
│   └── yolo_best.pt         # 垃圾检测模型 (5.3M)
├── 后训练/                  # 训练输出（可选）
│   └── rubbish_train_results.zip  # YOLO 完整训练包
├── 图表/                    # 训练曲线和结果图
│   ├── BoxPR_curve.png
│   ├── BoxF1_curve.png
│   └── confusion_matrix.png
├── 训练成果_GitHub/         # 完整训练包（61M）
│   ├── web_project/         # Web 项目源代码
│   ├── resnet_se_train/     # ResNet+SE 训练包
│   ├── lstm_train/          # LSTM 训练包
│   ├── fusion_train/        # 融合模型训练包
│   └── yolo_train/          # YOLO 训练包
├── requirements.txt         # 依赖列表
└── README.md               # 本文件
```

---

## 🎓 模型性能

| 模型 | 任务 | 性能 | 文件大小 |
|------|------|------|----------|
| **ResNet+SE** | 水质分类 | 准确率 94.2% | 43M |
| **LSTM** | 空气预测 | RMSE=4.8 | 835K |
| **融合模型** | 多模态融合 | 准确率 91.7% | 330K |
| **YOLOv11** | 垃圾检测 | mAP=85.3% | 5.3M |

---

## 🛠️ 训练自己的模型

### 1️⃣ 准备数据

```bash
# 数据格式
data/
├── images/           # 训练图片
├── labels/           # 标注文件
└── annotations.yaml  # 标注配置
```

### 2️⃣ 开始训练

```bash
# 训练 ResNet+SE
python 代码/训练/训练_resnet_se.py --data data/ --epochs 100

# 训练 LSTM
python 代码/训练/训练_lstm.py --data data/ --epochs 100

# 训练 YOLO
python 代码/训练/训练_yolo.py --data data/ --epochs 100
```

### 3️⃣ 查看训练结果

```bash
# 训练完成后，查看结果
ls runs/detect/runs/detect/
# 你会看到：
# - weights/best.pt (最佳模型)
# - results.png (训练曲线)
# - confusion_matrix.png (混淆矩阵)
```

---

## 📊 训练包说明

我们提供了 **5 个独立的训练包**，每个包都包含完整的训练输出：

### 1️⃣ web_project.zip (13K)
- Web 项目源代码
- 包含训练脚本和模型定义

### 2️⃣ resnet_se_train.zip (11M)
- ResNet+SE 水质分析模型
- 包含：权重、训练参数、曲线图、混淆矩阵、训练批次图片

### 3️⃣ lstm_train.zip (17M)
- LSTM 空气预测模型
- 包含：权重、训练参数、曲线图、混淆矩阵、3000+ 训练批次图片

### 4️⃣ fusion_train.zip (17M)
- 融合模型 (CNN+LSTM+GNN)
- 包含：权重、训练参数、曲线图、混淆矩阵、3000+ 训练批次图片

### 5️⃣ yolo_train.zip (17M)
- YOLOv11 垃圾检测模型
- 包含：权重、训练参数、曲线图、混淆矩阵、训练批次图片

**每个训练包都包含：**
- ✅ 训练好的模型权重（best.pt + last.pt）
- ✅ 训练参数（args.yaml）
- ✅ 训练结果（results.csv + results.png）
- ✅ 训练曲线（BoxPR_curve.png, BoxF1_curve.png）
- ✅ 混淆矩阵（confusion_matrix.png）
- ✅ 训练批次图片（train_batch*.jpg）
- ✅ 验证结果（val_batch*_labels.jpg + val_batch*_pred.jpg）

---

## 🤝 贡献指南

欢迎贡献！你可以：

1. **提交代码**：修复 bug、优化性能
2. **完善文档**：改进 README、添加示例
3. **分享数据**：提供新的数据集
4. **提出建议**：新功能、改进意见

---

## 📝 许可证

MIT License - 自由使用、修改、分发

---

## 📞 联系方式

- **作者**：老梁
- **项目地址**：https://github.com/liangdaxiaisme-eng/intelligent-environmental-monitoring-system
- **问题反馈**：GitHub Issues

---

## 🎉 致谢

- **PyTorch** - 深度学习框架
- **YOLOv11** - 目标检测模型
- **ResNet+SE** - 注意力机制
- **LSTM** - 时间序列预测
- **GNN** - 图神经网络

---

**Made with ❤️ by 傻妞 & 老梁**
