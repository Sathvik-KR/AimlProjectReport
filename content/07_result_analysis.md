# Results and Analysis

## Model Performance Comparison

The proposed BGE-small-en-v1.5 with Logistic Regression model was evaluated against a TF-IDF with Logistic Regression baseline using the same training, validation and test splits. The held-out test set contained 180 queries distributed across six intent classes.

The proposed model achieved an accuracy of 91.11%, outperforming the baseline accuracy of 84.44%. The improvement indicates that sentence embeddings capture semantic similarities between differently worded queries more effectively than traditional TF-IDF representations.

<!-- col-w: 33 20 15 23 36 | align: center center center center center -->

--------------------------------- -------------------- --------------- ----------------------- ------------------------------------
 Method                            Evaluation Set       Accuracy (%)    Weighted F1-score (%)   95% Confidence Interval (Accuracy) 
--------------------------------- -------------------- --------------- ----------------------- ------------------------------------
 TF-IDF + Logistic Regression      Test (180 samples)   84.44           84.12                   78.4–89.0%                         

 BGE-small + Logistic Regression   Test (180 samples)   91.11           90.87                   85.9–94.5%                         
--------------------------------- -------------------- --------------- ----------------------- ------------------------------------

Table: Intent Classification Performance

## Learning Curve Analysis

The learning curves illustrate how model performance changes as the training dataset increases. The proposed model shows consistent improvement with additional training samples, indicating that it benefits from more representative query examples.

The training and validation scores gradually converge as the dataset grows. A small difference between the two curves indicates reasonable generalization, with no significant evidence of overfitting. The TF-IDF baseline also improves with additional samples, but its validation performance remains lower than that of the proposed model.

The learning curves demonstrate that BGE embeddings provide a stronger representation of natural-language queries, particularly when users express the same intent using different sentence structures.

## Confusion Matrix Analysis

The confusion matrix evaluates predictions across the six intent classes: all students, internships by student, all companies, all internships, internships by company and greetings.

Most queries are correctly classified. A small number of errors occur between related intents, particularly between internships by student and internships by company. These queries may contain overlapping student and company information, making intent identification more challenging.

![Intent Classification](assets/images/aiml_clg_intent_classification.jpg){width=5in height=3in}

The proposed model produces fewer incorrect classifications than the TF-IDF baseline, demonstrating improved intent recognition across different query types.

## Entity Extraction Analysis

The RoBERTa-based NER model extracts student names and company names from natural-language queries. The regular-expression-based component identifies USNs using their predefined format.

Entity extraction performs effectively when names and identifiers are clearly stated. Errors mainly occur with unfamiliar names, ambiguous organization names and incomplete queries. Incorrect entity extraction can affect the accuracy of subsequent database retrieval even when the intent is correctly classified.

## Error and Functional Analysis

The system successfully handles common queries involving student records, internships, companies and greetings. It also supports queries containing multiple entities, such as a student name combined with a company name.

Errors are primarily associated with ambiguous wording, unfamiliar names, incomplete information and queries that do not match the supported intent classes. The predefined query strategies ensure that recognized intents are handled through controlled database operations rather than unrestricted SQL generation.

## Runtime and Resource Analysis

The AIML service performs intent classification and entity extraction independently of the Next.js backend. The transformer models require additional memory and processing resources during initialization and inference.

The Next.js backend handles request orchestration, strategy selection and database retrieval. When the AIML service is unavailable, the keyword-based fallback supports basic queries, while entity-dependent queries require the AIML service.

## Overall Analysis

The results indicate that BGE-small-en-v1.5 with Logistic Regression provides better intent classification performance than the TF-IDF baseline. Its ability to represent semantic relationships between sentences improves recognition of queries with different wording but similar meanings.

Combined with RoBERTa-based entity extraction and regular-expression-based USN detection, the proposed architecture provides a practical natural-language interface for retrieving student placement and internship information.

\newpage
