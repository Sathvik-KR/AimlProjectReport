# Introduction

## Background and Context

Educational institutions manage large volumes of student, internship, and company records. Retrieving specific information through traditional database interfaces can be time-consuming, especially when queries involve multiple conditions. Natural Language Processing (NLP) offers a more accessible approach by allowing users to retrieve information through everyday language. Recent advances in Transformer-based architectures have significantly improved natural language understanding and contextual text representation [@vaswani2017; @devlin2019].

This project develops an AI-powered Student Information System that converts natural-language queries into structured database operations. It combines an AIML service built with Python and FastAPI with a Next.js application connected to PostgreSQL through Prisma.

## Problem and Motivation

Students, faculty, and placement coordinators often need information based on student names, USNs, companies, or internship details. Traditional search interfaces require users to know the available fields and filters. Natural-language interfaces provide an alternative by allowing users to interact with databases without requiring direct knowledge of database query languages [@andersen1995].

The proposed system simplifies this process through a conversational interface. Users can ask questions naturally, while the system identifies the intended operation and relevant entities before retrieving matching records.

## Research Gap

General-purpose NLP systems may struggle with domain-specific student names, USNs, and company entities. Unrestricted natural-language database querying can also introduce complexity and reliability concerns.

This project addresses these challenges through domain-specific entity extraction, intent classification, and predefined database query strategies.

## Research Questions and Contributions

The project explores how sentence embeddings and classification can identify user intent, how Named Entity Recognition (NER) and regular expressions can extract relevant entities, and how these components can be integrated with controlled database operations. Sentence embedding techniques provide semantic representations that support intent classification across differently worded queries [@reimers2019].

Its main contributions include BGE-small sentence embeddings with Logistic Regression, RoBERTa-based entity extraction, regex-based USN detection, and a conversational interface with limited keyword-based fallback support.

## Scope and Assumptions

The system supports six predefined intents related to students, internships, companies, and greetings. It focuses on English-language queries and read-only database operations. It does not generate unrestricted SQL or support record modification. Its operation assumes an available database and configured models; fallback processing supports only selected basic queries.

\newpage
