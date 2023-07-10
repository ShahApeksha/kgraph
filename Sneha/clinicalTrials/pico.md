# A PICO-based Knowledge Graph for Representing Clinical Evidence
1.	Background:
•	Clinical evidence is traditionally disseminated in unstructured, natural language scientific publications.
•	Clinical trial registries provide structured results data that are more timely and complete.
•	Efforts have been made to make clinical evidence computable and structured.
2.	Materials and Methods: 2.1 Data Source:
•	Data was collected from ClinicalTrials.gov, focusing on COVID-19 clinical trials.
•	ClinicalTrials.gov provides structured data in XML format.
Figure 1: Flowchart of the research- Illustrates the step-by-step flow of the research process.
2.2 Data Structure:
•	14 fields were extracted from 6279 clinical trial XML files, including information about study design, conditions, interventions, outcomes, funding, enrollment, gender, age, and study type.
•	Additional fields for start date and completion date were added to the 71 clinical trials with reported results.
Figure 2: The entities and relations represented in our knowledge graph-Visualizes the entities (nodes) and their relationships in the knowledge graph.
2.3 Data Terms Standardization:
•	Medical Text Indexer (MTI) was used to extract standardized medical subject heading terms for conditions.
•	MetaMap tool was used to standardize intervention/comparison terms by mapping them to Concept Unique Identifiers (CUI).
•	Outcomes descriptions were standardized manually.
2.4 Data Visualization:
•	The graph database Neo4j and its query language Cypher were used for data visualization and querying.
•	The clinical trial data was represented as a knowledge graph, showing nodes for clinical trials, conditions, interventions, comparisons, outcomes, funding, enrollment, gender, age, study type, start date, and completion date.
•	Relationships between nodes were established, such as "has_intervention" and "has_comparison" between clinical trials and interventions/comparisons.
3.	Results: 3.1 The Clinical Trials Results reported in registered platform vs. in bibliographic database:
•	A comparison was made between clinical trial results reported in registered platforms and those reported in bibliographic databases.
•	71 registered clinical trials were analyzed, and it was found that the completion time of clinical trials was on average earlier than the publication of bibliographic articles.
3.2 Knowledge Graph Information:
•	Two knowledge graphs were constructed: COVID-19 Trial Knowledge Graph (CTKG) and COVID-19 Trial Results Knowledge Graph (CTRKG).
•	CTKG contained 66856 nodes with 10 types and 1217673 relations with 9 types.
•	CTRKG contained 1067 nodes with 12 types and 1405 relations with 13 types.
•	The graphs allowed for queries, batch exports, and comprehensive clinical evidence based on the PICO framework.
Table 1: Node types and the number of unique entities in Knowledge Graph - Describes the types of nodes and the number of unique entities in each knowledge graph.
Table 2: Relationship types and the number of unique relations in Knowledge Graph-Provides information about the types of relationships and the number of unique relations in each knowledge graph.

3.3 Research Visualization:
•	A visualization of the knowledge graph related to COVID-19 clinical trials was generated.
•	The graph displayed basic information such as age groups, genders, study types, start dates, completion dates, conditions, interventions, and outcomes.
•	Clusters of related nodes were observed, providing an overview of the 71 clinical trials with reported results.
Figure 3: Knowledge graph related to COVID-19-Presents a visual representation of the knowledge graph, showcasing basic information about the 71 clinical trials with reported results.
3.4 Case Query: 3.4.1 Nodes information of Clinical trial knowledge graph:
•	An example of a single clinical trial query was demonstrated.
•	Cypher language was used to extract the study record and its associated information.
Figure 4: Node information of Clinical trial knowledge graph- Displays an example of the node information obtained from a specific clinical trial query.
3.4.2 Case query for outcome data:
•	A specific outcome ("c-reactive protein") was used as an example for querying.
•	Cypher language was used to retrieve all outcome nodes related to the standardized name "CRP".
Figure 5: Result of the query for specific outcomes-Shows the outcome nodes obtained from a query for a specific outcome ("CRP").
Figure 6: Information of outcome nodes example-Provides an example of the outcome node information obtained through a query.
3.4.3 Relationship Query:
•	Relationships between intervention/comparison and outcome were established based on the extracted P-values.
•	Cypher language was used to query significant relationships between interventions and outcomes.
Figure 7: Result of the query for relationship-Presents the result of a query for relationships between interventions/comparisons and outcomes, indicating significant or no difference.
4.	Discussion and Conclusion:
•	The study validated the concept of "computable evidence synthesis" by presenting structured and standardized clinical trial data in knowledge graphs.
•	The knowledge graphs provided a comprehensive representation of clinical evidence based on the PICO framework.
•	The methodology can be applied to other conditions and can incorporate data from multiple platforms.
