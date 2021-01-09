# Enterprise Knowledge Graph Timeline

**Putting graph representations of knowledge in historical context**

Here is a timeline of some of significant events that have led to the creation of the enterprise knowledge graph.  We focus on how the representation of knowledge impacted the way that problems were solved.

## First Forms of Knowledge Storage: Brain Evolution
Lets take a step back and see how brains evolved to store knowledge.  Centralized nervous systems may have first evolved around 521 million years ago.  They probably evolved from simple [Nerve Networks](https://en.wikipedia.org/wiki/Nerve_net) which consisted of specialized cells that worked together to process information.  All networks that process information can be modeled by graph databases.

What is interesting to note is that higher life forms never have evolved information processing systems that use tabular data storage.  This is an artificial construct that evolved from writing systems.

<br/>[Wikipedia page on Brain Evolution](https://en.wikipedia.org/wiki/Evolution_of_the_brain)

## Cuniform Tablets
Around 3,000 BCE in the fertile crescent, a group of farmers started to record transactions as rows in clay tablets.  Despite its limitations in storing relationships, for the next 5,000 years, tabular representations of data became the dominant way to store and transmit knowledge.

![Cuniform Tablet](../img/cuniform-writing.png)

This was the first known case of persistent data representation.  Although the transactions were initially simple, they started in motion a long change of representing data in tabular structures.  A process that still exists today.

## Hero of Alexandria
Hero is known to have created the first devices that store information on mechanical devices that control the playback of effects such as sounds.  This was one of the first forms of machine readable knowledge.
![](../img/hero-of-alexandria.png)

[Hero of Alexandria](https://en.wikipedia.org/wiki/Hero_of_Alexandria)

## Book of Ingenious Devices
A large illustrated work on mechanical devices, including automata, published in 850 by the three brothers of Persian descent, known as the Banu Musa.  This book was a collection of best practices for storing and playing back information.

![Book of Ingenious Devices](../img/banu-musa-mechanical.jpg)

* [Book of Ingenious Devices](https://en.wikipedia.org/wiki/Book_of_Ingenious_Devices)

## Looms
Basile Bouchon developed the punch card as a control for looms in 1725.

## Leonhard Euler Invents Graph Theory
In 1736 Euler invented graph theory while pondering the problem of walking around the city of Konisberg.  By reducing the topology of the city, the rivers and islands to a graph he showed that you could not walk through the city and cross each of those bridges once and only once.

![]
[Seven Bridge of Konisberg](https://en.wikipedia.org/wiki/Seven_Bridges_of_K%C3%B6nigsberg)

## Punched Cards
In 1890 Herman Hollerith developed punched cards for use in commercial data processing. These cards became the backbone of machine readable information storage until core memory was invented.

It is interesting to note that both programs and data were stored on punch cards.  Early batch programmers would submit both data decks and program decks together and return the following day to see the results of their programs often printed in additional card decks.

At the time, storing data on rectangular cards was an extremely practical decision.  It made it easy to build hardware to store and read information.  An unfortunate consequence was that for the next 125 years many people were taught that data within a computer's memory must also have this format.

[Wikipedia on Punched Cards](https://en.wikipedia.org/wiki/Punched_card)

## Flat File Databases
The earliest databases were usually modeled using the same data structure as punch cards: data loaded one row at a time.  The layout of fields within the cards might be fixed with or variable width depending on the type of data being stored.

The predominant language for information processing was COBOL for business and FORTRAN for scientific computing.  Both these languages used functions that read and wrote flat file data.

[Wikipedia Flat File Database History](https://en.wikipedia.org/wiki/Flat-file_database#History)

## Relations Added to Flat Files
In 1970 the concept of adding relationships to flat files was codified into a new type of database appropriately called "Relational" databases.  Although the name "relational" was used, fast relationship traversal were not a primary concern.  The system required all rows of both tables to be fist analyzed before the relationships could be discovered when a query was executed.

https://en.wikipedia.org/wiki/Relational_database#History

## Resource Description Format (RDF)
The need to store relationships between information was addressed by Ramanathan V. Guha and Tim Bray starting around 1995.  A first public draft of RDF appeared in October 1997 as part of standards promoted by the World Wid Web consortium.

The RDF data model was a brilliant development but was widely misunderstood due to poor understanding of its potential.  Many thought it was only for storing metadata or for storing data within a database.  In reality it's strength was a robust standard method for serializing complex knowledge in a portable format.

![](https://en.wikipedia.org/wiki/Resource_Description_Framework#History)

## The Semantic Web
In May of 2001 Scientific American published an article on the Semantic Web.  This article launched and entire industry of companies that wanted to use connected data to power AI systems.  The standards did allow anyone on the web to publish knowledge that could be easily linked into an knowledge graph.  But the stack of tools built on top of RDF had many issues with sustainability and have never gained widespread commercial adoption in most large corporations.

![](../img/semantic-web-cover.png)

## Neo4j: The First Labeled Property Graph
In May of 2007 Neo4j created the first labeled property graph.  Unlike the RDF model that did not allow relationships to have properties, the LPG model allowed every relationship to have any number of properties.  This meant that adding a property to a relationship did not require you to refactor the graph structure (Reification) causing all queries to be rewritten.  We finally had a sustainable data model that allowed the models to gracefully grow as complexity grew.

Neo4j also kept their in-memory model simple which allowed simple pointer hopping operations to be used to traverse the graph.  This is a key to performance and will enable future hardware optimizations.

[Neo4j First GitHub Commit May 2007](https://github.com/neo4j/neo4j/commit/6a945ab06a928bbd0f93dc56af279ee35107d7c3)

## The Google Knowledge Graph
On May 16, 2012, Google published the "Things Not Strings" blog post.  Now the world knew that graphs were no longer an academic interest. Google's graph serviced millions of requests per minute and was available 24X7.  Knowlege Graphs became cool.
[Introducing the Knowledge Graph: things, not strings](https://www.blog.google/products/search/introducing-knowledge-graph-things-not/)

## TigerGraph Releases the First Distributed LPG
Although the Neo4j system was innovative for it's time, it was built around a memory model that did not include queries that spanned multiple servers.  In 2017 TigerGraph release a version of a native labeled property graph that was designed from scratch to take into account distributed queries.  This allowed it to have robust scale-out performance to large clusters to meet the needs of large enterprise-scale applications.