# COVID-19 Social-Distancing Model using Spark RDD

This project simulates scalable COVID-19 proximity analysis using PySpark RDDs. It models a real-world concert scenario where people are seated outdoors and identifies infection risk zones through spatial distance checks across three queries. Here, we work with 3 synthetic datasets representing people and their infection status. Using Spark RDDs, we perform efficient distance joins to detect close contacts and analyze the risk of exposure in large spatial datasets.

## Contents  

- `data/`: Subsets of synthetic datasets used in the analysis are added here, these were created to simulate real-world social spacing and infection scenarios.  
`subset_people.csv` - All individuals at the event (randomly generated people with id, x, y, name and age)  
`subset_infected.csv` - Subset of infected individuals (same format as above, subset of subset_people.csv)  
`subset_some_infected.csv` - Same as people data, but includes a new column INFECTED with values "yes" or "no" for each person  

- `output/`: Text outputs of all three queries — generated from running the RDD-based logic in Spark.  
`Query-1.txt` - List of close contact pairs (pi, infect-i)  
`Query-2.txt` - Unique IDs of all people at risk (duplicates removed)  
`Query-3.txt` - Infected person + count of people within 6 units  

- `utils+model/`: `social-distancing-model.ipynb` - End-to-end notebook with dataset generation logic, Spark RDD setup and all 3 proximity queries as below.

## Queries

| **Query** | **Title**                         | **Task**                                                                 |
| --------- | --------------------------------- | ------------------------------------------------------------------------ |
| Q-1   | Close Contact Detection           | For each infected person, find all individuals within 6 units distance.  |
| Q-2   | Unique At-Risk Individuals        | Return distinct IDs of all people who were close to any infected person. |
| Q-3   | Infected-to-Contact Count Mapping | For each infected person, count how many others are within 6 units.      |  
