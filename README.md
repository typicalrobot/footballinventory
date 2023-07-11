# footballinventory
This would help sports professionals to keep a well-maintained and structured database of all game data, allowing them to make changes quickly. It will also allow game viewers to view the points roster and compare ranks and games. <br>
# [ORM Model](https://github.com/typicalrobot/footballinventory/blob/main/ORM%20diagram.jpg) <br>
We used Halpin’s steps to create our ORM model and define relationships between various entities and domains.
Our ORM model consists of entities such as: Team, Match, Person, Stadium, League, Country.
Subtypes in our model are:
Person has subtypes being: Player, Manager and Referee with a constraint put on them so they do not overlap.
Team has subtypes being: National team and Club with a constraint on them.
Ternary relationship in our model is:
A team plays in a match in a stadium.
Many to many relationships:
A player can have many positions, A team can play several matches, A club can have many founders. <br>
# [Relational Schema](https://github.com/typicalrobot/footballinventory/blob/main/relational%20schema.jpg) <br>
A team has a club, manager, can be a national team, has specific players belonging to them, has manager(s).
A team can also win a match played in a specific stadium part of a specific league.
A player can have different positions in a certain team.
A person can be either a referee, a manager or a player. <br>
# [Stored procedure 1](https://github.com/typicalrobot/footballinventory/blob/main/Stored%20Procedure%201.png) <br>
The spTeamDateFoundedRange stored procedure allows a user to generate a query for the list of teams that were founded between a date range. This store procedure required two variables; 1. StartDate and EndDate. The StartDate is the earliest date range and the  EndDate  is the latest date range. If StartDate variable is wrong, it will use the date of the oldest team. Likewise if EndDate is null the function will use the least oldest club date.
<br>
# [Stored procedure 2](https://github.com/typicalrobot/footballinventory/blob/main/storedpro2.png) <br>
The spGetTeamWinCounts was created to query how many goals a particular team has scored in a particular stadium. The function takes 2 parameters. The first parameter is stadiumName,which takes the name of the stadium that is being queried and the second parameter takes the TeamName, which is the team who has scored those goals. When either the stadiumName of TeamName is not provided, an error message is displayed. <br>
# [Stored procedure 3](https://github.com/typicalrobot/footballinventory/blob/main/storedpro3.png) <br>
The spGetPointTableLeague  is a stored procedure that allows you to specify the name of the league using the variable leagueName and it will give you the league table showing all the teams in order of their point from highest to lowest. If the leagueName is not specified, the function will throw an error message. <br>
# [Trigger 1](https://github.com/typicalrobot/footballinventory/blob/main/trigger1.png) <br>
The trTeamWinsMatch trigger is an after insert trigger that is run automatically when the TeamWinsMatch table has a new entry. When a team wins a match in a particular league. They automatically get 3 points. Therefore there is no need to manually enter this information into the database. It can be done using triggers. This function updates the league table with the points of the team who just won the match by 3 points. <br>
[Running the trigger](https://github.com/typicalrobot/footballinventory/blob/main/trigrun1.png) <br>
# [Trigger 2](https://github.com/typicalrobot/footballinventory/blob/main/trigger2.png) <br>
The trMatchDetails is an after trigger that is run whenever the user inserts into the TeamPlaysMatchInStadium.  The function inserts all the details related to a match in the MatchDetails table. <br>
[Running the trigger](https://github.com/typicalrobot/footballinventory/blob/main/trigrun2.png)
# [Query 1](https://github.com/typicalrobot/footballinventory/blob/main/q1.png) <br>
List the details of all the players like Name, TEam,Jersey_No, Position, DOB Country_Name by joining multiple tables. <br>
# [Query 2](https://github.com/typicalrobot/footballinventory/blob/main/q2.png) <br>
This query gives information about the managers like Name, club they manage, nationality and their date of birth. <br>
# [Query 3](https://github.com/typicalrobot/footballinventory/blob/main/q3.png) <br>
This query gives out match details such as the stadium where its held, teams that are playing, capacity of the stadium. <br>
# [Query 4](https://github.com/typicalrobot/footballinventory/blob/main/q4.png) <br>
This gives us the number of matches played in the stadium. <br>
# [Query 5](https://github.com/typicalrobot/footballinventory/blob/main/q5.png) <br>
This query uses points to calculate the rank for a particular league table. <br>
 



