# Title : A unified drug–target interaction prediction framework based on knowledge graph and recommendation system


1. Drug-target interactions (DTI) prediction is crucial for drug development in areas like virtual screening, drug repurposing, and identifying potential side effects.

2. Traditional experimental methods for DTI detection are costly and time-consuming, leading to the development of computational approaches.

3. Computational methods for DTI prediction can be classified into structure-based, ligand-based, and hybrid approaches.

4. Hybrid methods, such as proteochemometrics (PCM) and network-based methods, have shown promise in overcoming limitations and handling complex systems.

5. Network-based methods integrate multiple data sources, including drug-target interactions, drug-drug interactions, and protein-protein interactions, to predict DTIs.

6. Machine learning techniques, including deep learning and graph embedding, have been applied in network-based methods for DTI prediction.

7. Knowledge graphs (KG) have been increasingly used in biomedical research, extracting fine-grained knowledge elements from omics data.

8. Recommendation systems, widely applied in various fields, can also be used for DTI prediction by modeling drugs as users and targets as items.

9. Existing methods in DTI prediction have shortcomings, including dependency on similarity measures and limited evaluation in real-world scenarios.

10. Curated relational data compilations, represented as knowledge graphs, enable the utilization of multi-omics resources in DTI prediction.

11. Two types of approaches for utilizing knowledge graphs are end-to-end methods and integration of pre-trained KG embeddings with prediction models.

12. Developing a unified framework that combines KG embeddings and recommendation system techniques is necessary for accurate and flexible DTI predictions.

13. The proposed framework, KGE_NFM, incorporates knowledge graph embeddings and neural factorization machine (NFM) for DTI prediction.

14. KGE_NFM captures latent information from heterogeneous networks without relying on similarity matrices and applies NFM for the specific downstream task of DTI prediction.

15. The results of evaluations in various scenarios demonstrate that KGE_NFM outperforms baseline methods in terms of accuracy and practical applicability.

16. The impact of different types of knowledge graphs on DTI prediction is explored, and effective strategies for more accurate inferences are investigated.

17. KGE_NFM is described as a powerful, robust, and extensible framework for DTI prediction, offering new insights into drug target discovery.

Overall, the article presents a unified framework, KGE_NFM, that combines knowledge graph embeddings and recommendation system techniques for accurate and practical drug-target interaction prediction. The framework addresses limitations of existing methods and demonstrates improved performance in different scenarios, providing valuable insights for drug discovery.

RESULTS
1. The study compares the proposed method with three types of DTI prediction methods: feature-based methods, end-to-end methods, and heterogeneous data-driven methods.

2. The evaluation is conducted on two benchmark datasets: Yamanishi_08's dataset and BioKG dataset.

3. In the warm start scenario, where the dataset is partially known, the performance of heterogeneous data-driven methods (DTiGEMS+, TriModel, and KGE_NFM) is high and robust, especially when the dataset is balanced.

4. Feature-based methods are influenced by imbalanced datasets, meaning that the performance can be affected when there is an unequal representation of drugs and proteins in the dataset. On the other hand, heterogeneous data-driven methods can partly overcome this limitation.

5. End-to-end methods perform better when the dataset size is larger, making them more suitable for large-scale DTI predictions.

6. In the cold start scenario for drugs, where the structural characterization of drugs plays a dominant role, KGE_NFM performs best in terms of AUROC (Area Under the Receiver Operating Characteristic curve), while RF (Random Forest) performs best in terms of AUPR (Area Under the Precision-Recall curve).

7. In the cold start scenario for proteins, KGE_NFM outperforms other methods, indicating its potential to capture the inherent associations in interactions between drugs and proteins.

8. End-to-end methods exhibit improved performance on the BioKG dataset compared to Yamanishi_08's dataset. This improvement can be attributed to the larger number of drugs and proteins available in the training set.

9. The application of Knowledge Graph Embedding (KGE) alone does not provide significant advantages compared to the feature-based method NFM (Neural Factorization Machine). However, when KGE is combined with NFM and traditional characterization of drugs and proteins (KGE_NFM), it enhances the predictive performance of DTI.

10. The integration of KGE and RF further improves DTI prediction performance compared to RF alone. This indicates that combining the strengths of KGE and RF can lead to better results.

11. Constructing the knowledge graph in a proper organization and utilizing betweenness centrality can enhance DTI predictive performance by enabling precise information extraction from heterogeneous data.

