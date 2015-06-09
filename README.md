# Neo4J
Learnings on Neo4J and graph databases

### Why?

##### Why would you want to use this database?
Relational databases aren't actually good for storing relationship data
Relationship queries in relationship databases can be complex, slow and unpredictable, but since graph databases are designed for this sort of thing, the queries are more reliable
Relational databases are great for storing and retrieving data that fits nicely into a tabular format, but writing queries becomes increasingly difficult as more and more joins need to be prescribed, and the more joins the engine is required to perform, the worse performance
Joins and junction tables are not sophisticated enough to fully express the multitude and richness of relationships found in some data
No need to reserve space and then populate it with a "null" value, as the flexible schema easily accommodates diverse properties eg. no need for "date of last lightning strike: null"

##### What application areas is it suitable for?
Relationship-rich data, rather than data that can be neatly tabulated and self-contained
Interconnected, complex database systems similar to those used by social networks

##### Who else is using it? What are they using it for?
eBay: eCommerce delivery service routing
Walmart: relevant and personal recommendations
CrunchBase: used to build a “Business Graph”
Cisco: content management, master data management
National Geographic: real-time recommendations
Dating: eHarmony, Hinge, Meetic, Bang with Friends

### What?

##### What sort of database is it?
Neo4J is a GRAPH database -- graph databases don't organise information via columns, but rather through relationships
Graph databases reveal patterns and connections between bits of data
Set up as a collection of nodes connected by relationships
Labeled nodes (for informational entities) are connected via directed, typed relationships
Both nodes and relationships hold arbitrary properties (key-value pairs)
Data is recorded in nodes and relationships and can be labelled with zero or more labels to add further data relationships between nodes
Neo4J uses simplified graph theory, so relationships can only be uni-directional -- if you have 20 bi-directional relationships then that requires 40 "relationships"

##### What other databases is it similar to?
AllegroGraph, designed for LinkedIn
Apache Giraph, used by Facebook
Trinity, by Microsoft
GraphDB, InfiniteGraph, OrientDB, InfoGrid, HypergraphDB

### How?

##### How do you setup this database?
##### How do you use this database?
##### What Node.js modules are available for it?
##### Which one would you use, why, and how?

Create example code to demonstrate its use with a simple Node.js app.
