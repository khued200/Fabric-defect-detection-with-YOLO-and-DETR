# Fabric-defect-detection-with-YOLO-and-DETR
## Fabric defect detection
Fabric defect detection is a part of fabric quality control in textile production. In textile companies, the detection of defects and unacceptable areas of fabrics at the quality control stage has great importance for apparel production, although it is also a post-manufacturing operation for weaving and knitting mills.

The fabric defects may cause a 45-65% incurred loss in sale prices. Besides, approximately 85% of the product rejects in the apparel industry are related to fabric defects.

## Dataset
Using [TILDA dataset for fabric defect detection in roboflow](https://universe.roboflow.com/irvin-andersen/tilda-fabric/dataset/2)

The dataset contains 896 total images (train: 776, valid: 80, test: 40)

There are 4 classes in the dataset: holes, oil spots, thread errors, objects

## Train model
Using 3 models: GELAN-C-DET (YOLOv9), YOLOv10-L, and DETR-R50
Train for 100 echos for each model, training time ~ 2h
YOLOv9:
| Model | Test Size | Param. | FLOPs | AP<sup>box</sup> |
| :-- | :-: | :-: | :-: | :-: |
| [**GELAN-C-DET**](https://github.com/WongKinYiu/yolov9/releases/download/v0.1/gelan-c-det.pt) | 640 | 25.3M | 102.1G |**52.3%** |

YOLOv10:
| Model | Test Size | Param. | FLOPs | AP<sup>box</sup> |
| :-- | :-: | :-: | :-: | :-: |
| [**YOLOv10-L**](https://github.com/WongKinYiu/yolov9/releases/download/v0.1/gelan-c-det.pt) | 640 | 24.4M | 120.3G |**53.2%** |

DETR:
| Model | Backbone | Schedule | Inf_time | AP<sup>box</sup> |
| :-- | :-: | :-: | :-: | :-: |
| [**DETR**](https://github.com/WongKinYiu/yolov9/releases/download/v0.1/gelan-c-det.pt) | R50 | 500 | 0.036 |**42.0%** |

Training model using Kaggle environment
Fine-tuning the model to get better results
## Result

<img src="https://github.com/user-attachments/assets/904a7deb-0839-4f41-b203-d8a2729ad289" height="500">
<br/>
<img src="https://github.com/user-attachments/assets/6147ee40-75d2-49bc-b931-17c4316c1aa4" height="250">

|Model|	GELAN-C|	YOLOv10-L|	DETR-R50|
| :-- | :-: | :-: | :-: |
|FPS	|16.64	|24.45	|9.35|

While YOLOv9-GELAN-C got the best accuracy, YOLOv10-L faster than ~50%

Some detect images:

|||
|:-------------------------:|:-------------------------:|
|![c1r1e1n10_jpg rf 302df4c62380ef189aeb08d7dbc54397](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/9a46c467-911c-4ba9-9b5d-fa2a72b50baf)|![c1r1e2n26_jpg rf 397a04a8f89051055723d42e8d428c3f](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/81c616c7-323b-4e3c-88bb-f12cb5e3a32a)|
|![c1r1e4n10_jpg rf c87f0bf21c6e9c849ae2b88c3be1a415](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/b19891ed-4b29-4e54-ac90-7b17deb5d0ad)|![c1r1e3n26_jpg rf c06496de2418cb3b7ea2198ec487daca](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/6b416655-ca6b-4870-8b7c-7027183045a4)|





