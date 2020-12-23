# Enterprise Knowledge Graph Glossary of Terms

#### Accumulator
A type of variable that tracks items as you traverse through a graph.  Accumulators can be global or be attached to a specific vertex.

Accumulators allow MapReduce style queries where each server node in a cluster does work in its local data and returns consolidated results to the query node.  For example, in the query *"count all customers that have returned clothing items"*, each node would return only a single count to the query node.  This type of query reduces the amount of communication between nodes in the graph cluster.

#### Automaic Sharding
The process of automatically migrating data from one server to another server in a distributed database.  Auto-sharding is frequently done as a database cluster grows or shrinks based on new data being added or removed from the cluster.

Auto-sharding is one of the key features that differentiate scale-out enterprise-class databases from departmental solutions.  Testing sharding at scale under continuous load in the face of possible hardware failure is one of the key challenges facing enterprise data architects.

#### Bitermporal Modeling
A specific case of [Temporal Modeling](#temporal-modeling) modeling designed to handle historical data in two different timelines.  One timeline is concerned with when an event occurred in the real world and the other timeline is concerned when the data was recorded or corrected in a computer system. This makes it possible to rewind the information to "as it actually was" in combination with "as it was recorded" at some point in time. 

In order to implement this feature within an Enterprise Knowledge Graph, the data model must accommodate updates while preserving historical information. Information cannot be overwritten or discarded even if it is erroneous.  The consequence is more data must be retained even through only a small percentage of queries might require historical views of data.  Bitemporal models are more complex to query and require additional RAM and disk storage.
<br/>[Wikipedia Bitemporal Modeling](https://en.wikipedia.org/wiki/Bitemporal_Modeling)

#### Brain Anologies
Explaining enterprise knowledge graphs in terms of the human brain.  Human brains have roughly 82 billion neurons and a degree of 10,000.  Many enterprise knowledge graphs for the largest companies exceed 80 billion vertices but have only a handful of connections between them [Degree](#degree).

#### Business Event
A change in the state of a business entity within an operational source system that may be published to a downstream consumer such as an enterprise knowledge graph.

Business events are usually transmitted by [Change Data Capture](#change-data-capture) software and sent via document messages in formats such as JSON or XML.
[Wikipedia](https://en.wikipedia.org/wiki/Event-driven_architecture)

#### Business Vocabulary
A collection of terms and phrases that have meaning to a specific domain of work.  A business vocabulary typically starts out with a flat list of terms in a spreadsheet. The terms are listed with their abbreviations and definitions and how they are used within a specific project or department.

As vocabularies grow and mature the individual terms might be grouped together.  These groupings become taxonomies and can then be used to automatically classify documents with metadata tags of their preferred labels.  Classified documents
can have a dramatic increase on the search quality of a search engine.

#### Change Data Capture
Software that detects changes in a database and transmits the change information via [business events](#business-event) to a remote system.  These events are often published on stream processing systems using the publish/subscribe integration pattern.
<br/>Also known as: CDC
[Wikipedia page on Change Data Capture](https://en.wikipedia.org/wiki/Change_data_capture)

#### Concept
An idea, notion or a unit of thought.  Concept elements are the fundamental unit of work in semantics and are in integral part of enterprise knowledge graphs. 

In practice, each concept is usually associated with a vertex in a graph and has one preferred label in each language such as English.  Concepts may have many alternate labels.
Concepts are grouped in Schemas and may be part of one or more Collections.<br/>
[Concept Reference on W3C SKOS Site](https://www.w3.org/TR/skos-reference/#concepts)

#### Concept Graph
A graph that stores the core business concepts of a project, department or enterprise.  In the ideal world, an enterprise graph will use a combination of machine learning to connect related concepts together.

#### Cost Sharing
The ability of a single graph data model to be shared by many business units and thus the costs can also be shared.  Lower charge backs make graph databases more cost-effective than other data models.
<br/>See also: [No Complexity Penalty](#no-complexity-penalty)

#### Data Ingestion
A process by which data is moved from one or more sources to a destination where it can be stored and further analyzed. The data might be in different formats and come from various sources, including RDBMS, other types of databases, S3 buckets, CSVs, or from streams.

#### Decision Tree
A way of storing business rules in a graph.  A decision tree contains a series of branches, each branch containing a conditional expression.  If the conditional expression returns TRUE, then a true link is traversed.  If the conditional returns FALSE and false branch is traversed.

Decision trees and the corresponding rules that are represented as pointer hops in an enterprise knowledge graph have many integration and performance benefits.

#### Degree
The degree of a vertex is the count of the number of connections between the vertex and other vertices.  The average degree of a graph is the average number of connections for a vertex.

For non-directional graphs, counting is one per edge.  For directional graphs that have reverse edges, each connection counts as two connections.  In a directional graph, each vertex has both an in-degree and out-degree.

#### Departmental Graph
A graph designed to store information from one or more departments of an enterprise.  Departmental graphs may be limited in that they can't be scaled up to hold enterprise data.

#### Data Layer
Raw low-level binary codes that contains information after analysis.

#### Dashboard
A set of views, usually presented on a single page, that display information as a set of key performance indicators and charts.  In general, dashboard views can be customized for a role or a specific user.

#### Document Store
A type of database that stores data as tree-structured data elements such as JSON or XML.  Document stores use path-like query languages such as X-PATH to traverse the tree structure.  Languages such as XQuery provide high-quality functional programming languages with strong type checking.

X-PATH is a mature W3C standard for expressing path traversal using a rich array of standardized wildcard expressions.

#### DB Engines
A web site that harvests web documents that discuss databases and classifies the documents based on a taxonomy of database types.  The "Popularity changes per category report" is frequently cited in many graph presentations.
<br/>[DB Engines](https://db-engines.com/en/ranking_categories)

#### Embedding
A data structure, usually a vector of decimal numbers, associated with an item in a graph, that helps users quickly find similar items.  Vertices, Edges, and Paths may all have embeddings.

#### Enterprise Knowledge Graph
A scalable graph database system used to store large-scale connected information for an entire enterprise.

By scalable we mean that it must be able to run on multiple servers as the graph expands.  Without scalability the graph might be considered a project or departmental graph.

For many large organizations, enterprise knowledge graphs typically have hundreds of developers doing concurrent loading and query development and the models can be dynamic. For example the Google Knowledge Graph team is thought to contain over 1,500 developers.

#### Entity Resolution
The process of finding records in a data set that refer to the same entity across different data sources.

Entity Resolution is a core technique in converting Information layer data into a consistent knowledge graph.
<br/>[Wikipeia Record Linkage](https://en.wikipedia.org/wiki/Record_linkage)

#### Force Directed Graph
A graph layout algorithm that simulates forces on springs that move items 
[Wikipedia Force Directed Graph Drawing](https://en.wikipedia.org/wiki/Force-directed_graph_drawing)

#### Glossary
A business vocabulary associated with a topic.  A glossary often has both general definitions of terms as well as contextual definitions for a specific domain or project.<br/>
<br/>See also: [Business Vocabulary](#business-vocabulary)

#### GraphQL
A query language for APIs and a runtime for fulfilling those queries with your existing data.

Ironically, GraphGL has nothing to do with graph databases other than the fact that the queries often run much faster on graphs.  The name "graph" was used internally at FaceBook since they store their data in a graph structure.

One concern about GraphQL at the enterprise-scale is that your graph database should be able to detect GraphQL queries that are using too many resources.  This means your enterprise graph databases must understand concepts of [resource quotas](#resource-quotas).

#### Graph Query Language
A proposed standard graph query language being developed by the Working Group 3 (Database Languages) of ISO/IEC JTC 1's Subcommittee 32. 
GQL is designed to work with [Labeled Property Graphs](#labeled-property-graph).
<br/>[Wikipedia GQL Page](https://en.wikipedia.org/wiki/GQL_Graph_Query_Language)

#### Graph Structured Query Language
A distributed graph query language developed by TigerGraph.  GSQL was designed to be syntactically similar to the SQL language
but it also integrated distributed query concepts that share patterns similar to MapReduce queries.
<br/>Also known as: GSQL

#### Graph Database
A way of storing information in terms of vertices and edges.  Graph databases consider edge traversal as a primary performance consideration.  By storing edges as in-memory pointers graph databases offer roughly a 1,000x performance improvement over relational database management JOIN operations that must be calculated for each query.
See also: [Index Free Adjacency](#index-free-adjacency)

#### Graph Isomorphism
A graph can exist in different forms having the same number of vertices, edges, and also the same edge connectivity. Such graphs are called isomorphic graphs.

#### Index Free Adjacency
Accessing related entities in a system without having to consult a centralized index.  Using direct in-memory pointers to represent relationships is approximately three orders of magnitude faster than referencing a central index system.
<br/>See also: The Neighborhood Walk Story

#### Information Layer
Data about our key business entities.  This includes Things, like People, Places and Events.

#### Key-Value Store
A type of database that stores items as pairs of keys and values.  The keys are strings and the values are binary blobs such as files or images.  A simple put/get/delete interface is used to manage the database.

Key-value stores are excellent complements to graph databases since their simplicity allows for low-cost-per-byte storage. 

#### Knowledge Layer
A layer in the knowledge triangle that contains connected information.  The knowledge layer is often the top layer in our views.  There are some views that include a Wisdom layer on top of the knowledge layer.

#### Knowledge Triangle
A stack of three layers.  At the base is the [Data Layer](#data-layer), above that the [Information Layer](#information-layer) and at the top the [Knowledge Layer](#knowledge-layer).
![Knowledge Trainagle](img/knowledge-triangle.png)

#### Labeled Property Graph
A graph data model where each Vertex and Edge have a single type and goth Vertices and Edges have attributes.
Both TigerGraph and Neo4j use the LPG data model.
<br/>Also known as: LPG

#### Load-As-Is Pattern
A data loading pattern that loads the data into a graph with minimal transformation.  Once the data is loaded
into the graph the transformation is done in the native language of the graph such as GSQL.  This pattern
allows many projects to share the underlying data loaders and allows each team to customize the post-loading transformation
using the native query language of the graph.  The other major data model is the RDF model which is discouraged at Optum due
to the challenges with Reification. Reification causes RDF SPARQL queries to be rewritten.
<br/>[Load-as-is pattern](https://www.marklogic.com/blog/understanding-the-load-as-is-pattern/)
<br/>See also: [RDF](#resource-description-framework)

#### The Neighborhood Walk Story
A story used to illustrate the difference between direct pointer hopping and using centralized indexes to traverse relationships.  The story uses a 30-second walk between two houses vs. an 8.2-hour walk to a central location and back.

#### No Complexity Penalty
Unlike relational databases, graph databases quickly traverse many complex relationships.  As a result, graph databases are better at modeling the real world - which is full of complexity.  We use the phrase "No Complexity Penalty" every time we are training people who have come from the relational world that worry that too many relationships will slow down their queries due to slow JOINs.
<br/>See also: One version of the truth

#### One Version of the Truth
The real world has many complex relationships.  There are many ways to build simple models that take shortcuts to optimize queries by limiting relationships.  This is important in relational database modeling.  But the closer we get to modeling the real world, the closer to a single version of the truth we get.  Models that fairly represent the complexities of the real world can be reused among many business units and thus the costs of holding the information in memory can be shared.  This is why graph databases cost less then relational databases.

#### On-the-Wire vs. In-the-Can
A way of looking at knowledge representation requirements in two domains.  On-The-Wire implies that serialization of a dataset must retain connection information within itself and to other external systems.  In-The-Can knowledge representations are optimized for ease of query and [sustainability](#sustainability).  RDF is optimized for On-The-Wire exchange of knowledge.  LPG is optimized for In-The-Can tasks such as ease of query and sustainability.

#### Ontology
A graph of [Concepts](#concept) within a specific domain.  Ontologies often begin as flat term lists, that become taxonomies that then have more complex relationships than simple broader and narrower concepts.  Ontologies
are often stored in formats such as SKOS and OWL.

#### Open vs Closed World
https://en.wikipedia.org/wiki/Open-world_assumption
https://en.wikipedia.org/wiki/Closed-world_assumption

#### Operational Source System
A transactional computer that is the source of a data stream.  Enterprise Graph Databases often use [Change Data Capture](#change-data-capture) software on these systems to create an event stream of change records that so they can be stored in a central enterprise knowledge graph.  Change records are new, updated, or deleted business entities.

#### Preferred Label
A preferred lexical label associated with a [Concept](#concept).  In the [SKOS](#skos) standard, there should be
one and only one preferred label per language per concept.

#### Project Graph
A graph that supports a specific project.  Project graphs may contain knowledge that is not of interest to the rest of the enterprise.

#### Reference Data
Reference data is data used to classify or categorize other data.  They typically are stored as a set of valid codes for a specific data element.

For example the list of [Country Codes](https://en.wikipedia.org/wiki/Country_code) is a type of reference data.  Reference data is often stored as a short code and a definition of what that code represents.

#### Reification
Reification is the process by which an abstract idea about a computer program is turned into an explicit data model or other object created in a programming language.  Specifically, in the RDF modeling process it is the process of adding an abstract vertex to a graph when properties are needed in a relationship.  Reification causes queries that traverse that node to be rewritten.  This means that SPARQL queries are inherently much more difficult to maintain than LPG graph queries.

#### Resource Description Framework
An early family of standards developed by the World Wide Web Consortium for exchanging graph data championed by the [Semantic Web](https://en.wikipedia.org/wiki/Semantic_Web) community starting in 1999.  RDF gained some traction around 2010 but failed to gain widespread adoption due to the complexity of the standards and the problems of [Reification](#reification).
<br/>[Wikipedia](https://en.wikipedia.org/wiki/Resource_Description_Framework)

#### Resource Quota
The ability to limit the resources consumed by a query such as CPU time, or RAM for individuals or groups.

Large enterprise-scale graph databases must carefully monitor and constrain queries that consume too many resources.  Many older technologies such as Apache Drill are difficult to implement without the ability to monitor and restrict resources.

#### Role-based Access Control
The ability to assign access to a resource to individuals that have a specific role.  For Enterprise Knowledge Graphs, there are both high-level subgraph rules and fine-grain rules such as vertex-related role-based access control.

#### Rules Engine
A software component that executes rules according to some algorithm.

In the Enterprise Knowledge Graph space rules are frequently represented in [Decision Tree](#decison-tree) structures within the graph.
<br/>[Rules for Knowledge Graph Rules])https://dmccreary.medium.com/rules-for-knowledge-graphs-rules-f22587307a8f

#### Semantics
The branch of computer science associated with meaning.  It can be best understood by understanding the semantic triangle.  The key point of the semantic triangle is that we cannot directly associate a label with a referent without traversing concepts. 

![Semantic Triangle](img/semantic-triangle.png)

#### Shapes Constraint Language
A W3C standard RDF vocabulary for validating RDF graphs against a set of conditions.

Unlike document validation standards like XML Schema, SHACL assumes that data quality checks should be able to look for relationships in a graph as well as the local context of a document.  These conditions are provided as shapes and other constructs expressed in the form of an RDF graph.  LPG graphs do not yet have a version of SHACL.
<br/>Also known as: SHACL
<br/>[SHACL W3C](https://www.w3.org/TR/shacl/)

#### Simple Knowledge Organizational System
A model for expressing the basic structure and content of concept schemes such as thesauri, classification schemes, subject heading lists, taxonomies, folksonomies, and other similar types of controlled vocabularies. SKOS is also
the name of the world-wide-web standard for encoding these systems.  Serializations of SKOS are typically done in RDF format although other encodings such as XML and JSON are common.
<br/>See Also: [W3C SKOS Primer](https://www.w3.org/TR/skos-primer/)
<br/>See Also: [W2C SKOS Referecnce](https://www.w3.org/2009/08/skos-reference/skos.html)

#### Sustainability
The ability for a team of developers to maintain the code that supports an enterprise knowledge graph in the face of changes to the data model.  The key measure is to avoid problems related to rewriting graph queries when small changes are made to the graph data model.
<br/>See also: The Jenga Tower Story

#### Systems Thinking
A way of looking at problems in terms of components that interact with each other over time using direct connections, indirection connections and both positive and negative feedback cycles.  Systems Thinking forces us to think broadly about how our enterprise knowledge graphs interact with external systems.  Systems thinking also helps us see the unintended consequences of our actions.

#### Temporal Modeling
The process of modeling time in a data model.  Modeling time can be complex when the requirements of a system require you to be able to recreate detailed reports as they were at a prior point in time. Temporal modeling includes the concept of versioning and [bitemporal modeling](#bitermporal-modeling)

#### Triple Store
A purpose-built database for the storage and retrieval of RDF triples through semantic queries.  Triple stores are not used in most enterprise graphs due to their lack of [sustanability](#sustanability) due to problems with [Reification](#Reification).
https://en.wikipedia.org/wiki/Triplestore

#### Web Ontology Language
A Semantic Web language designed to represent rich and complex knowledge about things, groups of things, and relations between things.
<br/>[W3C OWL Web Site](https://www.w3.org/OWL/)