# About the Enterprise Knowledge Graphs Book

## Intended Audience
The book is intended for individuals and organizations that are considering or currently implementing Enterprise Knowledge Graphs (EKGs).  In this book, we define EKGs as scalable graph databases that span two or more business units.  The definitions of these terms will be defined in the first chapter of the book.

## Part 1: Introduction to EKGs
Part 1 of this book introduces you to the high-level concepts in EKGs.  We describe the *what* EKGs are, *why* companies build them and and *how* EKGs start and grow.

[Chapter P1.1: Introduction](intro/introduction.md) defines *what* an EKG is and how it is being used in large organizations.  We address the question of scalability and how many graph database systems claim to be scalable but fall down when they reach specific architectural limitations.  We also bring up the concept of role-based access control since we have found this feature key to widespread adoption of enterprise knowledge graphs.  We also introduce other key terms and give their definitions.

[Chapter P1.2: Cost and Benefits](intro/ekg-cost-benefits.md) describes *why* organizations are building EKGs.  We briefly cover the cost-benefits of building EKGs and describe the key use-cases of enterprise-knowledge graphs. and economic models that will help you determine if they might be a good fit for your organization.  We provide examples of how integration of data aids both customer experience an empowers data scientists to be more productive.

[Chapter 3: Lifecycles](intro/lifecycles.md) focuses on *how* EKGs are built in practice in the real world.  We describe how pilot projects are created but also designed to scale to meet enterprise needs.  We describe how EKG data models evolve an grow to absorbs new knowledge that provides deeper insights.  We also discuss the importance of subgraphs and both corse an fine-grain role-based access control.  Finally, we introduce the concept of "Edge of Chaos" and how it guides how EKGs grow.

## Part 2: EKG Concepts
Part 2 is an in depth analysis of the core concepts involved in building and running EKGs.

[Chapter P2.1: Introduction] introduces the concept of the knowledge triangle and the processes we used to turn raw data into entity-based information and then to connect this information into useful and queryable knowledge.

[Chapter 2.2: Modeling] covers enterprise-scale graph data modeling issues and the key issue of sharable data models between multiple business groups.  If data models can be shared they avoid duplication and lower analytical costs for the enterprise.

[Chapter P2.3: Ingestion] covers the concept of scalable transactions and data ingestion into an EKG.  We discuss the issues related to change-data-capture in source systems, schema matching and schema mapping, canonical data models, business events, streaming, publish-subscribe patterns and load and stress testing. 

[Chapter P2.4: Enrichment] introduces the concept if enrichment of data and connecting information.  This includes connecting incomming data to taxonomies and ontologies as well as reference data.

## Part 3: Case Studies
Part 3 is a deep dive into the most important case studies that help EKGs get launched.  Getting your first project off the ground successfully is critical for EKG success.

