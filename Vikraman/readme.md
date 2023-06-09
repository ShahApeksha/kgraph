'''
LOAD CSV WITH HEADERS FROM 'file:///sickle_cell_anaemia.csv' AS row
MERGE (x:Node {name: row.x_name, type: row.x_type, id: row.x_id,source:row.x_source})
MERGE (y:Node {name: row.y_name, type: row.y_type, id: row.y_id,source:row.y_source})
MERGE (x)-[:RELATION {type: row.display_relation}]->(y)
'''

#Precision Medicine Oriented Knowledge Graph

A resource that comprehensively describes the relationships of diseases to biomedical entities would enable systematic study of human disease. Understanding the connections between diseases, drugs, phenotypes, and other entities could open the doors for many types of research, Knowledge graphs developed for individual diseases have yielded results and insights to diseases but the costs and extended timelines of these individual efforts has created a need to create an umbrella for all this biomedical knowledge.

many primary data resources contain information about diseases, consolidating them into a comprehensive, disease-rich, and functional knowledge graph presents three challenges.

→First: ( Curation of data requires expert and manual labour)

. Existing approaches to network analysis of diseases require expert review and curation of data in the knowledge graph. 

. Such efforts require manual labor and expensive expert input, making them difficult to scale. 

→Second: (  Lacks a consistent representation of diseases )

. There lacks a consistent representation of diseases across biomedical datasets and clinical guidelines.  

. Database developers select the ontology that best suits their function from a multitude of biorepositories. 

. Each set disease vocabulary was tailored for some to serve a unique purpose. International Classification of Diseases (ICD) codes are optimized for medical billing. MedGen, PhenoDB, and Orphanet focus on rare and genetic diseases. Expertly curated disease descriptions in medical repositories do not follow any naming conventions. 

→ Third: (Diseases aren’t defined and classified properly)

. Defining diseases as clear and distinct entities for analysis is medically and scientifically uncertain.

. For instance, while autism spectrum disorder is considered a medical diagnosis, the condition has many subtypes. Clinically studied disease subtypes often do not correlate clearly with those defined in disease ontologies. Although only three subtypes of  autism have been clinically identified, the Unified Medical Language System (UMLS) describes 192 subtypes, the Monarch Disease Ontology (MONDO) describes 37 subtypes, and finally, Orphanet contains 6 disease entries for autism. 

. The challenge in reconciling disease entities is only exacerbated by the variety of synonyms and abbreviations available for any particular disease and the difficulty in linking structured disease entities to unstructured names in text. 

PrimeKG provides a comprehensive resource for studying how drugs interact with specific molecular changes in diseases, including information about their approved uses, conditions to avoid, and potential uses beyond the approved indications.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ff69e56b-d89d-4236-aae7-f15b7df8afaa/Untitled.png)

## Methods

We proceed with a detailed description of the 20 primary data resources used to build PrimeKG.

### overview of primary data resources

To create a comprehensive knowledge graph for studying diseases, we gathered information from 20 primary resources along with various biological and clinical repositories

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/83bfbf71-9e26-418b-8858-f0b4290584c6/Untitled.png)

(**a)** Shown are 20 primary data resources curated to develop PrimeKG. The colors highlight which data records are used to uniquely identify each node type. For example, GO is colored by biological 
processes, cellular components, and molecular functions because GO terms are the unique identifiers used to define nodes for these three node types. 

(**b)** Primary resources are colored by each node type for which they possess information. For example, GO provides links from biological processes, cellular components, and molecular functions to genes. As a result, we add the fourth color to represent the 
gene/protein class. 

(**c)** Illustrated is the process of harmonizing these primary data records to extract relationships between node types.

 (**d)** The left side illustrates PrimeKG, and the right side shows all the textual sources of clinical information on drugs and diseases. The node type legend is consistent across the figure. Abbreviations -

MF: molecular function, BP: biological process, CC: cellular component, PPI:
 protein-protein interactions, DO: disease ontology, MONDO: MONDO 
disease ontology, Entrez: Entrez gene, GO: gene ontology, UMLS: unified 
medical language system, HPO: human phenotype ontology, CTD: comparative
 toxicogenomics database, SIDER: side effect resource.

### Primary Data Resources

**BEEGEE:** 

collected filtered gene expressions.1,786,311 anatomy-protein associations where gene expression was found to: be present or absent

**Comparative toxicogenomics database**: 

