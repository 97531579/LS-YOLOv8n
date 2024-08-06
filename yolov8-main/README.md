Notes:
The first point is the version issue
    torch: 1.13.1
    torchvision: 0.14.1

The second point is the dependency packages that need to be installed
Most of the packages that need to be installed are in requirements.txt
    Some additional package installation commands:
    pip install timm thop efficientnet_pytorch einops -i https://pypi.tuna.tsinghua.edu.cn/simple
    pip install -U openmim
    mim install mmengine
    mim install "mmcv>=2.0.0"


The third point is model improvement

Fasterblock model under ultralytics/nn/extra_modules/block.py calss Faster_Block
Replace Bottleneck in C2f with FasterBlock in FasterNet
Example: ultralytics/models/v8/yolov8-C2f-Faster.yaml
Replace C2f with C2f-Faster.

EfficientHead in ultralytics/nn/extra_modules/head.py for Detect_Efficient class
ultralytics/models/v8/yolov8-EfficientHead.yaml
Redesign of the detection header using the idea of feature root sharing.
Example: ultralytics/models/v8/yolov8-EfficientHead.yaml
Using EfficientHead instead of Detect

Improvements to the WIOU loss function are in class BboxLoss(nn.Module) under ultralytics/yolo/utils/loss.py.
Hyperparameter settings under ultralytics/yolo/utils/metrics.py class WIoU_Scale



