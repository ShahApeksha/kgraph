# Drug knowledge bases and their applications in biomedical informatics research
1. How are they collecting data?
 Drug-related information is collected from different sources such as scientific
literature, social media platforms, and medical forums.
 The information is then gone through one or more manual review processes
before being curated into knowledge bases.
 While automated methods are being used to assist the curation, they are of a
basic level.
 Therefore, the process of constructing drug knowledge bases is time-consuming
and involves a significant amount of human effort.
2. How are they making graph data from the raw data?
 There is an alternative approach of implementing drug knowledge bases is graph
databases, which use graph structures to manage data.
 This makes it an ideal solution for managing biomedical entities, their properties,
and their relations.
 The graph databases are reported to scale better and load data faster than RDF
stores, which are physical implementations of ontologies.
 Therefore, it seems that the graph data is created by using graph databases to
manage the raw data.
3. What techniques are they using to build knowledge graph
 The article mentions that drug ontologies use W3C's Semantic Web technologies
such as RDF and OWL to manage knowledge.
 They also mention that an alternative approach to implementing drug
knowledge bases is graph databases, which use graph structures to manage data
and are an ideal solution for managing biomedical entities, their properties, and
their relations.
4. From the knowledge graph how are they proceeding to achieve their end goal?
 The importance of integrating drug knowledge bases and implementing a
scalable drug knowledge graph to enable more comprehensive views with richer
information is mentioned.
 They suggest that an open-source community effort has been established to
develop an integrated knowledge base of drugs and health outcomes of interest.
 They also mention the challenges associated with the drug knowledge base life
cycle, such as semiautomation of the knowledge extraction process and
integration of drug knowledge bases.
 It states that graph databases use graph structures to manage data, making
them an ideal solution for managing drug knowledge bases as well as a drug
knowledge graph.
Semi Automation of the knowledge extraction process.
 Semi automated methods can assist human curators in a more upgraded
manner. For example, given a drug side effect, a semiautomated method can
retrieve two sets of literature that have contradictory assertions, so that human
curators save the time of manually identifying different assertions across the
retrieved literature and make more informed decisions.
 Integration of drug knowledge bases involves combining information collected
from different drug knowledge bases to solve problems.
 While these integrations were performed at a limited scale, there are a few
challenges when performing integration at a larger scale.
 The first challenge is entity matching (or mapping) between two or more
knowledge bases.
 Another challenge is integrating relations of entities. It is not a problem if
there is only one type of relation between two entities.
 However, if more than one types of relation exist between two entities, we first
need to identify all possible relations between the two entities and review how
these relations are represented in different drug knowledge bases.