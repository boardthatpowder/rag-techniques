# Query Construction

![query construction](../images/images-query%20construction.png)

In **Retrieval-Augmented Generation (RAG)** systems, the **query construction** step involves transforming user inputs into structured queries that can effectively interact with various data sources, such as databases or knowledge graphs. This transformation enables the system to retrieve precise and relevant information, enhancing the quality of generated responses.

**1. Text-to-Metadata-Filter**

This technique involves analyzing the user's input to identify specific metadata criteria, which are then used to filter data sources for relevant information. By converting natural language queries into metadata filters, the system can efficiently narrow down search results.

*Example*:
- User Query: "Show me recent articles on climate change."
- Constructed Query: Filter articles where the topic is "climate change" and the publication date is within the last year.

[Notebook](./1%20-%20Text-to-metadata-filter.ipynb)

**2. Text-to-SQL**

In this approach, natural language queries are translated into SQL (Structured Query Language) statements, enabling interaction with relational databases. This allows users to access and manipulate structured data without requiring knowledge of SQL.

*Example*:
- User Query: "What is the average salary of software engineers in New York?"
- Constructed SQL Query: `SELECT AVG(salary) FROM employees WHERE job_title = 'Software Engineer' AND location = 'New York';`

[Notebook](./2%20-%20Text-to-sql.ipynb)

**3. Text-to-Cypher**

Similar to Text-to-SQL, this technique translates natural language queries into Cypher queries, which are used to interact with graph databases like Neo4j. It facilitates querying complex relationships within data stored in graph structures.

*Example*:
- User Query: "Find all colleagues of John Doe who have worked on project X."
- Constructed Cypher Query: `MATCH (p:Person {name: 'John Doe'})-[:WORKED_ON]->(:Project {name: 'Project X'})<-[:WORKED_ON]-(colleague) RETURN colleague.name;`

[Notebook](./3%20-%20Text-to-cypher.ipynb)