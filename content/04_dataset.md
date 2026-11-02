# Dataset and Materials

## Dataset Source and Provenance

The dataset used in this project was provided by college faculty in Microsoft Excel format. It contains student, internship, and company-related information collected as part of institutional placement activities. The dataset was supplied internally for academic project development and was not obtained from a public source.

The original spreadsheet contained inconsistencies and formatting issues, requiring preprocessing before database integration. Its use was restricted to the requirements of this project.

## Dataset Description

The institutional dataset consists of approximately 1,000 student records, 150 company records, and 300 internship records.

Student records include names, USNs, and academic details, while internship records contain company names, internship periods, and related information.

A separate natural-language query dataset contains 1,200 samples distributed across six predefined intent classes:

- All students
- Internships by student
- All companies
- All internships
- Internships by company
- Greetings

Each class contains 200 query samples.

## Data Preprocessing and Quality Checks

The original Excel data contained inconsistent formatting and incomplete values. The following preprocessing steps were performed:

- Standardizing column names and data formats.
- Correcting inconsistent text formatting.
- Removing duplicate records where identified.
- Handling missing and incomplete fields.
- Checking student USNs and company names for consistency.
- Organizing the data into structured database tables.

The cleaned records were then used to populate the PostgreSQL database.

## Eligibility, Privacy and Ethics

Only student and internship information relevant to the project was considered. Since the dataset contains institutional student information, it is treated as internal project data and is not publicly distributed. Its use is restricted to academic development and evaluation.

## Dataset Splitting

The natural-language query dataset was divided into training, validation, and testing subsets using a 70:15:15 ratio.

- Training: 840 queries (70%).
- Validation: 180 queries (15%).
- Testing: 180 queries (15%).

The training subset was used to train the Logistic Regression classifier, while the validation subset supported model selection. The test subset was reserved for final performance evaluation.

The institutional Excel dataset supports database operations, whereas the natural-language query dataset is used for NLP model training and evaluation.

\newpage
