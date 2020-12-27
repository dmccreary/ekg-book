# Strategic Serendipity

**Luck favors the prepared.  - Louis Pasteur**

When we thing of enterprise strategies, we often think of large groups of executives at multi-day off-site retreats.  They will be brainstorming, classifying ideas, looking for synergies, prioritizing, and then putting details into what they hope will be thoughtful planning for the next year and beyond.

Their goal is to prioritize concrete tasks that can be acted upon, assigned to teams, measured and then deliver results that can be measured with [key performance indicators](../glossary.md#key-performance-indicators).  Their job is to remove uncertainty and randomness from their plan.

But there is ample evidence that innovation and insight are not easy to predict.  Many stories about great discoveries such as the discovery of Penicillin by Alexander Fleming amount to random events that literally blew in through an open window.  Serendipity is the occurrence of random events that trigger positive outcomes.  Strategy and serendipity are oppositional thoughts.  Not everyone is good at holding oppositional ideas in their mind to come up with new innovations.  It takes practice.

We define [Strategic Serendipity](../glossary.md#strategic-serendipity) as the process of thoughtfully creating an environment that promotes insights, serendipity and tangible savings from newly connected information.  This means creating an environment around your EKG that encourages discovery.

## Discovery and the EKG
Discovery is different from creating regular [operational reports](../glossary.md#operational-reports) on your EKG.  Operational reports show things like counts of vertices of various types with special conditions.  The key is operational report on an EKG are run regularly and consistently and often feed the monitoring dashboards that are customized for each user.  But other than an occasional new trend line, they don't play a role in the EKG Discovery process.

In the context of the EKG, [data discovery](../glossary.md#data-discovery) (also called data mining) is a process of discovering new patterns in large data sets using a combination of query tools, machine learning and often visualization.

## A Story of Connected Data, Serendipity and Fraud Detection

Let me start out with a true story about what I mean by this idea of strategic serendipity environment.  When we first building graph databases we started to connect new data sources that had not been connected before.  One of our bright young engineers started seeing an unusual pattern of very small healthcare claims in dataset.  Being naturally curious, the engineer started to "connect some dots".  Because the team had not just loaded the flat claims items but also loaded and linked the providers that submitted the claims, the engineer could write simple queries to see that many of the small claims came from just a few providers.  Although the individual claims were small, when taken in aggregate, they amounted to over $10M in claims.

This pattern just did not make sense to the engineer.  So the engineer started to dig deeper.  The providers submitted these tiny claims were well outside the normal ranges of what other providers charged for similar procedures.  The engineer came up with charge distributions for other providers and then showed the average claims for "unusual" providers were much lower than normal.  Once they had the unusual providers identified they also saw that these claims were for procedures that their specialty codes didn't indicated they should be doing.

The engineer had found that some fraudsters had found a "loophole" in our audit rules.  Things below a specific threshold just went undetected by our audit rules, regardless of volume.  The fraud ring used stolen physician IDs to route claim reimbursements to their own personal bank accounts.

What is important about this story is that the engineer could never have found the patterns without connecting claims with physicians with their specialty classifications.  The values was not just in the flat claims files.  We needed to connect the data together using a graph database.

Remember that no one ever sat down with the team and said "go find fraudulent claims".  We know that fraud in healthcare claims cost US taxpayers what is estimated to be $50 billion dollars a year.  But fraudsters have grown every more sophisticated in their tactics.  And not all engineers are encouraged to follow their curious instincts.

So this is the job of a enterprise strategist.  We need to create environments that encourage insight and discovery.  Understand that it is impossible to predict exactly what the discoveries will be.  We can't predict when and where the discoveries will be.  But let's be very clear.  If we don't create an integrated set of connected data the insights may never be found.


