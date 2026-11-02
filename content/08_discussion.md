# Discussion

## Interpretation of Results

The evaluation results indicate that the proposed BGE-small-en-v1.5 with Logistic Regression model performs better than the TF-IDF baseline for intent classification. The proposed model achieved 91.11% accuracy and a weighted F1-score of 90.87%, compared with 84.44% accuracy and 84.12% weighted F1-score for the baseline.

These results support the objective of improving intent classification through sentence embeddings. BGE embeddings capture semantic relationships between queries more effectively than traditional word-frequency representations. The results are consistent with research on sentence embeddings, which demonstrates the effectiveness of semantic representations for capturing relationships between differently worded sentences [@reimers2019; @xiao2023].

The RoBERTa-based entity extraction component and regular-expression-based USN detection address the objective of identifying relevant student and company information. Together, these components allow the system to process queries containing multiple entities and retrieve relevant database records through predefined query strategies. Transformer-based models such as RoBERTa provide contextual representations that support named entity recognition [@liu2019roberta; @li2022ner].

The results support the research question that combining semantic intent classification with entity extraction can provide an effective natural-language interface for student information retrieval. However, classification performance alone does not establish perfect end-to-end retrieval accuracy, since entity extraction and database matching also influence the final response.

## Practical Significance and Deployment Considerations

The system reduces the need for users to navigate multiple database screens or understand database structures. Students, faculty members and placement coordinators can retrieve information using familiar natural-language queries.

The use of predefined Prisma query strategies provides controlled database access and avoids the risks associated with generating unrestricted SQL statements. Separating the AIML service from the Next.js application also improves modularity and allows both services to be developed and maintained independently. The use of FastAPI for the AIML service and Next.js for the web application provides established frameworks for building API-driven applications and web interfaces [@fastapi_docs; @nextjs_docs].

The main trade-off is computational resource usage. Transformer-based embedding and NER models require additional memory and initialization time compared with traditional keyword-based approaches. The system also depends on the availability of the AIML service for entity-dependent queries. The fallback classifier provides limited functionality when the AIML service is unavailable.

## Limitations

The dataset contains approximately 1,000 student records, 150 company records, 300 internship records and 1,200 natural-language queries across six intent classes. Although this provides a foundation for evaluation, it may not represent the full range of language patterns used across different institutions.

The classifier may perform differently when exposed to unfamiliar names, new company names, regional language variations, spelling errors and queries outside the training distribution. Generalisation to other institutions may require additional training examples and domain-specific evaluation. The performance of machine learning models depends on the representativeness of training data and the consistency of evaluation procedures [@pedregosa2011].

Data leakage is another potential concern. Similar or duplicated queries appearing across training and test sets could inflate evaluation scores. Careful dataset splitting and duplicate removal are therefore important for reliable assessment.

The reported evaluation metrics also contain statistical uncertainty because they are calculated from a limited test set of 180 queries. Performance may vary with different test samples. Entity extraction errors and ambiguous entity references can further reduce end-to-end retrieval reliability.

Potential bias may arise from the representation of names, organizations and query styles in the training data. Underrepresented naming patterns or language variations may result in lower recognition accuracy for certain users.

## Ethical and Societal Implications

The system processes student information, including personal identifiers and internship records. Access to this information must be restricted to authorized users, and sensitive records should be protected through appropriate authentication, authorization and secure data handling.

The system uses predefined database queries rather than unrestricted SQL generation, reducing the possibility of unintended database operations. However, controlled queries alone do not guarantee privacy; access permissions and data protection measures remain essential. PostgreSQL provides database-level capabilities for managing access and protecting stored information, which can support the implementation of appropriate data security controls [@postgresql_docs].

A natural-language interface can improve accessibility by allowing users with limited technical knowledge to retrieve institutional information. At the same time, incorrect classifications or entity extraction may produce incomplete or misleading results. Users should therefore be able to verify important information through the institution's official records.

## Summary

The proposed system demonstrates the practical value of combining sentence embedding-based intent classification, named entity recognition and predefined database query strategies. The evaluation supports the use of BGE embeddings over the TF-IDF baseline and demonstrates the potential of natural-language interaction for student information retrieval. Dataset limitations, computational requirements, privacy concerns and generalisation challenges must be considered before deployment in a larger institutional environment.

\newpage
