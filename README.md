# Synthetic training data generation from a single image for enhanced breast cancer diagnosis

Here I share the code developed for my thesis for the MSc in Fundamental Principles of Data Science at [Universitat de Barcelona](https://web.ub.edu/en/home).

```
Buetas, M. (2023) Synthetic training data generation from a single image for enhanced breast cancer diagnosis. Universitat de Barcelona.
```

## Description of the project

According to the [World Health Organisation (WHO)](https://www.who.int/news-room/fact-sheets/detail/cancer), breast cancer is one of the cancer types with a high prevalence worldwide. Deep-learning based computer-aided detection systems have shown promising potential in improving the curability and reducing mortality rates through early detection in mammography screening.

Artificial Intelligence (AI) has become a popular tool in medicine, aiming to reduce costs and assist radiologists in decision-making processes. However, AI in cancer imaging presents significant challenges, including data access and privacy issues, as well as a scarcity of expert-annotated medical imaging. Motivated by these factors, this project aims to enhance the robustness and generalisability of breast cancer classification tools. The study focuses on obtaining a pre-biopsy result of suspicious areas in mammograms, providing a comprehensive assessment of lesion nature. 

Firstly, it was observed that the classifier's performance for the malignant class was inferior to that of the other classes, and the tightness of the annotation mask around the lesion significantly influenced the classifier's performance. To improve the performance for malignant lesions, the study investigates SinGAN-based data augmentation to balance this underrepresented class. To the best of our knowledge, this project represents a novel investigation into the application of single-image generative models for breast cancer, addressing the challenge of expert annotation scarcity. Promising results were observed through the use of SinGAN-based data augmentation. The classification model, trained with SinGAN-augmented training data, demonstrated a higher AUC value for the malignant class ($0.718 \pm 0.044$), compared to the same model without augmented data ($0.677\pm0.076$). However, an unexpected trend was also identified during the experiments. It was observed that using more SinGANs for data augmentation did not always result in a higher enhancement of performance. 

This project opens up new research possibilities through collaboration with healthcare experts. Its ultimate goal is to achieve the necessary robustness and trustworthiness of AI-based applications for adoption in the clinical workflow.

## Methods and material

- For this project, patches were extracted from the mammograms, including both lesion and healthy areas, in both scanned and digital formats. The technique followed for generating the patch dataset is explained in detail in the Python notebook `generate_patch_dataset.ipynb`. To generate the dataset, the BCDR dataset needs to be downloaded. Three metadata .csv files are also generated, one for lesions, another for healthy digital patches, and a third one for scanned film patches. These files contain the corresponding data required for the project objectives, each with a unique ID for each patch. To convert the previously generated .csv files into a unified .jsonl metadata file, the Python script `csv_to_jsonl_metadata.py` is used. Additionally, the patches containing lesions are extracted with varying percentages of adjacent healthy tissue or different levels of zoom. This approach serves two purposes: exploring the model's robustness against different window sizes used in the sliding window procedure for lesion detection, and analysing the influence of the annotation's tightness to the lesion on the performance of a classifier. 

- 

SinGAN official repository...

