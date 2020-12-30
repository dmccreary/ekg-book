# Graph Data Modeling

<div style="text-align: right"><i>
All models are wrong, but some are useful.  - George Box
<i></div>

* What is graph data modeling?
* How is it different from traditional RDBMS data modeling?
* Keeping blobs out of the graph
* Accurately modeling complexity
* Single models of the world
* Modeling to minimize RAM
* Vertices, edges and attributes
* Example: A geospatial model

## What is a Graph Data Model?

## Single Models of the Truth

<div style="text-align: right"><i>
All happy families are alike, but every unhappy family is unhappy in its own way. (Leo Tolstoy, Anna Karenina, 1878)
<i></div>

I think about this quote when I am data modeling.  A happy data model is one that adequately captures the complexity of the real world.  If the world has lots of complex relationships, then our model may need to capture these relationships.

On the other hand, when we denomalization a logical data model to increase the performance of a query, we make our other family members very unhappy.

