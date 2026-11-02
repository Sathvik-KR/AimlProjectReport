# Conclusion and Future Work

## Conclusion

This project developed an AI-powered Student Information System that enables users to retrieve student placement and internship information through natural-language queries. The system addresses the limitations of traditional database interfaces by allowing users to request information without manually navigating database tables or filters.

The proposed approach combines BGE-small-en-v1.5 sentence embeddings with Logistic Regression for intent classification, RoBERTa for student and company entity extraction, and regular expressions for USN identification. These components are integrated with a FastAPI-based AIML service and a Next.js application using Prisma and PostgreSQL. Predefined query strategies process the classified intent and extracted entities to retrieve relevant records.

In the evaluation, the proposed BGE-based classifier achieved 91.11% accuracy and a weighted F1-score of 90.87% on the 180-query test set, outperforming the TF-IDF baseline, which achieved 84.44% accuracy and an 84.12% weighted F1-score. These results support the use of sentence embeddings for improved natural-language intent classification in the proposed system.

The main limitation is the relatively small and institution-specific dataset, which may restrict generalisation to unfamiliar names, different query patterns and other institutions. The system also depends on transformer-based services for complete entity extraction and query processing.

## Future Work

The following improvements can extend the system:

- **Dataset expansion:** Include more queries, institutions, naming patterns and variations in natural-language expressions.
- **Multilingual support:** Extend query processing to regional languages and mixed-language inputs.
- **Improved entity extraction:** Improve recognition of unfamiliar student names, company names and ambiguous references.
- **Conversation context:** Support follow-up questions using information from previous queries.
- **Performance optimisation:** Reduce model loading time and inference latency through model optimisation and efficient deployment.
- **Enhanced security:** Introduce role-based access control, audit logging and stronger protection for sensitive student records.
- **Expanded functionality:** Support additional placement-related queries, analytics and authorised database operations.

Overall, the project establishes a foundation for natural-language access to institutional student information. Further improvements in dataset diversity, entity extraction, security and deployment efficiency can make the system more reliable and suitable for broader institutional use.

\newpage
