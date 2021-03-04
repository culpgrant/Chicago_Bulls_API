# Chicago_Bulls_API
This is a repository directly related to my other repository [Chicago_Bulls_ETL_Twitter](https://github.com/culpgrant/Chicago_Bulls_ETL_Twitter) and the [Twitter Account](https://twitter.com/stats_bulls). This is the documentation to the REST API to query the database that runs the Twitter Account.

# General Info
Please see the other .md files that breakdown how to use this Bulls API.

Endpoints:
- Query all data: [Example](https://github.com/culpgrant/Chicago_Bulls_API/blob/main/API_Get_All.md)
- Query data by player id: [Example](https://github.com/culpgrant/Chicago_Bulls_API/blob/main/API_Get_Player_ID.md)
- Query data by game date: [Example](https://github.com/culpgrant/Chicago_Bulls_API/blob/main/API_Get_Game_Date.md)

What data does it have?
- It has the Bulls Box Score Data from the 2020-2021 season.

Endpoints?
- The three .md files within this Repository have all the information associated with the three endpoints available currently.

# Sample Response:
{
    "statusCode": "200",
    "body": [
        {
            "player_id": 1628990,
            "player_name": "Chandler Hutchison",
            "team_id": "1610612741",
            "team_abbreviation": "CHI",
            "age": 24,
            "gp": 1,
            "win": 1,
            "loss": 0,
            "mins": 6.4,
            "fgm": 1,
            "fga": 4,
            "fgthreem": 0,
            "fgthreea": 1,
            "ftm": 0,
            "fta": 0,
            "oreb": 0,
            "dreb": 3,
            "reb": 3,
            "ast": 0,
            "tov": 1,
            "stl": 0,
            "blk": 0,
            "blka": 0,
            "pf": 1,
            "pfdrawn": 0,
            "pts": 2,
            "plusminus": -2,
            "game_date": "2020-12-29",
            "season": "2020-2021"
        }


# How is it done?
This is an API all hosted on AWS (same with the database). ![Image of Structure](https://user-images.githubusercontent.com/59777128/109910653-3b6a4880-7c6e-11eb-811a-ffb0e582bb7c.jpeg)
I have used AWS API Gateway to handle the calls from external users. Each endpoint/resource is tied to a Lambda Function that is triggered by the API call to that endpoint. The API only supports GET methods. The Lamda functions are Python functions that call the RDS Postgres database with the information passed from the call. The function is calling a stored procedure/function within the RDS Postgres database to protect against SQL Injection attacks as the user input has to be specific and is being cleaned.

