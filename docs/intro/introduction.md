# Chapter 1: What is an Enterprise Knowledge Graph

1. EKG are one type of NoSQL architectural patterns
1. Defining enterprise knowledge graphs
2. The Role of architectural scalability
3. Growth Rates of graph databases technology
4. Scale out graph database hardware
5. Scale out graph query languages

## NoSQL Architectural Patterns

Enterprise Knowledge Graphs (EKGs) are a type of [graph database](glossary.md#graph-database) that are designed to scale to meet the demanding requirements of large organizations.  Graph databases are just one type of NoSQL database architectural patten that we use to solve business problems.  The six types of NoSQL database architectural patterns are described in Figure 1.1.

![NoSQL Architectural Patterns](../img/nosql-architectural-patterns.png)

The six key architectures are:

1. **[Relational](../glossary.md#relational-database)** - where data is stored in rows of tables and new data is added one row at a time.  Relationships between tables are calculated at query time using JOIN statements that require central indexes to be used to traverse the relationships.  Also known as row-stores.
2. **[Analytical](../glossary.md#analytical-database** - where data is stored in centralized fact tables with simple relationships to dimensional tables.  Dimensions each represent a way you classify the facts in the fact table.  Analytical databases severely restrict the number of JOIN operations to optimise performance but force everyone to agree on the dimensions used to classify data.  Analytical databases tend to be the most difficult to use between departments since the [denormalization](glossary.md#denomalization) isprocess can be very specific to a single departments view of the enterprise.
3. **[Key-value Store](../glossary.md#key-value-store)
4. **[Column-family Store](../glossary.md#column-family-store)
5. **[Graph Database](../glossary.md#graph-database)
6. **[Document Store](../glossary.md#document-store)

## Defining Enterprise Knowledge Graphs

In this book, we define Enterprise Knowledge Graphs as the following:

**An Enterprise Knowledge Graph ia a scalable graph database that stores information from two or more departments of an organization.**

You will note that this definition is both somewhat general and very specific.  It is general because it includes many graph projects using a wide variety of technologies.  It is very specific in that it requires whatever graph database being used to have scalable technology under the hood.  Unfortunately, this eliminates most departmental graph projects in use today.

Why do we define EKGs with scalability as a prerequisite?  Because to truly meet the future needs of a large enterprise we must build our graph on an infrastructure that will not fall over and die as it grows beyond the initial pilot phase.  I have seen many well intentioned software architects claim to be building enterprise scalable graph databases only to have the projects fail due to performance problems as they grow beyond their early stages.

We also exclude knowledge graphs that are only attempting to solve problems for a specific department or specific business unit.  These can still be valuable projects for an enterprise since they can help individuals and departments learn the capabilities of graph databases.

Now let's take a closer look at what we mean by scalable.

## Scalable Knowledge Graphs
Scalability is an inherent characteristic of any database architecture.  It implies that as the size an complexity of the databases grows, the architecture must accommodate this growth without rewriting the core applications.  Although unexpected performance problems with specific queries might occur as the size of your database grows, they should be fixable by doing simple query optimization.

The key aspect of scalable graph databases is the ability to distribute a graph over a large number of independent but closely connected servers in a data center.  As demands grows, the number of servers in the cluster must easily scale without users or operations being impacted.

### Scalability Means the Four Vs
Volume, velocity, variability and veracity are considered the four Vs that define scalable systems.

**Volume** refers to the total amount of data in our knowledge graph.  For example enterprise-scale graphs may easily contain over 10 billion vertices and 50 billion edges. 

**Velocity** means that new inserts, updates and deletes might be coming in fast via streaming events and these events must be ACID compliant and still never slow down read access times.  Service levels agreements (SLAs) must focus not on total average times, but the averages of the slowest 5% of the transactions.

**Variability** means that data is not uniform and can be easily stuffed into a single fact table of an [OLAP](#online-analytical-processing-system) cube.

**Veracity** means we need to be able to validate the quality of incoming data in real-time and quickly raise warning flags if corrupt data is being transmitted into our EKG.

Note: We avoid using the term "[Big Data](../glossary.md#big-data" in this book.  It is an ambiguous statement of a problem and adds no insight into a solution.

### Scalability Means Automatic Sharding
The first criteria is that when the size of the enterprise graph grows to take on a new department or a new project, new hardware can be installed and the database is smart enough to use the new hardware without extensive pain and suffering by the database staff.  This is illustrated in Figure 1.2.

![Automatic Sharding](../img/autosharding.png)

### Scalability Means Scalable Access Control
Many graph products claim to have performance scale out capabilities, but their software falls down when we give them a a detailed list of what roles can access what data.  This means they might be able to scale their data to 100 nodes, but only a single role of "admin" can be defined for the graph.  They provide an all-or nothing approach to security.  This model works in small applications where access to the application is controlled by security access rules.  However it breaks down when I want 100 teams to only be able to run queries on their own team's data.  We will provide more examples of vertex-level role-based access control in [Chapter 3](#lifecycles.md)

### Scalability Means High Availability
Many graph products are perfect for a small team in a single city that work 9am to 5pm.  Upgrades can be done at night and on weekends.  But Enterprise class systems don't have users in a single city.  Employees and customers are all over the world.  That means when we upgrade our database with a new version of software we can't shut it down.  We need distributed servers that can take a single node down, upgrade the software and get it back into the cluster without ever dropping a single transaction.

### Scalability Means Ease of Creating Distributed Queries
If you are building enterprise-class knowledge graphs you may need to support 100+ concurrent developer all writing queries on a graph distributed over 100+ nodes in a cluster.  These queries need to efficiently distribute their work over each node and bring back just the data that is relevant to the results.  For example if you run a count of customers that have purchased a specific product, that query needs to distribute the query to each node and have each node return a simple count to the server where the query originated.  Those counts are summed together and returned to the user.  This type of query is sometimes called a map-reduce query since only the *counts* (reduced data) are returned to the origin server.  The actual customer data never never needs to move around.

### Scalability Means Resource Quotas
In a small project graph, you often have control and review processes of the code that each developer is working on.  In an enterprise setting you can't control everyone's code.  You need to assume that user will write run-away queries or just run queries that are not optimized for performance during the development and testing phases of query development.  You enterprise graph needs to be able to monitor rouge queries and shut them down when vertex counts, edges counts, CPU counts or memory resources reach reasonable limits.  Without these resource quotas a single query can take down an entire enterprise graph database.  So we need fine-grain controls in query resources, even when the queries may be running on 100 different nodes in a cluster.

### Scalability Means Scalable Metadata Management
For small project graphs, you many only have a few hundred vertices, edges and attributes.  For enterprise-scale graphs you may have thousands of these items and staff that are new to the enterprise knowledge graph need to be able to quickly search for the structures they are interested in.  Once they find the items of interest they need to understand their meaning and what the various code within value sets mean (reference data).  New users also many need to ask the data steward for each attribute questions such as where did the data come from, what assumptions were made about the data if if the dataset contains any sensitive information that might restrict who can view the data.

<!--
Non-published notes:

Note this definition does not address the word "enterprise":

https://help.poolparty.biz/pp/white-papers-release-notes/poolparty-technical-white-paper/an-enterprise-knowledge-graph-life-cycle-a-summary/the-enterprise-knowledge-graph-a-definition
->

