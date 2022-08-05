# BasketballProps
CSPB 3287 Final Project
<h1> Basketball Props </h1>
<h2> Motivation </h2>
<p> In 2018 the federal ban on sports betting was overturned, this has led to sports gambling becoming an entirely new industry. Making smart and informed decisions with sports betting is incredibly important, and researching which decisions are worth it can help give gamblers an advantage that prevents them from throwing money away. This database aims to provide an easy way for users to research NBA data to help efficiently make those smarter decisions, specifically on NBA game results and player props. Player Props being the total of a specific statistic (such as Nikola Jokic’s rebounds in a game). In the past researching which bets had a history of hitting more often required users to have dozens of tabs open and clicking different windows to bring up multiple results at the same time. This database and the queries that I provide will give users a simple way to research which bets have a history of happening more often.</p>
<h2> Project Description </h2>
<p> This project contains three python notebooks in addition to this one. </p>
</br>
<p> tablesetup.ipynb handles the creation of the sql tables, triggers, and indices, it then loads in data from external CSV files and inserts them into the SQL Tables </p>
<p> This file contains the following actions: </p>
<p> Load in our required libraries and then connect to our provided database </p>
<p> Create our Tables, after the creation we add some constraints </p>
<p> Create appropriate Triggers for our Tables </p>
<p> Create appropriate Indices for our Tables </p>
<p> Load in external CSV files into Pandas Dataframe Objects </p>
<p> Remove Unneccessary columns and nan values from our Dataframes </p>
<p> Convert each Dataframe to a Dictionary </p>
<p> Insert the values from each Dictionary to the SQL Tables </p>
</br>
<p> tablemodifications.ipynb handles the testing of constraints, the testing of triggers through deletions, the testing of triggers a duplicate value, the testing of inserting a duplicate value </p>
<p> This file contains the following actions: </p>
<p> Load in the required libraries and connect to the database </p>
<p> Test that the constraints introduced in table hold by checking a record, and trying a duplicate insertion expecting a failure </p>
<p> Test each trigger that was created in tablesetup.ipynb </p>
</br>
<p> queries.ipynb handles the queries that are executed against the database </p>
<p> This file contains the following queries and is the main purpose of the project: </p>
<p> The following queries are executed </p>
<p> The Team Roster for a Specified Team in each season</p>
<p> Career Averages for Highest Scoring Players </p>
<p> Players who Averaged 10,5,5 </p>
<p> Best Individual Seasons </p>
<p> Season Averages for a Specified Player </p>
<p> Player Props against a Specific Team </p>
<p> Win Percentage of one Specific Team against another Specific Team </p>
</br>
<h2> Required Items Checklist </h2>
<p> The following items were required for this project, a brief description of how and where that requirement is met is provided below: </p>
<p> Multiple Tables -  tablesetup.ipynb, four tables were created for this project Teams, Players, Games, Games_Details </p>
<p> Relationships between Tables - tablesetup.ipynb, in the creation of tables each table other than Teams references another table </p>
<p> Show SQL Statments for table creation, insertion of initial data, updates and queries - tablesetup.ipynb contains table creation and insertion of initial data with acccompanying code, tablemodification.ipynb contains updates of data, queries.ipynb contains sql queries against the tables </p>
<p> Table Creation - tablesetup.ipynb, the four tables are created </p>
<p> Constraints - tablesetup.ipynb, Teams has a primary key, Games_Details and Games are both given composite primary keys tablemodifications.ipynb contains testing of these constraints</p>
<p> Indexes - tablesetup.ipynb, contains indices that were created to assist with the more common queries </p>
<p> Queries - queries.ipynb, filled entirely with queries </p>
<p> Joins between Tables - queries.ipynb, utilizes joins between tables in most of its queries </p>
<p> Grouping Results - queries.ipynb, groups results in most of its queries </p>
<p> Updates - tablesetup.ipynb, update triggers are implemented to update Games_Details when Players is updated, this trigger is tested in tablemodifications.ipynb </p>
<p> Deleting Items that are Foreign Keys in other tables - tablesetup.ipynb, deletion triggers are implemented here, those triggers are testested in tablemodifications.ipynb </p>
</br>
<h2> Main Queries </h2>
<p> This project computes a multitude of queries, from player season averages, to career averages, and much more. Each individual query is discussed more in-depth in the queries.ipynb notebook. Here I'd like to go over the two main queries that handle the motiviation behind the project </p>
<p> The first query Player Props was the main motivation behind the project. This query returns the player performances of a specific player against a specific team.</p> 
<p> This query is demonstrated by searching for Jaylen Brown performances against the Brooklyn Nets </p>
<p> First a CTE is created of all GAME_IDs where the nets were either the home or away team </p>
<p> Next Games_Details is queries to find the specific player-game records involving Jaylen Brown </p>
<p> These two are merged together in one query to find Jaylen Brown's performances against the Brooklyn Nets </p>

</br>
<p> 
