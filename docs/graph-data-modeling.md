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