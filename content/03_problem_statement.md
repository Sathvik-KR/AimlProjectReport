# Problem Definition and Objectives

## Problem Statement

Educational institutions maintain large amounts of student, internship, and company information in structured databases. However, retrieving specific information through traditional interfaces often requires users to navigate multiple pages, understand database fields, and apply filters manually.

The problem addressed by this project is the development of an AI-powered system that allows users to retrieve student and internship information using natural-language queries. The system accepts a user's question, identifies the intended operation and relevant entities, and retrieves matching records from a PostgreSQL database. It operates through a conversational web interface supported by an AIML service for natural-language processing.

## Research Question

Can sentence embedding-based intent classification, combined with named entity extraction, provide reliable natural-language access to student and internship information through predefined database query strategies?

The project also investigates whether this approach can reduce the need for users to understand database structures while maintaining accurate and relevant query results.

## Objectives

- **Develop an intent classification model:** Generate sentence embeddings using BGE-small-en-v1.5 and classify queries using Logistic Regression. Evaluate the model using accuracy, precision, recall, and F1-score.
- **Implement entity extraction:** Use a RoBERTa-based NER model to identify student and company names. Evaluate extraction performance using entity-level precision, recall, and F1-score.
- **Implement USN detection:** Use regular expressions to identify student USNs from queries and evaluate correctness against known identifiers.
- **Integrate NLP with database operations:** Connect the classification and extraction outputs to predefined Prisma query strategies. Verify that each supported intent retrieves the correct database records.
- **Develop a conversational interface:** Build a web interface that accepts natural-language queries and presents results in suitable formats, including tables and student profile information.
- **Implement fallback processing:** Provide basic keyword-based query handling when the AIML service is unavailable and test the system's ability to handle such situations.

## Success Criteria

The project is considered successful when the intent classifier achieves satisfactory performance on held-out test data, entity extraction identifies relevant student and company names, and USN detection correctly recognizes valid identifiers. Classification performance will be assessed using accuracy, precision, recall, and F1-score, while entity extraction will be evaluated using entity-level precision, recall, and F1-score.

At the application level, supported queries should retrieve relevant records without incorrect intent-to-strategy mapping. The conversational interface should display results clearly and handle unsupported or incomplete queries appropriately. The fallback mechanism should successfully process selected basic queries when the AIML service is unavailable.

These criteria will be assessed through model evaluation, representative test queries, database result verification, and end-to-end functional testing.

\newpage
