# The Knowledge Triangle

**Knowledge does not emerge from data.  - Judea Pearl**

## Information Layer

## Knowledge Layer

## Other Models

#### The DIKW Pyramid

Although we use the term “knowledge” broadly in normal conversation, it has a specific meaning in the AI and graph database community. Even within computer science, it has many different meanings based on the context of a discussion. This article gives a suggested definition of the term “knowledge” and uses the Knowledge Triangle metaphor to explain our definition. We will then show some variations of the Knowledge Triangle and see how the word knowledge is used in information management and learning management systems. I have found that having a clear image of the knowledge triangle in your mind is essential to understanding the processes around modern database architectures.

Here is our definition of Knowledge in the context of AI and graph databases:
Knowledge is connected-information that is query ready.

This definition is a much shorter than the Wikipedia Knowledge page which is:

**…a familiarity, awareness, or understanding of someone or something, such as facts, 
information, descriptions, or skills, which is acquired through experience or education by perceiving, discovering, or learning.**

The Wikipedia definition is longer, more general and applicable to many domains like philosophy, learning, and cognitive science. Our definition is shorter and only intended for the context of computing. Our definition is also dependant on how we define “information”, “connected”, and “query ready”. To understand these terms, let’s reference the Knowledge Triangle figure above.

## The Data Layer
In the knowledge triangle diagram, let’s start at the bottom Data Layer. The data layer contains unprocessed raw information in the forms of binary codes, numeric codes, dates, strings, and full-text descriptions that we find in documents. The data layer can also include images (just as a jpeg file), speech (in the form of a sound file), and video data. You can imagine raw data as a stream of ones and zeros. It is a raw dump of data from your hard drive. Some types of raw data, such as an image — can be directly understood by a person just by viewing it. Usually, raw data is not typically useful without additional processing. We call this processing of raw data enrichment.

## Enrichment

Enrichment takes raw data and extracts the things we care about and converts data into Information. This Information consists of items we call business entities: people, places, events, and concepts.

## The Information Layer
Information is the second layer of the Knowledge Triangle. Information is more useful than raw data, but Information itself consists of islands of disconnected items. When we start to link information together, it becomes part of the Knowledge layer.

## The Knowledge Layer

Knowledge is the top layer of the Knowledge Triangle. The knowledge layer puts information into context with the rest of the information in our system. It is this context that gives information structure. Structure gives us hints about how relevant information is for a given task.

## Structure Informs Relevancy

How does structure inform relevance? Let’s take a search example. Let’s say we have a book on the topic of NoSQL. The word “NoSQL” should appear in the title of that book. There also might be other books on related topics, but they only mention NoSQL in a footnote of the book. If the counts of the term NoSQL are the same in both books then the book on NoSQL might be buried far down in the search results. A search engine that uses structural search knows that titles are essential in findability. Structural search engines boost hits of a keyword within a title of a document by a factor of 10 or 100. Many search engines used for intranet search (notability the default Microsoft Sharepoint) ignore the structure of a document when doing document retrieval, so they have a reputation for their inability to find documents.

The structured search example above is an excellent example of where query readiness is enhanced in the knowledge layer. The fact that a keyword appears somewhere in a document reflects very little structure. The fact that a keyword appears in a title has much more value. The fact that the keyword appeared in a chapter title gives us some knowledge that that entire chapter is about that keyword.

## Enrichment and Machine Learning

Today most enrichment is done by using simple rule-based systems. The most basic rules are called data ingestion rules where data transformation maps are created and executed when new data is loaded into our system. A typical map rule says take data from the fourth column of the CSV file and assign this to the field PersonFamilyName. These rules are manually created and maintained. About 70% of the cost of building enterprise knowledge graphs are related to building and maintaining these mapping processes. These mapping steps are often the most tedious parts of building AI systems since they require attention to detail and validation. Source systems frequently change, and there the meaning of codes may drift over time. Continuous testing and data quality staff are essential for these processes to be robust. The phrase garbage-in, garbage-out (GIGO) applies.

What is revolutionary about the mapping process is we are just starting to see machine learning play a role in this process. These processes are often called automated schema mapping or algorithm assisted mapping. To be automated, these processes involve keeping a careful log of prior mappings as a training set. New maps can then be predicted with up to 95% accuracy for new data sources. These algorithms leverage lexical names, field definitions, data profiles, and semantic links for predicting matching. Automatic schema mapping is an active field of research for many organizations building knowledge graphs. Automated mapping will lower the cost of building enterprise knowledge graphs dramatically. Graph algorithms such as cosine similarity can be ideal for finding the right matches.

## Structure and Abstraction

We should also note that many things in the real world also reflect the Knowledge Triangle architecture of raw data at the bottom and connected concepts at the top. One of my favorite examples is the multi-level architecture of the neural networks in animal brains, as depicted below.

![](../img/.png)

Brains have multiple layers of neural networks. Data arrives at the bottom layers and travels upward with each layer representing more abstract concepts. The human neocortex has up to six layers of processing. This figure is derived from Jeff Hawkin’s book On Intelligence.
Just like the Knowledge Triangle, raw data arrives at the bottom layer and travels upwards. But unlike our three-layer model, brains have up to six layers of complex non-linear data transformations. At the top of the stack, concepts such as recognition of an object in a file, the detection of a specific object in an image or the detection a person’s face are turned to the “on” state. There are also feedback layers downward so that if the output of one layer has quality problems, new signals are sent back down to gain more insights at what objects are recognized.

