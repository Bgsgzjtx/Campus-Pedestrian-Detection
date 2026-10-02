# Campus Pedestrian Detection

A YOLO-based pedestrian detection project for campus scenes.

## 项目简介

本项目使用 YOLO 目标检测模型，对校园场景中的行人进行目标检测。

当前版本为项目的第一阶段版本，主要针对校园道路、校园公共区域等场景中的行人进行检测。

> 当前版本仅检测 `pedestrian`（行人）类别。

## 项目目标

本项目旨在实现一个能够识别校园场景中行人的目标检测模型，并通过训练集、验证集以及真实场景图片对模型进行测试。

## 数据集

当前数据集包含：

- 训练集：159 张图片
- 验证集：40 张图片
- 类别数量：1
- 检测类别：`pedestrian`

数据采用 YOLO 格式进行标注。

## 模型与训练

- Detection framework: Ultralytics YOLO
- Model: YOLO11n
- Training epochs: 50
- Image size: 640 × 640
- Device: NVIDIA GPU
- Dataset type: Custom campus pedestrian dataset

## 实验结果

模型在验证集上的主要结果：

| Metric | Result |
|---|---:|
| Precision | 92.2% |
| Recall | 77.9% |
| mAP50 | 88.6% |
| mAP50-95 | 52.9% |

实验结果表明，模型已经能够较好地完成校园场景中的行人检测任务。

## 模型文件

训练完成后的最佳模型为：

`best.pt`

该模型可以用于对新的校园场景图片进行行人检测。

## 测试

可以使用训练得到的 `best.pt` 对新的图片进行预测。

示例：

```bash
yolo predict model=best.pt source="test_image.jpg" conf=0.25