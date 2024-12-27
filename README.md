[Deep learning-based smoker classification and detection: An overview and evaluation] (https://www.sciencedirect.com/science/article/abs/pii/S0957417424030756)


# Performance of Cigdet Dataset on YOLO variants

This repository has the details of our recent work on smoker classification and detection review.


## Performance
Benchmarking on [CigDet](https://data.mendeley.com/datasets/6hyrr8typ7/1) dataset

Results of top-4 performing YOLO variants.

| Model | Image Size | Params | mAP@50 | FLOPs | Inference time |
|:---------------|:----:|:---:|:--:|:--:|:--:|
| [YOLOv8](https://github.com/ultralytics/ultralytics) |   256  |     43.63M    |  80.30%  |     164.8G     |  11.6 ms  | 
| [YOLOv9](https://github.com/WongKinYiu/yolov9) |   256  |     50.95M    |   83.50%  |     238.9G     |  18.7 ms  |
| [YOLOv10](https://github.com/THU-MIG/yolov10) |   256  |     31.58M   |   78.90%  |     169.8G     |  10.0 ms  |
| [YOLO11](https://github.com/ultralytics/ultralytics) |   256  |     56.82M   |  81.50%  |    194.4G    |  12.1 ms  |


## Pretrained Models

Pretrained Models can be downloded from [here](https://drive.google.com/drive/folders/1J4_iQyvZc3FKM6bkIswALpLsWPEIAjR6?usp=drive_link)


## Validation
 
```
yolo val model=yolo{.../v5.pt/v8.pt/v9.pt/...} data=cigdet.yaml batch=32
```

Or
```python
from ultralytics import YOLO

model = YOLOv8.from_pretrained('yolov8')
# or

model = YOLOv8('yolov8.pt')

model.val(data='cigdet.yaml', batch=32)
```



## Prediction
For prediction on CigDet dataset, use the pretrained models and any test image from the dataset. 
```
yolo predict model=yolo{.../v5.pt/v8.pt/v9.pt/...} source=/path-to-dataset/images/image.jpg'
```



## Acknowledgement

Special Thanks to the YOLO research community for their contributions from [YOLOv1](https://github.com/pjreddie/darknet) to [YOLO11](https://github.com/ultralytics/ultralytics).





