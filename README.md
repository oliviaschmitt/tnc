
Running this code as is will create a knowledge graph for conservation technology learnings at TNC.
This can be used as a template to create own tags and relationships, thus own knowledge graphs, with other databases.


For creating a node graph in neo4j out of database stored in Smartsheet or Excel:




This will utilize Jupyter Notebooks (.ipynb) to run the scripts. (Can download Anaconda Navigator to run Jupytr Notebooks)



TAGS: (allows you to search for properties and create relationships)
1. Identify tags wanted in node graph. This should be sourced from database so that tags match column properties. <img width="893" alt="Screen Shot 2022-09-14 at 11 14 21 AM" src="https://user-images.githubusercontent.com/89168989/190194301-9dae7c09-4990-49a7-8ded-6d822c455b80.png">
2. Export tags to csv. 
3. Convert csv to json. I used https://csvjson.com/csv2json
4. See tags.json for formatting


CARDS: (the database)
1. Export learning card database (each row is a card) to csv
2. Convert csv to json
3. See csvjson.json for formatting


This formats your tags and cards to be ready for the scripts in json_to_neo4j that will create nodes and relationships in neo4j.


NEO4j:
1. Create neo4j AuraDB account
2. Create new instance (auradb free, time region doesn't matter, empty database)
3. Save password in json_to_neo4j notebook.
g = Graph(
    "neo4j+s://{YOUR CONNECT URL HERE}",
    auth=("neo4j", "{YOUR PASSWORD HERE")
)
4. Query -> copy connecturl to above cell in json_to_neo4j
5. Input Password
6. Once you connect and run cells in notebook, nodes and relationships should be created!


Other Tips
- To delete in neo4j: https://neo4j.com/docs/cypher-manual/current/clauses/delete/
- Can use neo4j Bloom to visualize relationships once created (instead of Query in Step 4 -> Explore)

