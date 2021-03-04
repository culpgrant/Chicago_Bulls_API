**Get All Data**
----
  This API Endpoint fetches all the data that is in the databse for a specific game date.
  
* **URL**

  <https://bhxm4s8tgd.execute-api.us-east-1.amazonaws.com/default/bulls_api_game_date?game_date=''>

* **Method:**
  
  `GET`

  
*  **URL Params**

   **Required:**
 
   `game_date=[string]`


* **Success Response:**
  

  * **statusCode:** 200 <br />
    **Content:** `"body": [
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
        }`
 

* **Example:**

<https://bhxm4s8tgd.execute-api.us-east-1.amazonaws.com/default/bulls_api_game_date?game_date=2021-03-01>

* **Notes:**

  Send a GET request to the URL above to retrieve all the data. Date format: YY-MM-DD
