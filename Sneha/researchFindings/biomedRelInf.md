# Biomedical relation inference via embeddings
1. How are they collecting data?
 The document mentions that the corpus for embedding consisted of
approximately 28.6 million PubMed abstracts downloaded from PubTator along
with their corresponding annotations, which resulted in approximately 153.3
million processed sentences.
 The training data for the supervised prediction models was mined from the
dependency paths present in GNBR.
2. How are they making graph data from the raw data?
 The authors are not explicitly making graph data from the raw data in this paper.
 Instead, they focus on using Word2Vec embeddings as a representation of
biomedical entities and relationship phrases.
 The embeddings serve as a foundation for their approach to relationship
modeling
3. .What techniques are they using to build knowledge graph?
 The techniques used to build the knowledge graph in this paper involve mining
multi-word phrases from PubTator and the Relation Ontology.
 These phrases are further augmented based on observed relationship types in
the dependency paths found in the GNBR database.
 The resulting set of phrases forms the basis for the knowledge graph
construction.
4. From the knowledge graph how are they proceeding to achieve their end goal?
 From the knowledge graph, the authors proceed to achieve their end goal by
utilizing the Word2Vec embeddings as training data for two supervised learning
tasks.
 These tasks involve classifying relations given subject and object, as well as
predicting objects given subject and relation.
 By training on these tasks, they aim to accurately identify relationships, recover
known interactions, and generate novel hypotheses in the biomedical field.
5. What is their graph algorithm strategy (eg., centrality, path finding etc)
 Their graph algorithm strategy involves using the embeddings and training data
derived from the knowledge graph to perform various analyses.
 While the specific algorithms used are not explicitly mentioned, the approach
seems to emphasize the utilization of Word2Vec embeddings to enable tasks
such as relationship prediction, information retrieval, and potentially other
analyses based on the constructed knowledge graph.
 The focus is on leveraging Word2Vec embeddings and the supervised learning
tasks to achieve the desired outcomes
6. What about graph embedding?
 Graph embedding is not the primary focus of this paper. Instead, the authors
utilize Word2Vec embeddings to represent biomedical entities and relationship
phrases in a shared embedding space.
 These embeddings facilitate the construction of the knowledge graph and are
used as training data for the supervised learning tasks.
 The paper does not delve into more advanced graph embedding techniques
beyond the use of Word2Vec