# Leveraging-Small-Object-Detection-in-Satellite-Imagery-Using-Dual-Attention-Augmented-CNN-Model

## Problem statement
Object detection in satellite imagery based on the SkyFusion dataset which contains vehicles within satellite imagery

## Challenge
Vehicles come in all different sizes, considering the classes of vehicles majorly being categorized into ships, airplanes, and vehicles such as cars, trucks, and buses. This calls for an image detection model that is capable in not only detection of small objects, but also of larger objects. This can be observed in the following images - 
<img width="1041" height="1037" alt="image" src="https://github.com/user-attachments/assets/22d9dabc-21bc-456a-990e-144f44fcea5a" />
This image of an airport show of how large an airplane can be within a satellite image

<img width="1002" height="1006" alt="image" src="https://github.com/user-attachments/assets/44f3e9fe-5915-4087-9b37-6558b6b8addb" />
And here we see how insignificant the boats are, within the vast waterbody. In fact, there are 2 boats within this image, and the 2nd one is barely even visible to the human observer.

# Running the project - 
We used Google Colab to run the Python notebook `(modify_yolo_11s.ipynb)`. Copy the file `modify_yolo.zip` into the same directory. 
### Getting the dataset - 
Go to the dataset at [Roboflow.com](https://app.roboflow.com/skyfusion-92vfy/prj2-bbnxz/7/export). Download the dataset meant for training YOLOv11, and get on with running the whole notebook.


## Methodology
Various models were tested before reaching the current model, this is what our workflow looked like - 
<img width="2353" height="798" alt="image" src="https://github.com/user-attachments/assets/ec274b78-ee60-428e-aca2-bd5339f6f9c1" />


After testing with different configurations, this was the final configuration which we arrived at - 
<img width="842" height="841" alt="yolo11s_hybrid" src="https://github.com/user-attachments/assets/35b16193-a353-4593-9f67-4ae47a706790" />

This module is meant to leverage the speed of YOLO11s, along with the speed of ECA, and the accuracy given by GAM attention module.

## Results 
The models tested are the standard YOLO variants (YOLOv8s to YOLOv12s) and attention-augmented YOLOv11s versions with the use of GAM, ECA, and hybrid. The models were trained on augmented data and assessed based on metrics such as Precision, Recall, F1-Score, mAP@50, and mAP@50–95.

Of the baseline YOLO models, YOLOv11s provided the highest overall performance with the highest Precision (0.79616), F1-score (0.7494), and mAP@50 (0.74523). This establishes YOLOv11s as a highly effective and reliable baseline for aerial tiny object detection. YOLOv9s also performed well, with well-balanced Precision (0.7774), Recall (0.6883), and F1-score of 0.7302, making it a viable alternative. YOLOv12s attained the best Recall (0.7518) of the regular variants, which reflects greater sensitivity in object detection, but at a rather lower precision.YOLOv10s and YOLOv8s showed relatively lower performance on F1-score and mAP measures, reflecting that these lighter or earlier models could be less appropriate for the demanding small object detection problem in aerial images. For the attention-augmented YOLOv11s models, inclusion of GAM, ECA, and the hybrid attention modules enhanced the detection performance over the base YOLOv11s based on mAP@50 and mAP@50–95: The Hybrid model (GAM + ECA) achieved the highest F1-score of 0.7230, with mAP@50 = 0.71072, revealing that attention mechanisms do enhance feature learning for small and complex objects. Individual attention modules (GAM and ECA) also improved performance over baseline YOLOv11s but failed to beat the hybrid combination. Even with the improvement of attention models in some aspects, the base YOLOv11s still holds the highest precision and F1-score overall, indicating that for this dataset and training setup, the less complex model provides a better trade-off between false positives and false negatives.
<img width="2400" height="1200" alt="image" src="https://github.com/user-attachments/assets/42f855d3-9ba8-49d7-bf9d-e47127747232" />

# Publication
Obtain the research paper here - [https://link.springer.com/chapter/10.1007/978-3-032-15621-1_27]

### Cite this paper
Yammanuru, L., Jose, N.T., Singh, R.P. (2026). Leveraging Small-Object Detection in Satellite Imagery Using Dual Attention-Augmented Single-Stage CNN Model. In: Zaroliagis, C., Bhandari, D., Gupta, P., Das, S. (eds) Applied Algorithms. ICAA 2026. Lecture Notes in Computer Science, vol 16423. Springer, Cham. https://doi.org/10.1007/978-3-032-15621-1_27
