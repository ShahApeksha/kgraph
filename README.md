# KNOWLEDGEGRAPH
 this is a file for scribbling the ideas, question and the code that we face and enconder at the time of building up the knowledge graph from the scap
## creating a kgraph for the biocurated rare diseases
# Understanding:
Building up a Kgraph require understandment of  diffrent domains: 
initially we came come to the better understanding of these basic terms
1. Taxonomy
2. Ontology
3. GraphDb
4. Kgraph
Taxonomy  describes the organisations vocabulary common term and synomyns.This then serves as the base of  the organisation to teach the Machine your language. in our case we are using the ontolgy of orphanet rare diseases for our pourpose.

Now lets deep dive into the term called ONTOLOGY as this term will be used  through out the making of knowledge grpah : ontology and knowledge graph go hand in hand!!
so the question is what is ontology !!? now we know what is a TAXONOMY : ontology is a SEMANTIC DATA MODEL, Map that describes the values various type of things we talk about in an organisation. Here in our domain the organisation refers to the diseases and their related properties , symptoms and so on . We can also say that it discribes the Ontology.It discribes what is known and what it wants to know and to connect the data for knowledge Mangement.

GraphDb is the triple storage.it mainly comprises collection of referenes to our knowledgeobject , Property of each object from various sources and the relation between them

Knowledge graph, also known as a semantic network, represents a network of real-world entities—i.e. objects, events, situations, or concepts—and illustrates the relationship between them. This information is usually stored in a graph database and visualized as a graph structure, prompting the term knowledge “graph.


### So how relavant is Ontology in Kgraph!? what is its role!? 
hmmm...!!

In a simple way  can say that the 
### knowledge graph = Ontology + GraphDB
