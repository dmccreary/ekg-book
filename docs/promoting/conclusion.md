# Conclusion

**Never mistake a clear view for a short distance.” — Paul Saffo**

We now come to an end of our journey through our tour of our knowledge about enterprise knowledge graphs.  We have touched on a wide number of topics and integrated concepts that I suspect you will not find in any single course in a typical universities course catalog.  Which is too bad.  Curriculum design is often driven by historical artifacts, not what is most useful to students.  Artificial barriers between college and university departments promotes specialized [hedgehog thinking](../glossary.md#hedgehog-and-fox), not systems thinking.

I hope that you will agree, that to successfully implement sustainable enterprise knowledge graph you need to be a generalist and draw knowledge from many disciplines.  I hope this book will help you in your journey.

I would like to conclude with a few thought experiments about what enterprise knowledge graphs can become in the near term future.  Being aware of the Paul Saffo quote above, I am going to hold off on giving you a predicted timeline of when these events will occur.  Prediction is hard, and there are many uncertain events that will radically change the the course of enterprise knowledge graphs.

## Specialized Enterprise Graph Hardware
We know that as graph databases increase in popularity, that they will gain the attention of people that are trying to optimize hardware to match the unique workload of enterprise knowledge graphs.  Companies like [Graphcore](../glossary.md#graphcore) and Intel with their [PIUMA](../glossary.md#intel-piuma) project have already begun this process.

The challenge is that not all graph databases will leverage this new hardware.  Doing so requires graph databases to take advantage of specialized hardware to create fast graph traversal.  It will take time for both software and hardware to align their systems to work together.

## Natural Language Query
Software like [GPT-3](../glossary.md#generative-pretrained-transformer) has already shown it can take English language description of queries and convert them to SQL.  Look for similar tools that will allow non-technical staff to literally ask complex questions about the content of a knowledge graph.

## Embeddings Everywhere
Graph embedding is just in it's infancy.  Right now it takes a huge amount of effort from dedicated data scientists that also understand graph data models to build embeddings.  In the future, graph databases will automatically build embedding for you by default.  Embedding will be associated with vertices, edges and paths and intelligent query generators will know how to use them in queries.  We will finally get to the state where our data science and our query developers will work together in a seamless way.

## Subgraphs and Micro Reasoners
Enterprise knowledge graphs may have standardized subgraphs that can be quickly loaded with a few clicks of an administration tool.  Need all the geolocations in the US including every geocoded address, city, state, county and zip code?  We have a subgraph for you and all the inference queries over that subgraph.

