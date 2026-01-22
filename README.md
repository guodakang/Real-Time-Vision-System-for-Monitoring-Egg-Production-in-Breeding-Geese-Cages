## A Real-Time Visual Monitoring System for Egg Production of Breeding Geese in Small-Group Natural Mating Cages

## ✨ Overview
This study proposes an efficient method for real-time measurement of individual egg-laying performance in small groups of breeding geese housed in natural-mating cages. The SELR system uses night-vision cameras to capture images under both daytime and night-time conditions, which are transmitted to an on-farm server for storage. After annotation, the collected data are used to train and refine the object detection model, TAGM-YOLO. TAGM-YOLO simultaneously identifies individual geese and detects newly laid eggs, and a matching strategy is then applied to associate each egg with the corresponding female. The system has been deployed in a terminal application that supports egg-laying statistics, image traceability, and breeder-goose profile management.
<img width="1836" height="1890" alt="Figure 1" src="https://github.com/user-attachments/assets/6d1eeb56-8181-44e0-bdd2-92198580cab4" />


## 📂 Datasets

To access the **datasets and code** used in this study, please ensure that all files are downloaded from the following Baidu Netdisk link: 
https://pan.baidu.com/s/1F38LGUh4Ip3_Bi1uTmkqtQ 
Extraction code：please email at 1395401554@qq.com

Examples of the Daytime and Night-time datasets are shown below:

<img width="525" height="454" alt="image" src="https://github.com/user-attachments/assets/e0464c08-4943-4cf0-b5ab-222e00d1e9d4" />

A pseudocode overview of the proposed method is provided below:
<img width="600" height="750" alt="伪代码" src="https://github.com/user-attachments/assets/e4cd9b42-b798-4e1e-9f65-a5b1afc27062" />


## 🧩 Method — Egg–Goose Matching

Using TAGM-YOLO detections, eggs are assigned to the nearest female goose (by centre-to-centre distance) within the Egg-Laying Area (ELA), and both the individual and cage egg counts are updated. An Egg Exit Area (EEA) marks when an egg has rolled into the collection zone. To avoid double counting, a moving Match-Forbidden Area (MFA) (radius = 2× egg box width) is created after matching; eggs inside the MFA are ignored until the egg exits the ELA (touches the EEA) or disappears without overlapping any goose box.
<img width="2930" height="3024" alt="Figure 7" src="https://github.com/user-attachments/assets/2e959503-9f1c-421b-a232-0a4cfb80c2d7" />



## 🎥 结果

The demonstration videos can be found at the end of the paper: Supplementary Video 1.mp4 and Supplementary Video 2.mp4.

Supplementary Video 1.mp4 compares MFA radius = 2×egg_width with MFA radius = 1×egg_width.

![Supplementary Video 1](https://github.com/user-attachments/assets/d17ce2a7-99b6-4e39-ae82-85a5f9713dea)



Supplementary Video 2.mp4 compares MFA radius = 2×egg_width with no MFA.


![Supplementary Video 2](https://github.com/user-attachments/assets/e52be715-aab1-4576-b53d-1ef1341eab30)
