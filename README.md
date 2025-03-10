# Terrain Segmentation for Off-Road Navigation  

## Overview  
This project focuses on terrain segmentation to enable off-road navigation. We utilize deep learning models to classify and segment different types of terrain, improving the navigation capabilities of autonomous systems.  

## Dataset  
We use the **RUGD (Robo-Urban Grassland Dataset)**, which consists of real-world off-road environments, providing diverse and challenging segmentation scenarios.  
![image](https://github.com/user-attachments/assets/ea836be3-adbf-4f80-84c2-32444eb72a18)


## Model  
We implement **U-Net** with the following backbone architectures:  
- [**EfficientNet-B3**](https://www.tensorflow.org/api_docs/python/tf/keras/applications/EfficientNetB2)
- [**MobileNetV2**](https://www.tensorflow.org/api_docs/python/tf/keras/applications/MobileNetV2)  

## Fine-tuning Strategy  
We fine-tune the **decoder and final layers** to optimize segmentation performance. Additionally, for some experiments, we fine-tune the last 12 layers of EfficientNet-B3.  

![image](https://github.com/user-attachments/assets/8879e267-8527-40ee-bddd-172ffef99df9)



## Training Results  

| Model           | Fine-tuned Layers  | Image Size | Validation Accuracy | Validation Mean IoU |
|---------------|------------------|------------|----------------------|----------------------|
| EfficientNet-B3 | Last 12 Layers    | 288x224    | 70.91%               | 29.35%               |
| EfficientNet-B3 | Decoder + Final  | 288x224    | 91.32%               | 64.66%               |
| EfficientNet-B3 | Decoder + Final  | 384x320    | 92.33%               | 68.17%               |
| MobileNetV2    | Decoder + Final  | 224x224    | 91.05%               | 65.51%               |

## Evaluation of Best Model on Test Set  

- **Test Accuracy:** **92.80%**  
- **Test Mean IoU:** **68.17%**

![image](https://github.com/user-attachments/assets/aceb2719-c051-4047-9d2c-6260a432fa01)




## Future Work  
- Experiment with different backbone architectures for improved segmentation.  
- Explore real-time inference optimization for deployment in off-road robotic systems.  
- Investigate self-supervised or semi-supervised learning approaches for better generalization.

<hr/>
References

http://rugd.vision/