Many people like to use brain metaphors when they explain knowledge graphs. Although some of these metaphors are useful, I urge you to use them cautiously. Brains typically have 10,000 connections per-vertex, and each connection does complex signal processing. So the architectures are very different in practice.

The last term we need to define is query readiness.

## Query Readiness
Of the many ways we can store data, which forms are the most useful for general analysis? Which forms need the minimum of processing before we can look for insights? What are the queries, searches, and algorithms we can use plug it to quickly find meaning in the data? The larger the number of these things you can use without modification, the more query ready your data is.
What the industry is finding is that the number of algorithms available to graph developers today is large and growing. The rise of distributed native labeled property graphs is making these algorithms available even for tens of billions of vertices. In summary, graphs are wining the algorithms race. The performance and scale-out abilities of modern graph database are pushing them to the forefront of innovation.

## Variations on the Knowledge Triangle

There are also many variations on the basic knowledge triangle metaphor that are useful in some situations. One of the most common is to add a Wisdom layer on top of the Knowledge layer. This four-layer triangle is known as the DIKW pyramid and is used frequently in information architecture discussions. I tend to downplay the role of wisdom in my early knowledge graph courses since the wisdom layer seems to be associated with touchy-feely topics or stories about visiting the guru on the mountain top for advice. That being said, there are some useful things to consider about the term wisdom.

For example, when you go to an experienced person for advice, you share with them your problem and the context of that problem. You expect them to use their knowledge to give you advice about your problem. You are expecting them to transfer a bit of their knowledge to you. We imagine the wisdom layer as a feedback layer to the structure of the knowledge layer. Wisdom can inform us how we can structure our knowledge in a way that it can be transferred from one context to another and still be valuable.

Stated in another way, can we take a small sub-graph out of an enterprise knowledge graph and port it to another graph and still be useful? For example, let’s suppose we have a sub-graph that stores information about geography. It might have postal codes, cities, counties, states, regions, countries, islands and continents in the graphs. Can we lift the geospatial subgraph out of one graph and drop into another graph? In neural networks and deep learning, taking a few layers of one neural network and dropping it into another network is called transfer learning. Transfer learning is frequently used in image and language models where training times are extensive. How you reconnect these networks into a new setting is a non-trivial problem.

These are the questions about the knowledge layer that you should be asking when you design your enterprise knowledge graph. If calling reuse issues the “Wisdom” layer helps you in your discussions, we encourage you to adopt this layer.

## Data Science and Knowledge Science
In some of my prior articles, I discussed the trends of moving from data science to knowledge science. We can also use the Knowledge Triangle metaphor to explain this process. This process is fundamentally about allowing staff direct access to a connected graph of your enterprise knowledge, thus saving them all the hassles of making meaning out of your raw data in the data lake.

![](../img/.png)

Data science staff can get faster time to insights using direct access to a knowledge graph.
To wrap up the post, I also want to suggest one other version of the knowledge triangle that has been mapped to an actual set of tools in a production knowledge graph. Instead of the abstract concept of raw data, we replace it with a diagram of a Data Lake or an object store such as Amazon S3. At the Information layer, we list the concepts we are looking for in the Data Lake, the definitions of these concepts, and the rules to validate each of these atomic data elements to make them valid. We also allow users to associate each business entity with a URI so they can be linked together in the next higher step. At the Knowledge Graph layer, we talk about making connections between the entities found in the information layer and the tools we use to connect data and find missing relationships automatically. These processes include entity resolution, master data management, deduplication and shape validation.
Image for post
From Data Lakes to transfer learning. The Knowledge Triangle in practice.
This diagram also mentions that there is often a feedback layer that automatically sends alerts to the data enrichers that there might be missing data and clues on how this data can be found.
Knowledge Spaces in Learning Management Systems
Lastly, we want to mention that modern AI-powered learning management systems (LMS) also use the term Knowledge Space. In the context of an LMS, knowledge space is a set of concepts that must be mastered to achieve proficiency in a field. Each student has a Knowledge State that shows where they are in learning a topic. AI-powered LMS systems use recommendation engines to recommend learning content associated with the edges of known concepts in each student's Knowledge Space. I will be discussing the topic of AI in education and Knowledge Spaces in a future blog post.
## Summary

In summary, The Knowledge Triangle is one of the most useful metaphors in our graph architecture toolkit. Along with The Neighborhood Walk, the Open World, and the Jenga Tower, it forms the basis for our introductory chapter on Knowledge Graph concepts.

I want to thank my friend Arun Batchu for introducing me to the Knowledge Triangle his willingness to transfer his wisdom to me.


# References

[The Knowledge Triangle Blog Post](https://dmccreary.medium.com/the-knowledge-triangle-c5124637d54c) Published Aug. 31st, 2019

https://en.wikipedia.org/wiki/Level_of_analysis#Computational

[Bloom's Taxonomy](https://en.wikipedia.org/wiki/Bloom%27s_taxonomy)

[AI futures - venture beat](https://venturebeat.com/2021/01/02/leading-computer-scientists-debate-the-next-steps-for-ai-in-2021/)