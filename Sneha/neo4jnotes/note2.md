# Title: 062 Graph-Based Features for Recommendation Systems in Drug Discovery - NODES2022 - Ben Vozza

-A recommendation system is a technology that analyzes user data and preferences to suggest relevant items or content. It is commonly used by platforms like Netflix to recommend movies and TV shows based on a user's viewing history, preferences, and other attributes.

-In drug discovery, scientists face a similar challenge as those at Netflix. They have thousands of potential genes to examine and determine which ones may be involved in a particular disease. The goal is to identify target genes for potential drug development and treatment.

-Initially, scientists may use high-throughput screening techniques to narrow down the list of genes. However, even after this step, they may still be left with thousands of genes to evaluate. This is where recommendation systems can be extremely helpful.

-By incorporating biological evidence, clinical data, literature information, and other relevant features, recommendation systems can prioritize and rank the genes. This helps scientists create a shortlist of the most promising genes to investigate further, saving them valuable time and resources.

-The success of recommendation systems in drug discovery is evident in various studies. For example, Insilico Medicine published a paper on the identification of novel genes for ALS (Amyotrophic Lateral Sclerosis), while AstraZeneca used gene recommendation systems to study drug resistance in EGFR (Epidermal Growth Factor Receptor).

-When building a gene recommendation system, using graph-based features in a database like Neo4j is advantageous. Biology naturally follows a network-like structure, where genes interact and influence each other within a cell. No gene acts in isolation. By modeling biological interactions as a graph, researchers can better understand the complexity of molecular biology.

-Neo4j, as a graph database, provides an efficient way to store, query, and analyze graph data. It allows researchers to capture the relationships between genes, diseases, drugs, and other relevant factors. Hetionet is an example of a biomedical knowledge graph that utilizes a graph database and has been successful in the field.

Overall, employing recommendation systems and leveraging graph-based features in databases like Neo4j can significantly aid drug discovery efforts by efficiently prioritizing genes and understanding their interactions within complex biological systems.

Building graph-based features using Neo4j and Cypher can greatly benefit drug discovery efforts. Here are some examples of how Neo4j and Cypher can be used to create features for a gene recommendation system:

1. Analyzing downstream effects: Scientists can use Neo4j to understand the potential downstream effects of targeting a specific gene. By querying the number of neighbors connected to the gene, they can minimize or maximize the number of potential effects associated with that gene.

2. Pathway analysis: Biologists often have specific pathways or molecular processes in mind when searching for disease targets. Neo4j allows them to find genes that interact, up-regulate, or down-regulate genes participating in a particular pathway. This information can be used as a feature to prioritize genes in the recommendation system.

3. Commercial considerations: Apart from biological factors, commercial aspects can also influence target selection. For example, scientists may want to avoid targets that competitors are already pursuing, particularly if they are at an advanced clinical trial stage. Neo4j can help analyze the number of competitors with trials at a specific stage, allowing scientists to make informed decisions.

-Other features that can be considered in a recommendation system include gene similarity, where Neo4j can generate node embeddings to compare the similarity of genes. Additionally, non-graph-based features like drug ability, gene essentiality, disease association scores from external sources like Open Targets, and experimental data such as RNASeq differential expression can also be incorporated.

-Once all the relevant features for each gene are generated, they can be fed into an optimization model for prediction. Multi-objective optimization frameworks like Pymoo or Pyomo can be used to minimize or maximize the features/objectives. Machine learning or deep learning approaches can also be employed if sufficient training data is available.

-The output of these models will be a prioritized gene list with recommendation scores, allowing scientists to focus their efforts on a smaller subset of genes for experimental validation. Automation of this process is a goal, and companies like Crossr are working to productize recommendation systems for drug discovery using features from Neo4j and other sources.