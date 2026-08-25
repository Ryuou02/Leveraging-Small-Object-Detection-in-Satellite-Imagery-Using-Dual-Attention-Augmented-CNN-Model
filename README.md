# Modified YOLO 11s with GAM+ECA attention modules

## Problem statement
Object detection in satellite imagery based on the SkyFusion dataset which contains vehicles within satellite imagery

## Challenge
Vehicles come in all different sizes, considering the classes of vehicles majorly being categorized into ships, airplanes, and vehicles such as cars, trucks, and buses. This calls for an image detection model that is capable in not only detection of small objects, but also of larger objects. This can be observed in the following images - 
<img width="1041" height="1037" alt="image" src="https://github.com/user-attachments/assets/22d9dabc-21bc-456a-990e-144f44fcea5a" />
This image of an airport show of how large an airplane can be within a satellite image

<img width="1002" height="1006" alt="image" src="https://github.com/user-attachments/assets/44f3e9fe-5915-4087-9b37-6558b6b8addb" />
And here we see how insignificant the boats are, within the vast waterbody. In fact, there are 2 boats within this image, and the 2nd one is barely even visible to the human observer.



## Methodology
Various models were tested before reaching the current model, this is what our workflow looked like - 
<img width="2353" height="798" alt="image" src="https://github.com/user-attachments/assets/ec274b78-ee60-428e-aca2-bd5339f6f9c1" />


After testing with different configurations, this was the final configuration which we arrived at - 
<img width="842" height="841" alt="yolo11s_hybrid" src="https://github.com/user-attachments/assets/35b16193-a353-4593-9f67-4ae47a706790" />
This module is meant to leverage the speed of YOLO11s, along with the speed of ECA, and the accuracy given by GAM attention module.
