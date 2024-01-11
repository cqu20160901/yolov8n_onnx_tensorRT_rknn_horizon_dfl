# yolov8n_onnx_tensorRT_rknn_horizon_dfl
yolov8n 目标检测部署版本，便于移植不同平台（onnx、tensorRT、rknn、Horizon），全网部署最简单、速度最快的部署方式，后处理为C++部署而写，python 测试后处理意义不大。

之前写过两次yolov8目标检测部署，后续继续思考，针对部署还有优化空间，本示例的部署方式优化了部署难度，加快了模型推理速度（略微增加了后处理的时耗）。

# 文件夹结构说明

yolov8n_onnx：onnx模型、测试图像、测试结果、测试demo脚本

yolov8n_TensorRT：TensorRT版本模型、测试图像、测试结果、测试demo脚本、onnx模型、onnx2tensorRT脚本(tensorRT-7.2.3.4)

yolov8n_rknn：rknn模型、测试（量化）图像、测试结果、onnx2rknn转换测试脚本

yolov8n_horizon：地平线模型、测试（量化）图像、测试结果、转换测试脚本、测试量化后onnx模型脚本

# 测试结果
![image](https://github.com/cqu20160901/yolov8n_onnx_tensorRT_rknn_horizon_dfl/blob/main/yolov8_onnx/test_onnx_result.jpg)

（注：图片来源coco128）

说明：推理测试预处理没有考虑等比率缩放，激活函数 SiLU 用 Relu 进行了替换。由于使用的是coco128数据进行训练的，且迭代的次数不多，效果并不是很好，仅供测试流程用。

导出onnx参考 [yolov8 瑞芯微RKNN和地平线Horizon芯片仿真测试部署-2023年11月15日版本](https://blog.csdn.net/zhangqian_1/article/details/134438275)
