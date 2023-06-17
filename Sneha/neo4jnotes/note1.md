#Title: Neo4j Live: Crossr - Knowledge Graph based Drug Discovery

Introduction:
- The video explores the relationship between drug discovery and knowledge graphs, highlighting their importance in advancing pharmaceutical research.

Key Points:

1. Drug Discovery Process:
- Drug discovery is a complex and time-consuming process aimed at developing new medications to treat diseases.
- It involves various stages, including target identification, lead compound generation, pre clinical and clinical trials, and regulatory approval.

2. Challenges in Drug Discovery:
- Traditional drug discovery methods rely on trial and error, making the process inefficient and costly.
- There is a vast amount of biomedical literature, research data, and genetic information that researchers need to analyze and interpret.
- Integration of diverse datasets from multiple sources is challenging, as information is scattered and often not easily accessible.

3. Knowledge Graphs in Drug Discovery:
- Knowledge graphs are powerful tools for organizing and connecting vast amounts of data, enabling meaningful insights and discoveries.
- They are structured representations of knowledge, linking entities, concepts, and relationships in a graph format.
- In drug discovery, knowledge graphs can integrate and analyze diverse data sources, such as scientific literature, drug databases, clinical trials, and genetic information.

4. Benefits of Knowledge Graphs in Drug Discovery:
- Efficient Data Integration: Knowledge graphs allow the integration of disparate data sources, providing a holistic view of drug-related information.
- Relationship Mapping: By capturing relationships between entities, knowledge graphs reveal hidden connections and patterns, aiding in target identification and lead generation.
- Semantic Reasoning: Knowledge graphs enable semantic reasoning, allowing researchers to ask complex queries and obtain meaningful insights from interconnected data.

5. Applications of Knowledge Graphs in Drug Discovery:
- Target Identification: Knowledge graphs help identify potential drug targets by integrating genetic, proteomic, and disease-specific information.
- Drug Repurposing: By linking known drugs to new disease indications, knowledge graphs facilitate drug repurposing efforts.
- Adverse Event Prediction: Knowledge graphs can assist in predicting and understanding adverse drug events by analyzing clinical data and patient information.

6. Future Implications:
- The use of knowledge graphs in drug discovery is still in its early stages, but it holds tremendous potential.
- With advancements in artificial intelligence and machine learning, knowledge graphs can aid in accelerating the drug discovery process and personalized medicine.
the open source, it's called Hetionet. It was released in 2017
and it is way ahead of their time. So they released a knowledge graph

The Crossr demo continued with the exploration of a network of differentially expressed genes in the context of epilepsy. Differentially expressed genes are of interest because they could potentially be reversed to normal levels, thereby reversing the disease state. The focus was on identifying small clusters within this gene set that have been differentially expressed in epilepsy to potentially identify a target.

The Neo4j graph data science library was used, which provides analytical features such as Louvain clustering with community detection. By running clustering using the Crossr platform and Neo4j's GDS library, five clusters of genes, representing functional modules, were identified in the network. These modules consisted of genes that interacted with each other and were functionally related.

To determine which module to investigate further, enrichment analysis was performed to identify prevalent biological processes and pathways within the modules. The paper being followed, Craft, emphasized the importance of immune response processes in identifying relevant modules. By analyzing the enrichment results, the pink cluster (cluster two) was identified as being associated with immune response processes, particularly inflammatory response and regulation of immune response.

The module in cluster two was then selected for further investigation. It was found that some genes in this module were already known to be linked to epilepsy and seizures. The module was also found to be enriched for microglia, a cell type associated with inflammation. This module of genes became the focus of the analysis.

Using the Crossr platform, potential drug targets for epilepsy were identified by looking for upstream regulators that had an impact on the module as a whole. Master regulator analysis, a type of analysis offered by Crossr, was performed to identify genes upstream of the genes in the module. CSF1R, a gene that regulates multiple targets in the module, was identified as a potential therapeutic target. CSF1R was highlighted in the original paper as an interesting target for antiepileptic drug intervention because of its regulatory role and its status as a receptor, making it an accessible drug target.

The use of a knowledge graph, specifically Neo4j, proved beneficial in exploring the functional orientation of CSF1R and its connections. Pathways associated with CSF1R were examined, as well as drugs known to impact this gene. The paper utilized PLX3397 as a compound to inhibit CSF1R in a preclinical model of epilepsy.

It is important to note that further validation through human trials would be necessary before CSF1R can be considered a definitive target of interest for epilepsy treatment.

Overall, the demo showcased how the Crossr platform, combined with the Neo4j graph data science library, can facilitate the identification of potential therapeutic targets for complex diseases like epilepsy. The platform allows for the exploration of gene networks, clustering of differentially expressed genes, enrichment analysis of biological processes, and identification of upstream regulators for targeted intervention.

1. The FDA prefers to see at least dynamical models, ideally parts of ones that have previously been approved for new drugs. It's important to have a diverse range of data sources and knowledge graphs to support the drug development process.

2. Knowledge graphs are powerful tools that provide quick access to a large amount of data. They can be tailored to specific disease models, such as Alzheimer's disease or cardiovascular diseases, to gain insights and make informed decisions.

3. Building a knowledge graph requires careful curation and consideration of various databases and confidence thresholds. Scientists need to decide which data sources are valuable and set appropriate thresholds for analysis.

4. While not familiar with the specific tool "Druglike," open-source initiatives that enrich the available data in drug discovery are valuable and contribute to the field.

5. The future of knowledge graphs in drug discovery looks promising. Computational approaches and knowledge graph-based drug discovery are gaining traction in the pharmaceutical industry. Disease-specific knowledge graphs and more general multi-disease knowledge graphs have their respective benefits.

6. Disease-specific knowledge graphs can provide insights into specific disease pathways, vulnerabilities, and potential targets. On the other hand, multi-disease knowledge graphs are useful for drug repurposing and identifying commonalities between diseases.

7. Challenges arise in creating digital twins of disease states and understanding the complex interactions within the human body. Biological variability and the need for dynamical models or well-tuned statistics make it a complicated task.

8. Knowledge graphs can also be valuable in clinical trials, particularly in patient stratification to identify relevant patients based on demographic and other factors. Knowledge graphs can help improve patient care and even be integrated into tools like chatbots for healthcare recommendations.

9. Crossr, the platform mentioned in the conversation, can be reached via email, LinkedIn, or their website for further inquiries or demonstrations.

10. The use of knowledge graphs in drug discovery and clinical trials is gaining momentum, and the technical infrastructure is moving in that direction. There are ongoing efforts to leverage knowledge graphs to accelerate therapeutics and improve patient outcomes.

11. The conversation touches on the complexity of the human body and the challenges of mirroring biological variability. While the digital world operates in ones and zeros, biological systems are messy and require a holistic understanding.

12. The potential applications of knowledge graphs extend beyond drug discovery, including patient care and clinical trials. Patient stratification and leveraging knowledge graphs for improved patient outcomes are among the potential use cases.