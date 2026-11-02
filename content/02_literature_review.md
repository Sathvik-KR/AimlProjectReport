# Literature review approach

This project uses a focused narrative review of research on natural-language interfaces to databases, intent classification, sentence embeddings, and named entity recognition. Relevant studies can be identified through Google Scholar, IEEE Xplore, ScienceDirect, and ACL Anthology using keywords such as Natural Language Interface to Databases, Intent Classification, Sentence Embeddings, BERT, Named Entity Recognition, and Question Answering over Databases. The review focuses primarily on work published between 2018 and 2025, while including earlier foundational research where relevant. Studies are selected based on their relevance to NLP-based information retrieval, methodology, reported findings, and applicability to structured student data.

## Literature review 

<!-- col-w: 51 47 55 77 | align: center center center center -->

--------------------------------------------------- ----------------------------------------------- ------------------------------------------------------- -----------------------------------------------------------------------------
 Study and year                                      Data and method                                 Key finding                                             Limitation and relevance                                                    
--------------------------------------------------- ----------------------------------------------- ------------------------------------------------------- -----------------------------------------------------------------------------
 BERT (Devlin et al., 2018)                          Large text datasets; Transformer pre-training   Improves contextual language understanding              Needs fine-tuning; relevant to entity extraction                            

 Sentence-BERT (Reimers and Gurevych, 2019)          Sentence pairs; Siamese BERT networks           Generates semantically meaningful sentence embeddings   May need domain adaptation; relevant to intent classification               

 Neural NLP Survey (Young et al., 2018)              Review of neural NLP techniques                 Highlights advances in language representation          Broad coverage; provides methodological background                          

 BGE (Xiao et al., 2023)                             Large text datasets; contrastive learning       Produces effective text embeddings                      Performance depends on the task; relevant to query representation           

 Natural Language Interfaces to Databases (Survey)   Review of natural-language database querying    Enables accessible database interaction                 Domain-specific queries remain challenging; motivates predefined strategies 
--------------------------------------------------- ----------------------------------------------- ------------------------------------------------------- -----------------------------------------------------------------------------

Table: Literature review

## Thematic synthesis and research gap

The reviewed work highlights three important areas: contextual language representation, semantic sentence embeddings, and natural-language database interaction. Transformer-based models support entity recognition, while sentence embeddings enable semantic comparison of user queries for intent classification. Research on natural-language database interfaces demonstrates the potential of conversational data retrieval but also highlights challenges in handling domain-specific information and generating reliable database operations.

However, these approaches do not directly address the combined requirements of student-specific entity extraction, intent recognition, and controlled database retrieval. This project addresses that gap by combining BGE-small sentence embeddings with Logistic Regression for intent classification, RoBERTa for entity extraction, and regular expressions for USN detection. The extracted information is then processed through predefined Prisma query strategies rather than unrestricted SQL generation.

\newpage
