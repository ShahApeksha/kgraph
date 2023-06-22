# Utilizing graph machine learning within drug discovery and development
# 1. How are they collecting data
- The document mentions various sources of data used in drug discovery and development, including electronic lab notebooks, electronic regulatory submissions, laboratory and clinical trial data collection, social media observations online databases, scientific literature, and more.
- Additionally, the document discusses the use of computational methodologies to expedite various parts of the drug discovery and development pipeline.
- Therefore, the source of data in this project is diverse and includes various types of data from different sources.
# 2. How are they making graph data from the raw data?
- One technique used to transform graph data from raw data is graph machine learning (GML), which is a new class of machine learning methods that exploits the structure of graphs and other irregular datasets.
- GML is used to model biomolecular structures, functional relationships between them, and integrate multi-omic datasets.
# 3. What techniques are they using to build knowledge graph?
- There are several techniques used to build knowledge graphs, including graph machine learning (GML), graph neural networks (GNNs), and graph embedding-based approaches.
- These techniques involve exploiting the structure of graphs and other irregular datasets to learn effective feature representations of nodes, edges, or entire graphs.
- Additionally, the document suggests that active learning may be deployed to
label critical missing data points and reduce model uncertainty.
# 4. From the knowledge graph how are they proceeding to achieve their end goal
- The document mentions that due to the problem of missing data within biomedical knowledge graphs, there are opportunities for active learning to be deployed to label critical missing data points to explore experimentally and therefore reduce model uncertainty.
- Additionally, in the rare disease arena, a knowledge graph embedding approach is introduced to identify repurposing hypotheses for rare diseases. The problem is cast as a link prediction problem in a knowledge graph.
- The authors use the Global Network of Biological Relationships, a knowledge graph built through literature mining and that contains diverse relationships between diseases, drugs, and genes.
- Due to the uncertainty associated with associations obtained from literature mining, the authors use a knowledge graph embedding approach designed to account for uncertainty.
# 5. What is their graph algorithm strategy
- The document describes several graph algorithm strategies, including traditional approaches such as centrality measures and clustering:
    - Centrality measures like closeness centrality quantify how closely a node isconnected to all other nodes
    - While clustering can be used to derive topological descriptors of the wiring patterns around each node in a graph.
- as well as more recent approaches such as random-walk based methods and graph neural networks.
    - Random-walk based methods and graph neural networks are both approaches used in graph analysis and machine        learning. Random-walk based methods, such as Deepwalk and node2vec, aim to embed a graph's nodes in a low-dimensional space while preserving node proximities.
    - On the other hand, graph neural networks use neural networks to learn representations of nodes and edges in a graph, allowing for tasks such as node classification and link prediction. Both approaches have been successful in various applications and have their own strengths and weaknesses.
- Additionally, the document discusses graph diffusion and graph isomorphism as related notions in graph analysis.
    - Graph diffusion is a notion that models the propagation of a signal on a graph,
    - while graph isomorphism is the problem of determining whether two graphs are structurally identical. The Weisfeiler-Lehman (WL) graph isomorphism test is a classical polynomial-time algorithm in graph theory that is based on iterative graph recoloring.
Overall, the document covers a range of graph algorithm strategies and their applications in machine learning and drug discovery.
# 6. Graph machine learning
- The document discusses graph machine learning (GML), which is a class of machine learning methods that exploit the structure of graphs and other irregular datasets.
- Within GML, there are graph neural networks (GNNs), which are deep neural network architectures specifically designed for graph-structured data. GNNs iteratively update the features of the nodes of a graph by propagating information from their neighbors.
- These methods have already been successfully applied to a variety of tasks and domains such as recommendation in social media and E-commerce, traffic estimations in Google Maps, misinformation detection in social media, and various domains of natural sciences including modeling fluids, rigid solids, and deformable materials interacting with one another and event classification in particle physics.
- In the biomedical domain, GML has now set the state of the art for mining graph-structured data including drug-target-indication interaction and relationship prediction through knowledge graph embedding, molecular property prediction, including the prediction of absorption, distribution, metabolism and excretion (ADME) profiles.