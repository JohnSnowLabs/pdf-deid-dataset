# PDF De-Identification Dataset

The **PDF Deid Dataset** is a fully synthetic collection of medical-style PDF documents created for de-identification tasks. All content is artificially generated using the Faker library and the GEMINI API, ensuring no real patient data is used. This dataset is ideal for training, benchmarking, and validating OCR and NLP models to identify and redact personally identifiable information (PII) in realistic medical document formats.

### Dataset Description

The dataset is divided into three levels: **Easy**, **Medium**, and **Hard**. The **Easy** set begins with 30 PDF files featuring clean layouts and consistent formatting. The **Medium** level builds on this by adding 10 more PDF files introducing varied formatting and noise. The **Hard** level includes all previous files, plus 10 more PDFS with further document formats like complexity and noise.

##### PHI Entities

The dataset contains the following **Personally Identifiable Information (PII)** entities, designed to simulate real-world clinical records:

- Patient Name
- Patient Date of Birth (DOB)
- Patient Age
- Patient Social Security Number (SSN)
- Hospital ID
- Doctor Name
- Doctor ID
- Hospital Name
- Hospital Contact
- Other Dates

##### Layout Sections

- **Header**
- **Patient Summary** (Paragraph)
- **Patient Demographics** (Form)
- **Patient Lifestyle** (Form)
- **Patient Vitals** (Form)
- **Doctor Information** (Form)
- **Doctor Notes Section** (Paragraph)
- **Past Hospital Visits** (Table)
- **Current Medications** (Table)
- **Medical Tests** (Table)
- **Footer**

##### Variations

- PHI in sections like **Patient Demographics**, **Patient Lifestyle**, **Patient Vitals**, and **Doctor Information** can span multiple lines for complexity.
- The **Patient Summary** section may include PHI (Name, DOB, Age) in either form fields or free-text format.
- Tables in **Past Hospital Visits**, **Current Medications**, and **Medical Tests** can appear either with borders or without.
- Medium PDF files feature a different layout and include added noise such as ink bleed, dirty screen effects, and subtle background textures.
- Hard PDF files contain densely packed information on single lines, which can challenge OCR systems. Additional noise includes punch holes (left margin), binder clips (right margin), noise texturisation, and moire patterns.

### Data Distribution 

| Level             | Files Included | Avg. PHI Entities | % of Total PHI                                                    |
|-------------------|----------------|-------------------|---------------------------------------------------------------------------------------------------------|
| 🟢 Easy           | 30           | 41                | DATE [50%], NAME [15%], HOSPITAL/ORGANISATION [15%], Phone Number [7.5%], AGE [5%], IDNUM [7.5%]
| 🟡 Medium         | 10           | 52                | DATE [38.8%], NAME [24.5%], ADDRESS [20.4%], Phone Number [4.1%], AGE [4.1%], IDNUM [8.1%]
| 🔴 Hard           | 10           | 46                | DATE [43.9%], NAME [22%], ADDRESS [12.2%], Phone Number [7.3%], AGE [4.9%], IDNUM [9.8%]                      

### File Description

  - **Visual_NLP_Metrics.ipynb**  
    - Guide for calculating NLP metrics using JSL packages.  
    - No pretrained pipeline included.
  
  - **Visual_NLP_Pretrained_Metrics.ipynb**  
    - Guide for calculating NLP metrics using JSL packages.  
    - Pretrained pipeline included.
  
  - **Visual_NLP_ZeroShot_Metrics.ipynb**  
    - Guide for calculating NLP metrics using JSL packages.  
    - Uses zero-shot stages for specific PHI detection.

  - **PDF Original:**
    - **Easy**  [ Contains 30 Easy PDF Files ]    
    - **Medium**  [ Contains 10 Medium PDF Files ]
    - **Hard**  [ Contains 10 hard PDF Files ]

  - **Mapping:**
    - **Ground Truth Files**  [ JSON files `pdf_deid_gts_*.json` contain ground truth data. ]
    - **Predicted Mapping Files**  [ JSON files `*_result_mapping.json` have predicted values, ground truth, precision, and recall. ]
      
- **Sample Result:** [ Contains PDF example outputs with black bbox in place of PHI. ]
    
### Metrics

| Difficulty Level | Precision | Recall | F1-Score | Total Files |
|------------------|-----------|--------|----------|---------|
| 🟢 Easy          | 0.9851      | 0.9799   | 0.9825    | 30     |
| 🟡 Medium        | 0.9800      | 0.9575   | 0.9686     | 40     |
| 🔴 Hard        | 0.9561      | 0.9290   | 0.9424     | 50     |
