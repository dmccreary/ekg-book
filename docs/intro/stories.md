# Enterprise Knowledge Graph Stories

# The Google Knowledge Graph
On May 16, 2012, Google published the "Things Not Strings" blog post.  Now the world knew that graphs were no longer an academic interest. Google's graph serviced millions of requests per minute and was available 24X7.  Knowlege Graphs became cool.
[Introducing the Knowledge Graph: things, not strings](https://www.blog.google/products/search/introducing-knowledge-graph-things-not/)

# Glossary to Taxonomy to Ontology to Graph
Tracy had a background in library science.  She was asked to help a manufacturing company organize their datasets.

## Stage 1: The Glossary
On Tracy's first day on the job, she heard dozens of terms she had never heard before.  Many of them were acronyms of internal systems and projects.  She started buy writing down the terms that she didn't understand in the first column of a spreadsheet.  She put the definitions of the term in the second column. She was building a business glossary.

## Stage 2: The Taxonomy
After a while, Tracy saw some recurring patterns in her terms.  Some were computer application names, some were product names and some were "other".  She started grouping the related terms together and added another column for the category of each term.  She had a concept taxonomy.

## Stage 3: The Ontology
After a while, Tracy's categories started to grow and become more complex.  Categories had sub-categories and now she started to see relationships between terms.  Terms had broader terms and narrower terms.  Some teams used different names (or labels) for the same concept.  Tracy now had a graph of concepts.  She had an ontology.  Tracy could no longer maintain the system using a simple spreadsheet.  She worked with her peers to create a web front end to a graph database so it was easy for anyone to add and update concepts.

## Stage 4: Reference Data
Her graph database continued to grow.  For many concepts she was asked to store a code-set that described the valid values that data element could contain.  She was building a reference data set.  Here reference data started simply - a list of country codes, a list of state codes and a list of regions that included states.  Then they asked her to list all the cities that they sold products.  Soon she was tracking all the cities in the world and their long-lat coordinates.  But this was OK, because the graph database that Tracy selected scaled well as the data complexity and size grew.

## State 5: The Project Knowledge Graph
The company like the fact that when Tracy was asked to add a new feature it was always done quickly.  The data model scaled well and Tracy was not forced to rewrite queries as the data grew.  As the request for more data continued Tracy added detailed product information and the customers that used these products.  She then got regular updates of customer lists and their customer satisfaction surveys.  Now multiple departments wanted access to Tracy's database.  She became an enterprise resource.

## State 6: The Enterprise Knowledge Graph
Now that Tracy had more and more customer data and their purchase history, Tracy had to use multiple servers to manage the data.  The company also needed to access customer records 24X7 so she put in tools to automatically replicate data and automatically migrated data to new servers as they were added to the cluster.  Tracy had built an truly highly available enterprise knowledge graph.

