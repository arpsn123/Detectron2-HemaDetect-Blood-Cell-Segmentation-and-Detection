# Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Detectron2](https://img.shields.io/badge/Detectron2-v0.6.1-blue)](https://github.com/facebookresearch/detectron2)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.5.3-orange)](https://opencv.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.19.5-red)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.2.3-orange)](https://pandas.pydata.org/)

_**HemaDetect offers a cutting-edge approach to blood cell analysis, leveraging the capabilities of Detectron2 alongside advanced computational techniques and state-of-the-art algorithms. This platform is designed to achieve high accuracy in identifying and delineating red blood cells (RBCs), white blood cells (WBCs), and platelets within microscopic blood images, which are crucial for diagnosing various hematological conditions.**_

## Dataset Overview

The dataset comprises **339 images** that focus on the **Microscopic Analysis of Blood Cells**, featuring a diverse range of cell types, including:

- **Erythrocytes** (Red Blood Cells): Essential for oxygen transport in the body, their morphology can indicate various health conditions.
- **Leukocytes** (White Blood Cells): Crucial for immune responses, the dataset includes:
  - **Neutrophils**: A key component of the innate immune system, involved in combating infections.
  - **Basophils**: Important in allergic responses and inflammation.
  - **Lymphocytes**: Integral to the adaptive immune system, with subtypes including T-cells and B-cells.
- **Basophilic Stippling**: Associated with certain types of anemias and toxic states.
- **Platelets**: Involved in blood clotting, their count and morphology can signal various disorders.

![BloodImage_00234_2](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/61bdae98-220e-45b2-87ea-af00ebb6fe9e)

## Detailed Overview of Blood Cell Types

In this dataset, various blood cell types are represented, each with distinct functions and characteristics. Understanding these cell types is crucial for interpreting blood cell analysis in clinical settings.

### Erythrocytes (Red Blood Cells)

- **Function**: Erythrocytes are primarily responsible for the transportation of oxygen from the lungs to the body's tissues and the return of carbon dioxide from the tissues back to the lungs for exhalation. They achieve this through a protein called hemoglobin, which binds to oxygen and gives blood its red color.
- **Characteristics**: These cells are biconcave in shape, allowing for increased surface area to volume ratio, facilitating gas exchange. They lack a nucleus and organelles, maximizing space for hemoglobin. The average lifespan of erythrocytes is around 120 days, after which they are removed by the spleen and liver.
- **Clinical Relevance**: Abnormalities in erythrocyte count or morphology can indicate various conditions, such as anemia, polycythemia vera, or sickle cell disease.

### Leukocytes (White Blood Cells)

Leukocytes are essential components of the immune system, providing defense against infections and foreign invaders. They are categorized into several types:

#### Neutrophils

- **Function**: Neutrophils play a critical role in the innate immune response by rapidly responding to infections, particularly bacterial infections. They perform phagocytosis, engulfing and digesting microorganisms.
- **Characteristics**: These cells are the most abundant type of white blood cells, comprising approximately 55-70% of total leukocytes. They have a multi-lobed nucleus and granules in their cytoplasm that contain enzymes and antimicrobial substances.
- **Clinical Relevance**: Increased neutrophil counts can indicate infections or inflammation, while decreased levels may suggest bone marrow disorders or severe infections.

#### Basophils

- **Function**: Basophils are involved in inflammatory responses, particularly allergic reactions. They release histamine and other chemicals that promote blood flow to damaged tissues and attract other immune cells to the site of infection or injury.
- **Characteristics**: Basophils are the least common type of white blood cell, making up less than 1% of the total leukocyte count. They have large granules filled with histamine and other mediators, which can obscure their nucleus.
- **Clinical Relevance**: Elevated basophil levels can be associated with allergic reactions, chronic inflammation, or certain blood disorders.

#### Lymphocytes

- **Function**: Lymphocytes are key players in the adaptive immune response, with specialized functions in recognizing and remembering specific pathogens. They can be divided into three main types:
  - **B-cells**: Responsible for producing antibodies that target specific antigens on pathogens.
  - **T-cells**: There are several subtypes, including:
    - **Helper T-cells**: Assist other immune cells in responding to infections.
    - **Cytotoxic T-cells**: Directly attack and kill infected or cancerous cells.
- **Characteristics**: Lymphocytes are characterized by a large nucleus with minimal cytoplasm. They make up about 20-40% of total white blood cells.
- **Clinical Relevance**: Changes in lymphocyte levels can indicate viral infections, immune deficiencies, or malignancies such as leukemia or lymphoma.

### Basophilic Stippling

