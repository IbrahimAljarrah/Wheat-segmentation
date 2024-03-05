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

# Dataset Description
More details on the data acquisition and processes are available at https://arxiv.org/abs/2005.02162

# Pipeline Project
![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/ac614be8-cabc-453a-8596-f4807b9d3dab)

# Data Annotation
we have manually annotated around 400 images using cvat

# Using Roboflow Annotate
Annotate around 400 images manually using CVAT
    1- Upload the annotated images on robflow 
    2- Data Augmentation using robflow
    3- Train a yolo model on the annotated images using robflow.
    4- Connect the trained model to CVAT and use it to automate annotation for the rest of the images

![WhatsApp Image 2024-03-03 at 22 17 51_6ed1cc16](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/532fc5b7-c602-4cc6-bc54-62ef59fb8bea)


# Data Annotation using Model in CVAT.Ai
Video

# Export Data

      # json file
      
      ![WhatsApp Image 2024-03-04 at 15 02 54_2261f9f7](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/587129b2-0f82-426c-aa6f-d289240d1f87)
    
      # Segmentation Mask
      ![WhatsApp Image 2024-03-03 at 15 46 39_aefb25d4](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/8c6882dc-3982-475d-912c-0959a489fc03)


# Split data training and Validation

![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/7c3216e6-e536-4447-95e2-a28dcb6124b0)

# Models 

  # 1- Yolo8-seg
  1- The images and JSON file were uploaded to Roboflow and the annotation process was completed automatically
  2- Data Augmentation was used through Roboflow
  3- Connect roboflow with yolo8-seg through API-key and train the model, for 20 epoch
  ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/c4d96107-52fe-4f23-8752-cd84688a795a)

  ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/53c5290a-276b-47df-9903-90ab4019667d)
  
  # convertr model from .pt to onnx
  The Open Neural Network Exchange is an open-source artificial intelligence ecosystem of technology companies and research organizations that establish open        standards for representing machine learning algorithms and software tools to promote innovation and collaboration in the AI sector. ONNX is available on GitHub
  
  ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/1ea836bd-e4fa-4b28-99d0-e13fb6320e5d)

  ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/e8e3ed8b-0ead-468c-839f-25ce0b2cc000)

  # 2- U-Net
  Trained U-net model on the first batch of 800 images
  # Data Loading:
      Uses the glob library to get file paths for images and masks.
  # Image and Mask Preprocessing:
      Images and masks are read with OpenCV and stored in lists.
      Converted to NumPy arrays and expanded to 4D.
      Resized to 256x256 using OpenCV.
  # Normalization:
      Images normalized to [0, 1].
      Masks rescaled to [0, 1].
  # Building U-Net Model:
      U-Net architecture with encoder and decoder.
      Encoder: Convolutional layers, batch normalization, ReLU activation.
      Decoder: Transpose convolution for upsampling, concatenation with corresponding encoder block.
  # Model Compilation:
      Adam optimizer used.
      Binary_crossentropy loss for binary classification.
  # Model Training:
    Trained for 25 epochs with a batch size of 4.
    
      ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/cefb87db-a125-47ee-966a-c6cb2d04b9f4)

      ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/32d31577-26eb-4169-a487-88a868909551)
    
  # using all datasets 2609
  
  ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/c3b37259-2ea0-438d-bd48-5c3a3c509f58)

  # 3- SAM
  # Data Loading:
    Exported masks as segmentation masks using CVAT.
    Load images and masks 
  # Image and Mask Preprocessing:
    Images and masks are read using pillow and stored in lists.
    Converted to NumPy .
    Resized to 256x256.
  # Create a custom dataset
    Convert the NumPy arrays to Pillow images and store them in a dictionary
    Create an instance of Samdataset:
    processor :(facebook/sam-vit-large")
  # Load pre-trained model 
    ViT-L SAM model.
  # Train model with train_dataloader 
    optimizer: Adam
    Loss: DiceFocalLoss
    epochs 10
    ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/0eea00b4-1068-4caa-80d5-3068c2015633)
    ![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/82398add-d3cb-40b7-8eb7-650a27ed2e9e)
# Summery

![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/a4798cca-20ea-4f22-b628-4c0ce935e4a8)

# Prediction Test

![image](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/6a3f26a6-60ee-469f-9872-74e9a2296e4f)

# Conclusion
1- YOLOv8-seg stands out as the most effective model among its counterparts.
2- Establishing a seamless integration between Roboflow and CVAT can significantly enhance the annotation process, making it both more efficient and expedited.
3- Empirical evidence supports the notion that converting models to ONNX format can notably accelerate the prediction phase.

# Future Work
1. Expanding the dataset size is imperative for future endeavours.
2. Enriching the dataset with additional images, particularly those featuring multiple plants, can enhance object diversity and model robustness.

                   ![WhatsApp Image 2024-03-04 at 00 20 05_4276f4cd](https://github.com/IbrahimAljarrah/Wheat-segmentation/assets/49195935/6c93cef4-f7cf-4452-a0da-9a84e3eb2a8e)






















  






















