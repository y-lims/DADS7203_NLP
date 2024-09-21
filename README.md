# Information Extraction (IE)

Information Extraction (IE) refers to the task of extracting relevant information from text documents with the goal of generating **knowledge**. It encompasses a wide range of tasks such as keyword/keyphrase extraction, named entity recognition, relation extraction, event extraction, and more.

## IE Tasks

1. **Keyword or Keyphrase Extraction (KPE)**: Extracting important words and phrases that summarize the main idea of a text.
2. **Named Entity Recognition (NER)**: Identifying and classifying named entities (e.g., people, places, organizations) in text.
3. **Named Entity Disambiguation (NED) & Linking (NEL)**: Assigning unique identities to entities and linking them to knowledge bases.
4. **Relation Extraction**: Identifying relationships between entities in a text.
5. **Event Extraction**: Detecting and extracting event-related information.
6. **Temporal Information Extraction**: Extracting temporal (time-related) information.
7. **Template Filling**: Filling pre-defined templates with extracted information.

## IE Applications

- **News and Content Tagging**: Tagging articles and media content.
- **Chatbots**: Extracting specific information from large data pools.
- **Social Media**: Extracting time-sensitive and frequently updated information.
- **OCR**: Extracting data from forms, receipts, checks, and documents.

## General Pipeline for IE

IE requires more fine-grained natural language processing (NLP) than text classification. Key processes include:
- Part-of-speech tagging.
- Coreference resolution (to identify which entities pronouns refer to).
- Keyphrase extraction (minimal NLP).
- Deeper NLP processing for other tasks.

Evaluation of IE models typically involves **precision**, **recall**, and **F1 scores** using standard datasets.

# Keyphrase Extraction (KPE)

Keyphrase Extraction (KPE) is concerned with identifying important words and phrases that capture the essence of a text document. Applications of KPE include search, document tagging, recommendation systems, and text summarization.

### Implementing KPE with `textacy`

Two algorithms in `textacy` for keyphrase extraction are:
- **TextRank**: Effective for finding common and important single words or simple phrases.
- **SGRank**: Better suited for identifying more detailed and complex phrases.

### Practical Advice for KPE

1. **Document Length Sensitivity**: Keyphrase extraction may be more effective when applied to specific sections (e.g., introduction and conclusion) of long texts.
2. **Overlapping Keyphrases**: Similar keyphrases may overlap. To address this, use similarity measures (like cosine similarity) to choose distinct keyphrases.
3. **Unwanted Patterns**: Adjust the algorithm to avoid keyphrases starting with undesired words (e.g., prepositions).
4. **Poor Text Extraction**: Poor extraction (from PDFs, scans) can affect keyphrase extraction. Adding post-processing to clean keyphrases can help.

# Named Entity Disambiguation and Linking (NED & NEL)

## Named Entity Disambiguation (NED)

NED involves assigning a unique identity to entities mentioned in text, which is a key step toward understanding relationships between them.

## Named Entity Linking (NEL)

NEL combines **NER** and **NED** to link entities to knowledge bases. It is used in question answering systems, knowledge base construction, and other advanced NLP applications. NEL typically relies on additional NLP tasks such as:
- **Linguistic Parsing**: Identifying subject, verb, object relationships.
- **Coreference Resolution**: Resolving multiple mentions of the same entity.

NEL systems are evaluated by **precision**, **recall**, and **F1 scores** using standard test sets.

### NEL Using Azure API

The Azure API provides Named Entity Linking (NEL) functionality and is commonly used due to its ease of access (e.g., seven-day free trial). NEL through Azure allows users to link entities to external knowledge bases and gain deeper insights into entity relationships.

### Key Considerations for NEL

1. **Imperfections in NEL**: NEL systems may struggle with new or domain-specific terms, and the quality of other NLP steps (like parsing) can affect accuracy.
2. **Text Extraction Quality**: Poor-quality text extraction and cleanup can negatively impact NEL performance. When using third-party tools, there's limited control over customization or internal processes.

---

This README provides an overview of Information Extraction (IE) tasks, implementation strategies, and key considerations when working with Named Entity Linking (NEL) and Keyphrase Extraction (KPE) using practical tools like `textacy`.
