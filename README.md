# 基于深度学习的印刷电路板组件检测研究

> Research on Printed Circuit Board Component Detection Based on Deep Learning

**作者**:戴亨 | **导师**:张云港 副教授  
**学校**:云南师范大学 信息学院 | **学位**:硕士  
**专业**:计算机应用技术 | **答辩时间**:2025 年 5 月

---

## 📖 论文摘要

针对 PCB 组件检测中**目标尺寸小、类间相似度高、数据样本有限**等挑战,本文基于深度学习方法提出了两种针对性的检测算法,在自建的 SPCB-Datasets 数据集上取得了优于现有方法的检测效果,并在 PCB 缺陷检测任务上验证了模型的通用性。

## 🎯 主要贡献

1. **构建 SPCB-Datasets 数据集**:整合 FICS 与 pcb_wacv_2019 公共数据集,通过几何变换与色彩空间增强,构建了包含 **14,602 张图像、9 个组件类别**的专用数据集。

2. **提出 DFBA-YOLOv8 模型**:基于 YOLOv8n 改进的高速 PCB 组件检测算法
   - 引入 DCNv4 可变形卷积增强特征提取
   - 设计 RFAConv 关注感受野的卷积模块
   - 提出基于 BiFPN 改进的 BPFPN 多尺度特征融合结构
   - 设计基于注意力机制的 AMD_Detect Head 检测头
   - **检测精度 mAP@0.5 = 88.6%,推理速度 103 FPS**

3. **提出 EfficientPCB-DETR 模型**:基于 RT-DETR 改进的高精度 PCB 组件检测算法
   - 使用 EfficientFormerV2 替换原 ResNet-18 主干
   - 用 HiLo 注意力优化 AIFI 中的多头自注意力
   - 采用 DySample 轻量化上采样模块
   - **检测精度 mAP@0.5 = 92.5%,推理速度 64 FPS**

4. **跨任务通用性验证**:在公开 PCB 缺陷检测数据集上,DFBA-YOLOv8 取得 88.3% mAP@0.5,EfficientPCB-DETR 取得 85.6% mAP@0.5,均显著优于现有方法。

## 📊 性能对比

### PCB 组件检测任务(SPCB-Datasets)

| 模型 | 参数量 (M) | mAP@0.5 | mAP@0.5:0.95 | FPS |
|------|-----------|---------|--------------|-----|
| YOLOv8n (baseline) | 3.20 | 83.4% | 57.2% | 113 |
| RT-DETR (baseline) | 24.79 | 87.6% | 53.9% | 56 |
| **DFBA-YOLOv8 (Ours)** | 3.43 | **88.6%** | **61.6%** | **103** |
| **EfficientPCB-DETR (Ours)** | 17.88 | **92.5%** | **57.8%** | **64** |

## 📁 仓库内容

- 📄 [论文全文 PDF](Dai-Heng-Master-Thesis-PCB-Component-Detection-2025.pdf)
- 📊 [答辩 PPT](slides/defense.pdf)(可选)
- 💻 [代码实现](code/)(可选)

## 🔑 关键词

PCB 组件检测 · 深度学习 · 小目标检测 · YOLOv8 · RT-DETR · 注意力机制 · 工业视觉

## 📧 联系方式

- **邮箱**:你的邮箱@xxx.com
- **GitHub**:[@你的用户名](https://github.com/你的用户名)

## 📜 引用

如果本工作对你的研究有帮助,欢迎引用:

​```bibtex
@mastersthesis{dai2025pcb,
  title={基于深度学习的印刷电路板组件检测研究},
  author={戴亨},
  year={2025},
  school={云南师范大学},
  type={硕士学位论文}
}
​```
