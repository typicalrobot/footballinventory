# footballinventory
This would help sports professionals to keep a well-maintained and structured database of all game data, allowing them to make changes quickly. It will also allow game viewers to view the points roster and compare ranks and games. <br>
# [ORM Model] (https://github.com/typicalrobot/footballinventory/blob/main/ORM%20diagram.jpg) <br>
We used Halpin’s steps to create our ORM model and define relationships between various entities and domains.
Our ORM model consists of entities such as: Team, Match, Person, Stadium, League, Country.
Subtypes in our model are:
Person has subtypes being: Player, Manager and Referee with a constraint put on them so they do not overlap.
Team has subtypes being: National team and Club with a constraint on them.
Ternary relationship in our model is:
A team plays in a match in a stadium.
Many to many relationships:
A player can have many positions, A team can play several matches, A club can have many founders. <br>


# Stored procedure 
The spTeamDateFoundedRange stored procedure allows a user to generate a query for the list of teams that were founded between a date range. This store procedure required two variables; 1. StartDate and EndDate. The StartDate is the earliest date range and the  EndDate  is the latest date range. If StartDate variable is wrong, it will use the date of the oldest team. Likewise if EndDate is null the function will use the least oldest club date.
<br>
