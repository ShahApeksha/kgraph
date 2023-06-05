# KNOWLEDGEGRAPH
 this is a file for scribbling the ideas, question and the code that we face and enconder at the time of building up the knowledge graph from the scap
## creating a kgraph for the biocurated rare diseases
# Understanding:
Building up a Kgraph require understandment of  diffrent domains: 
initially we can have the better understanding of these basic terms
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
from this we habe to have a hands on experience with the ontology and find the releavance, so we installed the Protege standford which is made over the java platform. and build an basic ontology  to have a hands on experience with it.Protégé is a free, open source ontology editor and a knowledge management system. 

for that we created a simple ontology for 
vehicle-->has subclass--> car, bus, motorbike
car--> object property--> fuel type, wheelconfiguration, usetype
object property subclass-->  use, fuel, wheel configuration
use-> has subclass--> taxi, private, comapany
fuel-> petrol, diesel, hybrid
wheel configuration--> FWD, RWD, AWD
Car--> data property--> color(xds:string), seatcapacity(xds:integer), gear(xds: interger)

so our first question wasthe relavence of ontology and the role of ontology :
 we could infer from this that the ontlogy is the generalised datamodel for the knowledge graph which help in implementation of the kgraph more effiecently and prodectively without having any confusion between the entites  and relation. 
If we have a more wider ontology we can use it as a universal one and and add fields on it as per the property and annotation the field holds.
The most important property that an ontology hold is the concept of reuseability of

### "A knowledge Graph is made up of interlinked real-world entities described in a formal structure so they can be used both by computer and people"
### " knowledge Graph is when an Ontology is applies to a set of induvidual data points."
### "knowledge Graph acquires and intergrates information intoa ontology and applies a reasoner to drive new knowledge"

In a simple way  can say that the 
### knowledge graph = Ontology + GraphDB


Now Got the relavance ;
### Next important question arrised was how to intergrat the data into the graph DB!?
huh!! for this we can use 2 diffrent appoach that is the RDF(Resource Description Framework ) and the LPG(Label Property Graph):
so what is this rdf and lpg we have to clear it up before  taking the next step

RDF:The Resource Description Framework (RDF) is a general framework for representing interconnected data on the web.. An RDF statement consists of three components, referred to as a triple:
1.Subject is a resource being described by the triple.
2.Predicate describes the relationship between the subject and the object.
3.Object is a resource that is related to the subject.

LPG:Labeled property graph (LPG) is a type of graph database.
In LPG-style databases the graph is comprised of nodes and relationships. Each node or relationship has an ID tag, one or more “labels” describing its type or class, and a set of “properties” that present values and a corresponding key to allow referencing. 


![image](https://github.com/Jeri-jose/kgraph/assets/72429659/91792f73-0ba4-487a-8b55-c0fe19c96b4b)























