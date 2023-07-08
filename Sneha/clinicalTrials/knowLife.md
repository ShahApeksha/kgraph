# KnowLife: a Knowledge Graph for Health and Life Sciences
Doi- 10.1109/ICDE.2014.6816754
1. Introduction:
- Motivation:
  - Knowledge bases like dbpedia.org, freebase.com, and yago-knowledge.org have limitations in providing domain-specific knowledge in health and life sciences.
  - Universal knowledge bases are insufficient for interesting use-cases that require depth and coverage in the health and life sciences domain.
- Prior work:
  - Existing biomedical knowledge bases, such as disease-ontology.org and omim.org, are manually built and lack integration and coverage.
  - There is a need for a one-stop portal that comprises knowledge on all health-related aspects in an integrated manner.
- Contribution:
  - KnowLife aims to automatically construct and maintain a knowledge base specifically focused on health and life sciences.
  - It integrates knowledge from various web sources and provides provenance information for facts.
  - KnowLife allows real-time annotation of documents and offers several use-case scenarios.

2. Knowledge Harvesting from Web Sources:
- Named Entity Recognition and Disambiguation:
  - The system identifies sentences in web sources that may express relational facts using a dictionary-based method.
  - Entities in these sentences are mapped to the Unified Medical Language System (UMLS).
- Pattern Mining:
  - Salient patterns connecting entities in candidate sentences are computed using a statistics-based approach.
  - The patterns are weighted based on confidence and support, learned from seed facts.
- Consistency Reasoning:
  - A Weighted Max Sat Solver is used to reason over the mutual consistency of fact candidates.
  - Consistency constraints, such as type signatures of relations and mutual exclusions, are applied to achieve high-quality facts.

3. Text Annotation:
- Pattern Matching:
  - Entities are discovered and mapped to the knowledge base using dictionary-based methods and salient patterns learned during knowledge harvesting.
  - Salient patterns are matched against sentences, and fact candidates are generated based on partial-match results.
- Type Checking:
  - Fact candidates are filtered based on the type signatures of relations to ensure compatibility between arguments and relations.
- On-the-fly Annotation:
  - Ad-hoc text is annotated in real time, allowing users to explore entities and facts as they read documents.
  - Entities and relationships mentioned in the text are marked and linked to relevant information in the knowledge base.

4. Demo Scenarios:
- Layman Scenario:
  - Laymen can annotate their own posts or texts of interest to quickly access relevant information about recognized entities.
  - Annotated entities provide links to information about causes, risk factors, symptoms, etc.
  - Laymen can explore textual evidence and access Wikipedia articles prepared for speed-reading via annotated entities and facts.
- Health Care Professional Scenario:
  - Medical professionals can use KnowLife to deepen their knowledge in specific areas and stay updated with the latest research.
  - Relevant scientific information aggregated from multiple articles is accessible through links in the knowledge base.
  - Clinical trials related to specific diseases can be accessed directly from the knowledge base.
