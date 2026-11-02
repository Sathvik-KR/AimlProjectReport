# Experimental Design

## Baseline Models

The proposed BGE-small embedding-based Logistic Regression classifier is evaluated against simpler classification approaches. These include a majority-class baseline and a TF-IDF-based Logistic Regression classifier. All models use the same dataset splits to ensure a fair comparison.

## Evaluation Protocol

The natural-language query dataset is divided into training, validation, and test subsets using a 70:15:15 ratio.

- Training: 840 queries.
- Validation: 180 queries.
- Testing: 180 queries.

The training set is used for model training, the validation set for model selection, and the test set for final performance evaluation. The test data remains separate from the training and tuning process.

## Evaluation Metrics

The following metrics are used to evaluate intent classification and entity extraction:

- **Accuracy:** Measures the proportion of correctly classified queries.
- **Precision:** Measures how many predicted instances of a class are correct.
- **Recall:** Measures how many actual instances of a class are identified correctly.
- **F1-score:** Represents the harmonic mean of precision and recall.
- **Confusion Matrix:** Shows correct and incorrect predictions across all intent classes.

Entity extraction is evaluated using entity-level precision, recall, and F1-score. USN extraction is evaluated by comparing extracted identifiers against the expected values.

## Uncertainty and Statistical Analysis

Model performance is evaluated using the held-out test dataset. Precision, recall, and F1-score are examined across individual intent classes to identify variations in classification performance.

The confusion matrix is used to identify frequently misclassified intents. Since the dataset is limited in size, results are interpreted within the scope of the available samples.

## Ablation and Robustness Testing

The system is evaluated by examining the contribution of its individual components. Intent classification is tested using different feature representations, including TF-IDF and BGE-small embeddings.

Entity extraction is tested independently for student names and company names, while regular-expression-based USN extraction is evaluated using valid and invalid identifier examples.

End-to-end testing is also performed using queries with different wording, missing entities, multiple entities, and unsupported requests. Fallback functionality is tested when the AIML service is unavailable.

## Reproducibility

The implementation uses Python, FastAPI, Sentence Transformers, Scikit-learn, and Hugging Face Transformers for NLP development. The web application uses Next.js, TypeScript, Prisma, and PostgreSQL.

The trained classifier, embedding model, and entity extraction model are maintained as separate components. Dataset versions, model configurations, dependencies, and training settings are documented to support consistent execution and future evaluation.

\newpage
