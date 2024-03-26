## Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection

_**HemaDetect offers a cutting-edge approach to blood cell analysis, leveraging the capabilities of Detectron2 alongside advanced computational techniques and state-of-the-art algorithms. The platform utilizes sophisticated segmentation and detection methodologies to achieve high accuracy in identifying and delineating red blood cells (RBCs), white blood cells (WBCs), and platelets within microscopic blood images.**_

The Dataset contains 339 images on "Microscopic Analysis of Blood Cells:

+ Erythrocytes
+ Leukocytes
  - Neutrophil
  - Basophil
  - Lymphocyte
+ Basophilic Stippling
+ Platelet

![BloodImage_00234_2](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/61bdae98-220e-45b2-87ea-af00ebb6fe9e)

14 images have been taken from the dataset for Training, and have been annotated manually by _MakeSense.ai_, and the annotated file exported as _COCO JSON Format for Object Detection_. 3 images kept for validation and remaining 322 images used for testing.

These 14 images and their combined single _.json annotation file_ used for training and 3 validation images their combined single _.json annotation file_ used for validation.

Detectron2 did **Object Detection**: Identifying and localizing objects with bounding boxes & **Semantic Segmentation**: Assigning each pixel in an image a class label on the test images.

![test_BloodImage_65_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/60b14b08-db23-4aab-bc67-cbf8d58639c5)

The Code also save the _Binary Predicted Mask_ for all 6 classes of each image in the test set.

_eg, all the Segmented Masks of a single random test image_
_
**Erythrocytes**_

![test_BloodImage_61_Red Blood Cells_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/86aeba5c-d758-4a52-980d-7ae5101ebf8f)

**_Neutrophil_**

![test_BloodImage_61_Neutrophil_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/3b4044a0-ffda-4d73-beab-769c42cac255)

_**Platelet**_

![test_BloodImage_61_Platelet_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/22a4cec6-74a6-4175-98a5-e003f17b966e)

**_Basophilic Stippling_**

![test_BloodImage_61_Basophilic Stippling_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/72ef0f16-f9ac-4dc4-85ac-d6a1775277e8)
