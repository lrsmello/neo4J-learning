# Graph Data Modeling

## Getitng Started
In this module, you will learn about:

- What graph data modeling is.
- How domain knowledge is important for modeling.
- The difference between a graph data model and an instance model.

### Data modeling process
Here are the steps to create a graph data model:

1. Understand the domain and define specific use cases (questions) for the application.

2. Develop the initial graph data model:
- Model the nodes (entities).
- Model the relationships between nodes.

3. Test the use cases against the initial data model.

4. Create the graph (instance model) with test data using Cypher.

5. Test the use cases, including performance against the graph.

6. Refactor (improve) the graph data model due to a change in the key use cases or for performance reasons.

7. Implement the refactoring on the graph and retest using Cypher.

### The Domain
Before you begin the data modeling process you must:

- Identify the stakeholders and developers of the application.
- With the stakeholders and developers:

    -  Describe the application in detail.
    - Identify the users of the application (people, systems).
    - Agree upon the use cases for the application.
    - Rank the importance of the use cases.

Most use cases for an application can be enumerated by a comprehensive list of questions. The use cases help to define how the application will behave at runtime.

Here are the use cases you will be working with to develop the initial graph data model:

1. What people acted in a movie?

2. What person directed a movie?

3. What movies did a person act in?

4. How many users rated a movie?

5. Who was the youngest person to act in a movie?

6. What role did a person play in a movie?

7. What is the highest rated movie in a particular year according to imDB?

8. What drama movies did an actor act in?

9. What users gave a movie a rating of 5?

In our domain, we want to differentiate a person who acted in or directed a movie and a user or reviewer who rated a movie. We have much more information about people such as their birth date, their tmdbId etc. Users who rated movies will just be named or identified.

### Purpose of the Model

#### Types of models
When performing the graph data modeling process for an application, you will need at least two types of models:

- Data model
- Instance model

##### Data Model
The data model describes the labels, relationships, and properties for the graph. It does not have specific data that will be created in the graph.

There is nothing that uniquely identifies a node with a given label. A graph data model, however is important because it defines the names that will be used for labels, relationship types, and properties when the graph is created and used by the application.

##### Instance Model
An important part of the graph data modeling process is to test the model against the use cases. To do this, you need to have a set of sample data that you can use to see if the use cases can be answered with the model.

## Modeling Nodes
In this module, you will learn about:

- Identifying the entities from your use cases.
- Creating nodes in the graph in support of the data model.

### Defining Labels
Entities are the dominant nouns in your application use cases:

1. What ingredients are used in a recipe?
2. Who is married to this person?

The entities of your use cases will be the labeled nodes in the graph data model.

### Node properties
Node properties are used to:

- Uniquely identify a node.
- Answer specific details of the use cases for the application.
- Return data.

### Unique identifiers in the Movie graph
In the Movie graph, we use the following properties to uniquely identify our nodes:

- Person.tmdbId
- Movie.tmdbId

## Modeling Relationships
The Neo4j components that are used to define the graph data model are:

- Nodes
- Labels
- Relationships
- Properties

### Data Modeling Process
In this module, we will learn about:
- Identifying the relationships from use cases.
- Creating relationships in the graph to support the data model.

Connections are the verbs in your use cases:
- What ingredients are used in a recipe?
- Who is married to this person?

### Relationship direction
When you create a relationship in Neo4j, a direction must either be specified explicitly or inferred by the left-to-right direction in the pattern specified. At runtime, during a query, direction is typically not required.

A relationship is typically between 2 different nodes, but it can also be to the same node.

### Fanout

<p align="center">
    <img src="docs/img/fanout.png" alt="fanout"/>
</p>

Here, we have entities (Person, Residence) represented not as a single node, but as a network or linked nodes.

This is an extreme example of fanout, and is almost certainly overkill for any real-life solution, but some amount of fanout can be very useful.

### Properties for relationships
Properties for a relationship are used to enrich how two nodes are related. When you define a property for a relationship, it is because your use cases ask a specific question about how two nodes are related, not just that they are related.

## Testing the Model
In this module, we will test that the graph can be used to test the use cases of the model.

### Why Test?
use the use cases to design the data model that includes labels for nodes, relationship types and direction, and properties for the nodes and relationships.

You have also populated the graph to implement the data model with a small set of test data. To ensure that the graph can satisfy every use case, you must test the use cases against the graph.

## Refactoring the Graph
In this module, we will learn about:
- Why we refactor a graph data model and graph.
- Adding labels to the data model.

### Why refactor?
Refactoring is the process of changing the data model and the graph.

There are three reasons why you would refactor:
- The graph as modeled does not answer all of the use cases.
- A new use case has come up that you must account for in your data model.
- The Cypher for the use cases does not perform optimally, especially when the graph scales

### Steps for refactoring
To refactor a graph data model and a graph, you must:
1. Design the new data model.
2. Write Cypher code to transform the existing graph to implement the new data model.
3. Retest all use cases, possibly with updated Cypher code.