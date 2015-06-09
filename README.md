# Neo4J: What, Why, How?

### What?

#### What sort of database is Neo4J?

Neo4J is a *graph* database. Graph databases don't organise information via columns and tables, but rather through *relationships* that reveal patterns and connections between bits of data.

Graph databases are set up as a collection of labeled nodes, connected by relationships. Both nodes and relationships record data and hold arbitrary properties (key-value pairs). They can be labelled with zero or more labels to add further data relationships between nodes.

#### What other databases is it similar to?

Neo4J was the first and most well-known graph database, but other, similar databases exist. These include:

* AllegroGraph, designed for LinkedIn
* Apache Giraph, used by Facebook
* Trinity, created by Microsoft
* GraphDB, InfiniteGraph, OrientDB, InfoGrid, HypergraphDB...

### Why?

#### Why would you want to use this database?

##### To analyse relationship data

Ironically, relational databases are not actually good for storing relationship data. Relationship queries in relational databases can be complex, slow and unpredictable. Writing queries becomes increasingly difficult as more and more joins need to be prescribed. The more joins the engine is required to perform, the worse the performance becomes.

Since graph databases are designed *specifically* for analysing relationships, queries are more reliable. The database returns information efficiently and intuitively.

##### To express diverse data properties

The joins and junction tables in relational databases are not sophisticated enough to fully express the multitude and richness of relationships found in some data. The flexible scheme of a graph database easily accommodates diverse properties.

Imagine a database of 10,000 people in which one user (Jim) has been struck by lightning. In a relational database the property "has been struck by lightning" would have to be assigned to 9,999 users and set to null (as well as to Jim). In a graph database, there's no need for an unnecessary property to be assigned to every node.

##### If your database is super-complicated

Relational databases are great for storing and retrieving data that fits nicely into a tabular format. But for interconnected, complex database systems, a graph database is a better choice.

#### What application areas is it suitable for?

Neo4J is suitable for relationship-rich data, rather than data that can be neatly tabulated and contained. Some application areas include:

* Social networks, which can use a graph database to easily show relationship data for their users
* eCommerce sites, using a graph database to deliver personal recommendations

#### Who else is using it? What are they using it for?

Neo4J is the most popular graph database, and is used by a number of notable companies. These include:

* eBay: eCommerce delivery service routing
* Walmart: relevant and personal recommendations
* CrunchBase: used to build a “Business Graph”
* Cisco: content management, master data management
* National Geographic: real-time recommendations
* Dating tech companies including eHarmony, Hinge, Meetic, Bang with Friends

### How?

#### How do you setup this database?
#### How do you use this database?
#### What Node.js modules are available for it?
#### Which one would you use, why, and how?

Create example code to demonstrate its use with a simple Node.js app.

#### What issues might there be with using Neo4J?

Neo4J uses simplified graph theory, so relationships can only be uni-directional -- eg. if you have 20 bi-directional relationships then that requires 40 "relationships"



##How to install
###Download Neo4J
Download it from the website
[http://neo4j.com/download/]


###Download Java inorder to run it.
Download Oracle Java 8 or OpenJDK.
For Ubuntu users you can find instructions here to download & install the Oracle Java 8 [http://askubuntu.com/questions/521145/how-to-install-oracle-java-on-ubuntu-14-04]

After installing Java extract the Neo4J files and run it from your terminal:
From the containing folder

`$ ./bin/neo4j start`

## Neo4J With node

Neo4J has a inbuilt HTTP REST interface which can be used with the Neo4J database. You can use it with the Node request module.

Follow instructions from this lovely blog:
[http://blog.modulus.io/learn-how-to-use-neo4j-with-node.js?utm_content=12954986&utm_medium=social&utm_source=twitter]

Here's the final code to access the Noe4J database:

You can access it in two ways 1) built in REST API using the request module in Node & 2) Use node-neo4j module.

The following code shows you how to connect to the databade with the REST API:

``` javascript
var request = require('request');
var host = 'http://localhost:7474/user/neo4j/neo4j',
port = 7474;

//url path for the database
var httpUrlForTransaction = 'http://' + host + '/db/data/transaction/commit';
console.log(httpUrlForTransaction);
function runCypherQuery(query, params, callback) {
  request.post({
      uri: httpUrlForTransaction,
      json: {statements: [{statement: query, parameters: params}]}
    },
    function (err, res, body) {
      callback(err, body);
    })
}

runCypherQuery('CREATE (somebody:Person { name: {name}, from: {company}, age: {age} }) RETURN somebody',
    {
    name: 'Ghuffran',
    company: 'Modulus',
    age: 44
    }, function(err, resp){

        if (err){
            console.log(err);
        } else {

            console.log(resp);
        }
    }
);
```
