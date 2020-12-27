# Chapter 1: What is an Enterprise Knowledge Graph

1. NoSQL architectural patterns
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

### Scalability Means Automatic Sharding
The first criteria is that when the size of the enterprise graph grows to take on a new department or a new project, new hardware can be installed and the database is smart enough to use the new hardware without extensive pain and suffering by the database staff.  This is illustrated in Figure 1.2

<!--
Non-published notes:

Note this definition does not address the word "enterprise":

https://help.poolparty.biz/pp/white-papers-release-notes/poolparty-technical-white-paper/an-enterprise-knowledge-graph-life-cycle-a-summary/the-enterprise-knowledge-graph-a-definition
->