180,976 associations of exposures with exposures, proteins, diseases, biological processes, molecular functions, and cellular components.

**Drug central:** 

drug-disease relationships were extracted.

**Entrez gene:** 

retrieved data about relations between genes and Gene Ontology terms

**Gene ontology:** 

Gene Ontology describes molecular functions, cellular components, and biological processes.

**Human phenotype ontology:** 

extracted 218,128 positive and negative associations between diseases and phenotypes. 

**Mayo clinic:**

 **I**nformation about symptoms, causes, risk factors, complications, and prevention of 2,227 diseases and conditions. Web-scraped the knowledgebase and extracted descriptions for these diseases and conditions using the *mayo.py* and *diseases.py* scripts.

**MONDO disease ontology:** 

The processed data contains 64,388 disease-disease edges.

**Orphanet:** 

curated information about definitions, prevalence, management and treatment, epidemiology, and clinical description for 9,348 rare diseases

**Four sources of physical protein-protein interactions:** 

.Protein-protein interactions (PPIs) are connections or relationships between proteins that have been confirmed through experiments. These interactions can serve various purposes, such as signaling, regulation, metabolic pathways, kinase-substrate relationships, and forming protein complexes. Combined data from various resources. After processing and organizing all this data, ended up with a network of 642,150 edges or connections between proteins. These edges represent experimentally-verified interactions between proteins and help us understand how they interact and work together in various biological processes.

**Reactome pathway database:**

Reactome is an open-source, curated database for pathways. Processing involved extracting ontology information such as hierarchical relationships and extracting pathway-protein interactions. The processed data contains 5,070 pathway-pathway and 85,292 protein-pathway edges.

**Side effect knowledgebases:**

The Side Effect Resource (SIDER)[96](https://www.nature.com/articles/s41597-023-01960-3#ref-CR96) contains data about adverse drug reactions. The processed data 202,736 contains drug-phenotype associations.

**Uberon multi-species anatomy ontology:**

Uberon is an ontology that contains information about the human anatomy. The processed data contains 28,064 hierarchical relationships between anatomy nodes.

**UMLS knowledgebase:**

The Unified Medical Language System (UMLS) Knowledge Source[46](https://www.nature.com/articles/s41597-023-01960-3#ref-CR46) contains information about biomedical and health-related concepts. retrieved the complete UMLS.

**additional vocabularies:**

We retrieved gene names and mappings between NCBI Entrez IDs and UniProt ID.

## **Standardizing and harmonizing data resources**

To create PrimeKG, - took different types of primary resources and made them work together seamlessly. We chose specific frameworks for each type of information, organized the data into a consistent format, and made sure that any overlapping or conflicting parts were sorted out. 

This way, PrimeKG can provide a unified and organized collection of resources that are easy to understand and use. 

In this study - use the terms "proteins" to refer to genes/proteins and "phenotypes" to refer to effects/phenotypes . 

It made sure that all the nodes (proteins and phenotypes) were clearly identified using unique identifiers from the specific ontologies and databases that we used. 

This mapping process helped to ensure that there was no confusion and each node was properly defined with its own unique identifier.

Identified sources of information across different primary resources for each node type to maximize the number of relationships in PrimeKG. 

the study modified the connections between different types of nodes (phenotypes, proteins, diseases, and drugs) to ensure that overlapping nodes were properly categorized as diseases and to remove any redundant or noisy connections involving overlapping phenotypes.

## **Building precision medicine knowledge graph (PrimeKG)**

To create PrimeKG’s graph, we merged the harmonized primary data resources into a graph and extracted its largest connected component

## Supplementing drug nodes with clinical information

Extracted both textual and numerical features for drug nodes in the knowledge graph from DrugBank and Drug Central.

## **Supplementing disease nodes with clinical information**

. gathered information about different diseases from various sources like the MONDO Disease Ontology, Orphanet, Mayo Clinic, and UMLS knowledgebase. They collected features such as disease definitions, descriptions, symptoms, prevalence, epidemiology, clinical descriptions, management, and treatment.

. used different techniques to match and map the disease information from these sources to create a comprehensive knowledge graph. For example, they mapped disease features to MONDO identifiers, removed references and URLs from descriptions, fixed formatting errors, and extracted specific information using regular expression.

. In simpler terms, the authors collected information about different diseases from various sources and organized them into a knowledge graph. Used different techniques to match and map the information to create a comprehensive view of each disease.