- **Function**: Basophilic stippling refers to the presence of small blue granules in red blood cells, indicative of certain pathophysiological conditions.
- **Characteristics**: These stipples are remnants of ribosomal RNA and are typically associated with disrupted hemoglobin synthesis or lead poisoning.
- **Clinical Relevance**: The presence of basophilic stippling can signal conditions such as thalassemia, sideroblastic anemia, or heavy metal poisoning.

### Platelets (Thrombocytes)

- **Function**: Platelets are crucial for blood clotting (coagulation) and maintaining hemostasis. They aggregate at sites of vascular injury to form a temporary plug that prevents blood loss.
- **Characteristics**: These cell fragments, derived from megakaryocytes in the bone marrow, lack a nucleus and are typically discoid in shape. They contain granules that store various substances involved in clotting.
- **Clinical Relevance**: Abnormal platelet counts can lead to excessive bleeding (thrombocytopenia) or increased clotting risk (thrombocytosis), impacting overall health and increasing the risk of cardiovascular events.


## Data Splitting


From this comprehensive dataset, **14 images** were meticulously selected for training purposes. Each image was annotated manually using the **MakeSense.ai** platform, with the annotations exported in **COCO JSON Format for Object Detection**. The annotations provide essential details such as bounding box coordinates and class labels, facilitating effective training of the detection model. 

Additionally, **3 images** were designated for validation to monitor the model's performance during training, while the remaining **322 images** were utilized for testing the model's capabilities on unseen data.

- **Training Set**: 14 images (combined into a single `.json` annotation file)
- **Validation Set**: 3 images (combined into a separate `.json` annotation file)
- **Testing Set**: 322 images

## Methodology

Utilizing the robust capabilities of Detectron2, the project executed both **Object Detection** and **Semantic Segmentation** tasks. 

- **Object Detection**: The model identifies and localizes objects within the images using bounding boxes, effectively highlighting the presence and position of each cell type.
- **Semantic Segmentation**: Each pixel in the image is classified into specific categories based on the identified objects, enabling a detailed view of the cellular structure.

The model's performance was rigorously evaluated on the test images, yielding impressive results that demonstrate its ability to accurately segment and classify blood cells.

![test_BloodImage_65_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/60b14b08-db23-4aab-bc67-cbf8d58639c5)

### Output: Segmented Masks

The implementation not only identifies the cells but also saves the **Binary Predicted Masks** for all **6 classes** present in each test image, allowing for a thorough analysis of segmentation accuracy and quality.

#### Example Segmented Masks from a Random Test Image:

- **Erythrocytes (Red Blood Cells)**

![test_BloodImage_61_Red Blood Cells_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/86aeba5c-d758-4a52-980d-7ae5101ebf8f)

- **Neutrophils**

![test_BloodImage_61_Neutrophil_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/3b4044a0-ffda-4d73-beab-769c42cac255)

- **Platelets**

![test_BloodImage_61_Platelet_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/22a4cec6-74a6-4175-98a5-e003f17b966e)

- **Basophilic Stippling**

![test_BloodImage_61_Basophilic Stippling_result](https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection/assets/112195431/72ef0f16-f9ac-4dc4-85ac-d6a1775277e8)

## Installation Guide

Follow these steps to set up the project in your local environment:

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/arpsn123/Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection.git
   cd Detectron2-HemaDetect-Blood-Cell-Segmentation-and-Detection
   ```

2. **Set Up a Python Virtual Environment (Recommended):**

   ```bash
   python -m venv venv
   source venv/bin/activate  # For Windows use `venv\Scripts\activate`
   ```

3. **Install Required Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Install Detectron2:**

   For installation instructions, refer to the official [Detectron2 installation guide](https://detectron2.readthedocs.io/en/latest/tutorials/install.html). Make sure to select the appropriate installation command based on your environment and CUDA version.


## Results

The results showcase the model's capabilities in accurately detecting and segmenting blood cells. Performance metrics such as **mean Average Precision (mAP)** and **Intersection over Union (IoU)** will be reported in the final analysis to quantify the model's effectiveness.

## Contributing

Contributions are welcome! If you wish to improve this project or report issues, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Commit your changes and push to your branch.
4. Open a pull request for review.


## Conclusion

This project not only highlights the powerful capabilities of Detectron2 in managing complex biological imaging tasks but also establishes a valuable resource for further research and development in medical image analysis. The insights gained from this analysis can significantly enhance the understanding of hematological conditions and improve diagnostic accuracy, ultimately contributing to better patient outcomes in clinical settings.

### Future Work

Future enhancements may include expanding the dataset with additional images, refining the segmentation algorithms, and integrating the model into a user-friendly application for broader accessibility in clinical environments.

---
