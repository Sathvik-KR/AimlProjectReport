##### Appendices

###### Appendix A: Model Configuration

- **Embedding model:** `BAAI/bge-small-en-v1.5`
- **Classifier:** Logistic Regression
- **Intent classes:** 6
- **Dataset split:** 840 training, 180 validation, and 180 test queries
- **NER model:** `Jean-Baptiste/roberta-large-ner-english`
- **USN extraction:** Regular expressions
- **Frameworks:** FastAPI, Next.js, React, and TypeScript
- **Database:** PostgreSQL with Prisma ORM

###### Appendix B: Data Dictionary

- **Students:** Student ID, USN, name, email, and creation timestamp.
- **Companies:** Company ID and company name.
- **Internships:** Internship ID, student ID, company ID, start date, and end date.

Internship records connect students with companies and support queries based on student or company information.

###### Appendix C: Supported Intents

The system supports six intents: `all_students`, `internships_by_student`, `all_companies`, `all_internships`, `internships_by_company`, and `greetings`.

Intent classification is combined with entity extraction to select predefined database query strategies.

###### Appendix D: Sample Query

**Input:** `Show internships completed by Rahul at Microsoft`

**Extracted output:**

```json
{
  "intentId": "INT002",
  "intent": "internships_by_student",
  "extracted_data": {
    "student_names": ["Rahul"],
    "student_usns": [],
    "company_names": ["Microsoft"]
  }
}
```

The Next.js backend uses the predicted intent and extracted entities to retrieve matching records from PostgreSQL through Prisma.

###### Appendix E: API Endpoints

**FastAPI (Port 8000)**

- `GET /` — Service information.
- `GET /health` — Health check.
- `POST /query` — Intent classification and entity extraction.

**Next.js (Port 3000)**

- `POST /api/query` — Query processing and database retrieval.

###### Appendix F: Evaluation Metrics

Intent classification is evaluated using accuracy, precision, recall, F1-score, and a confusion matrix. Entity extraction is assessed through person and organization recognition, while USN extraction is checked for identifier correctness.

###### Appendix G: Privacy and Security

The system uses predefined database queries instead of unrestricted SQL generation. Student records require appropriate access controls, secure database credentials, and protection against exposing sensitive information in logs or error messages.
