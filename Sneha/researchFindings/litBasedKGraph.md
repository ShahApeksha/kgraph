 # A Literature-Based Knowledge Graph Embedding Method for Identifying Drug Repurposing Opportunities in Rare Diseases
1. How are they collecting data?
 The document describes the use of a knowledge graph called the Global
Network of Biomedical Relationships (GNBR) to synthesize information from
biomedical literature relevant to rare diseases.
 The GNBR contains edges or links between two entities from among the set
{gene, drug, disease} and a support score representing the literature-derived
confidence of the relationships between those two entities.
 The relationships are divided into 32 high-level semantic themes and are
organized into four categories based on the entities they connect.
 The authors then apply a knowledge graph embedding method that explicitly
models the uncertainty associated with literature-derived relationships and uses
link prediction to generate drug repurposing hypotheses.
2. How are they making graph data?
 The authors are using a knowledge graph called the Global Network of
Biomedical Relationships (GNBR), which contains edges or links between two
entities from among the set {gene, drug, disease} and a support score
representing the literature-derived confidence of the relationships between
those two entities.
 They then extracted rare disease information from Orphanet and identified
2,779 rare diseases in GNBR by matching MeSH and OMIM IDs and indirectly
matching UMLS IDs using the UMLS Metathesaurus.
 Finally, they filtered GNBR by identifying the largest connected component of
the graph after removing any node that is not (1) a gene node, (2) a high-priority
rare disease node, or (3) a drug/disease node present in a known indication.
3. What techniques are they using to build knowledge graph?
 Natural language processing (NLP) techniques is used to process large bodies of
unstructured text and synthesize and summarize the relationships between
drugs, genes/proteins, and diseases into a heterogeneous knowledge graph
known as the Global Network of Biomedical Relationships (GNBR).
 They then apply a knowledge graph embedding method that explicitly models
the uncertainty associated with literature-derived relationships and uses link
prediction to generate drug repurposing hypotheses.
4. From the knowledge graph how are they proceeding to achieve their end goal?
 From the above mentioned techniques they build the knowledge graph.
 This approach achieves high performance on a gold-standard test set of known
drug indications and is capable of generating novel repurposing hypotheses,
which they independently validate using external literature sources and protein
interaction networks.
 Finally, they demonstrate the ability of their model to produce explanations of
its predictions.
5. What about graph embedding?
 Graph embedding methods learn a mapping from nodes and edges to low-
dimensional vectors such that the proximity structure of the original network is
preserved in the embedding space.
 These methods have been applied in pharmacological applications such as the
prediction of polypharmacy side effects and drug-drug interactions.
 The resulting vectors provide an ideal platform for machine learning tasks.
 In the context of drug repurposing, a literature-based knowledge graph
embedding method has been implemented that explicitly models the confidence
of relationships in GNBR based on their evidence in literature.
 This model is more appropriate for representing and learning from literature-
based knowledge, which is inherently noisy.