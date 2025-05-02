# PDF De-Identification Dataset

The **PDF Deid Dataset** is a fully synthetic collection of medical-style PDF documents created for de-identification tasks. All content is artificially generated using the Faker library and the GEMINI API, ensuring no real patient data is used. This dataset is ideal for training, benchmarking, and validating OCR and NLP models to identify and redact personally identifiable information (PII) in realistic medical document formats.

### Dataset Description

The dataset is divided into three levels: **Easy**, **Medium**, and **Hard**. The **Easy** set begins with 30 PDF files featuring clean layouts and consistent formatting. For the **Medium** set, 10 additional PDF files are added, each featuring completely different formatting styles compared to the initial 30, introducing increased structural variation.

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

##### Easy Layout Sections

The **Easy** set follows a structured format with the following sections:

- **Header**
- **Footer**
- **Patient Summary** (Paragraph)
- **Patient Demographics** (Form)
- **Patient Lifestyle** (Form)
- **Patient Vitals** (Form)
- **Doctor Information** (Form)
- **Doctor Notes Section** (Paragraph)
- **Past Hospital Visits** (Table)
- **Current Medications** (Table)
- **Medical Tests** (Table)

##### Variations

- PHI in sections like **Patient Demographics**, **Patient Lifestyle**, **Patient Vitals**, and **Doctor Information** can span multiple lines for complexity.
- The **Patient Summary** section may include PHI (Name, DOB, Age) in either form fields or free-text format.
- Tables in **Past Hospital Visits**, **Current Medications**, and **Medical Tests** can appear either with borders or without.

### Metrics
