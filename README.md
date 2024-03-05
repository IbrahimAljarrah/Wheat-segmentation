# Wheat-segmentation
# INTRODUCTION

Image segmentation is a pivotal task in computer vision, particularly in the agricultural domain where precise analysis of crop health and yield estimation is paramount. In recent years, advancements in deep learning techniques have revolutionized the field of image segmentation, enabling researchers to achieve unprecedented levels of accuracy and efficiency.

This study focuses on the application of state-of-the-art (SOTA) models for wheat segmentation, employing cutting-edge methodologies such as Yolov8-seg, the SAM model, and U-Net. Wheat segmentation plays a crucial role in monitoring crop growth, disease detection, and yield prediction, aiding farmers and agronomists in making informed decisions for better crop management practices.

# Challenge
While image segmentation holds promise for revolutionizing wheat agriculture, several challenges must be addressed to realize its full potential.

    1. Variability in Image Quality and Conditions
    
    2. Complexity of Wheat Plant Structures
    
    3. Computational Complexity and Resource Constraints
    
    4. Integration with Decision Support Systems

Addressing these challenges requires interdisciplinary collaboration among researchers, agronomists, data scientists, and industry stakeholders. 

# Pipeline Project
![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/ac614be8-cabc-453a-8596-f4807b9d3dab)

# Data Annotation
we have manually annotated around 400 images using cvat

# Using Roboflow Annotate
Annotate around 400 images manually using CVAT
    1- Upload the annotated images on robflow 
    2- Data Augmentation using robflow
    3- Train a yolo model on the annotated images using robflow.
    4- Connect the trained model to CVAT and use it to automate annotation for the rest of images

![WhatsApp Image 2024-03-03 at 22 17 51_6ed1cc16](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/532fc5b7-c602-4cc6-bc54-62ef59fb8bea)


# Data Annotation using Model in CVAT.Ai
Vedio

# Export Data

  # json file
  
  ![WhatsApp Image 2024-03-04 at 15 02 54_2261f9f7](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/587129b2-0f82-426c-aa6f-d289240d1f87)

  # Segmentation Mask
  ![WhatsApp Image 2024-03-03 at 15 46 39_aefb25d4](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/8c6882dc-3982-475d-912c-0959a489fc03)


# Split data Traning and Validation

![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/7c3216e6-e536-4447-95e2-a28dcb6124b0)

# Models 

  # 1- Yolo8-seg
  1- The images and JSON file were uploaded to Roboflow and the annotation process was completed automatically
  2- Data Augmentation was used through Roboflow
  3- Connect roboflow with yolo8-seg through API-key and train the model, for 20 epoch
  ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/c4d96107-52fe-4f23-8752-cd84688a795a)

  ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/53c5290a-276b-47df-9903-90ab4019667d)

















  






