DISCUSSION

1. The study introduces a unified framework called KGE_NFM for predicting Drug-Target Interactions (DTI).
2. KGE_NFM integrates diverse information from different sources to enhance DTI prediction accuracy and robustness.
3. KGE_NFM combines Knowledge Graph Embedding (KGE) and Neural Factorization Machine (NFM) techniques.
4. KGE_NFM extracts heterogeneous information from multi-omics data using KGE and incorporates traditional drug and protein characterization using NFM.
5. The framework is validated on two benchmark datasets and compared with five state-of-the-art methods.
6. KGE_NFM outperforms existing methods, especially in the scenario of the cold start for proteins.
7. Unlike previous methods, KGE_NFM does not rely on similarity networks of drugs and proteins, simplifying the integration of multiple types of data.
8. KGE_NFM can utilize fine-grained heterogeneous information from omics data, such as KEGG pathways and protein binding domains.
9. The study highlights three techniques for further improving predictive performance and discusses their impact.
10. NFM, a content-based recommendation system, efficiently utilizes the low-dimensional characterization from KGE, leading to improved prediction performance.
11. KGE_NFM is scalable and can handle multi-modal data, including structural information of biomolecules and association information from biochemical networks.
12. The framework shows promise in facilitating protein target discovery for complex diseases and molecular mechanisms elucidation.
13. The study acknowledges the need for a systemic organization of biomedical knowledge for effective use of multi-omics data.
14. KGE_NFM is sensitive to parameter adjustments and requires careful treatment during the training procedure.
15. Future efforts will focus on improving the KG construction pipeline and expanding the application scope of KG-based recommendation systems in downstream tasks.


METHODS

The study used four benchmark datasets to evaluate their method for drug-target interaction (DTI) prediction: Luo's dataset, Hetionet, Yamanishi_08's dataset, and BioKG.

1. Luo's dataset: It consists of four types of nodes (drugs, proteins, diseases, and side-effects) and six types of edges (drug-target interaction, drug-drug interactions, protein-protein interactions, drug-disease associations, protein-disease associations, and drug-side-effect associations). The network contains 12,015 nodes and 1,895,445 edges.

2. Hetionet: This dataset integrates biomedical data from 29 publicly available resources and includes 47,031 nodes of 11 types and 2,250,197 relationships of 24 types. It includes small molecule compounds, genes, diseases, anatomies, pathways, biological processes, molecular functions, cellular components, perturbations, pharmacologic classes, drug side effects, and disease symptoms.

3. Yamanishi_08's dataset: It consists of four sub-datasets: enzymes (E), ion channels (IC), G-protein-coupled receptors (GPCR), and nuclear receptors (NR). The dataset was collected from various sources such as KEGG BRITE, BRENDA, SuperTarget, and DrugBank. The network contains 25,487 nodes and 95,579 edges.

4. BioKG: This biological knowledge graph integrates biomedical data from 14 databases and is designed for relational learning. It includes links (protein-protein interactions and drug-protein interactions), properties (annotations associated with entities), and metadata (data about biological entities). The KG contains 105,524 unique nodes and 2,043,846 edges.

The workflow of their method, KGE_NFM, consists of three main components:
1. Extraction of heterogeneous information using Knowledge Graph Embedding (KGE) models, specifically DistMult, to learn low-rank representations for entities and relations in the KG.
2. Automatic dimensional reduction using Principal Component Analysis (PCA) to reduce noise and dimensionality in the data.
3. Information integration and drug/protein collaborative recommendation using Neural Factorization Machine (NFM), which combines the linearity of Factorization Machines (FM) and the non-linearity of neural networks.

The study compared their method against several state-of-the-art methods for DTI prediction using 10-fold cross-validation. The evaluation protocols considered different experimental settings: warm start (common drugs and targets between training and test sets), cold start for drugs (unseen drugs in the test set), and cold start for proteins (unseen proteins in the test set).

They also included baselines from three categories: end-to-end methods, feature-based methods, and heterogeneous data-driven methods. The baselines used different input representations such as raw symbols (e.g., SMILES and FASTA sequences), molecular fingerprints, and descriptors.

Overall, the study aimed to demonstrate the effectiveness of their KGE_NFM method for DTI prediction and compare it against existing approaches using diverse benchmark datasets.