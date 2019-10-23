# data
Basketball data collected and triaged by the team at Pivot Analysis.

### Data Model

Right now there is only one worksheet, "Events". An **Event** is our standardized model for play-by-play actions in a game.

For each event (row), these are the fields (columns):

| Field             | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
| **Actor**         | The normalized<sup>1</sup> name of the player that performed the action. |
| **Roster**        | The name and key<sup>2</sup> of the roster to which the actor belongs. |
| **Order**         | The order the event was collected in.                        |
| **STS**           | "Same Time Sort", which is how we sort events so that fouls are attributed to the correct players even when several events occur at the same clock. |
| **Period**        | Period/quarter of the game                                   |
| **Clock**         | Time on the clock                                            |
| **Seconds LIG**   | Seconds _Left in Game_. Useful for ordering the clock over the course of the entire game. |
| **Seconds EIG**   | Seconds _Elapsed in Game_, the inverse of the LIG.           |
| **Seconds LIP**   | Seconds _Left in Period_                                     |
| **Visitor**       | The score for the visitor after that event occurred.         |
| **Home**          | The score for the home team after that event occurred.       |
| **Margin**        | The margin of the game as an absolute value.                 |
| **Action**        | A standardized representation of what that event represents according to its notes. |
| **Acting Lineup** | The lineup for the team that performed the action at the time of that event. |
| **Opp Lineup**    | The opposing lineup that was on the floor when the action was performed. |
| **Notes**         | The original notes on the play                               |
| **Garbage**       | Event is in the last 5 minutes with a margin >= 15           |
| **Clutch**        | In the last 5 minutes, but the margin is < 10                |
| **Final Two**     | Final two minutes of the half or game                        |
| **Overtime**      | Is the game in overtime?                                     |
| **Starting**      | Was this action performed by the starting lineup?            |
| **Normal**        | If none of the previous flags apply, it's _Normal_           |
| **X**             | If available, the 10 units per foot X coordinate of the action (this is the scale used by stats.nba.com) |
| **Y**             | If available, the 10 units per foot Y coordinate of the action (this is the scale used by stats.nba.com) |
| **Distance**<sup>3</sup>  | The hypotenuse of the X, Y calculation from the rim used for approximating shot distance (in feet) |

### Available Data
* Duke MBB 2018
* NBA Opening Night 2019-20 (w/ Locations)

### Other Notes
##### Locations

Only one game has locations in the initial Duke dataset, which is their 2018 NCAA tournament game against Michigan State. These locations should be used as approximations only due to their provenance.

### Contact

For more information, please hit us up at contact@pivotanalysis.com. 



<sup>1</sup> Normalized names are those that remove special characters in an effort to make them as easy to match as possible.  
<sup>2</sup> Keys are created for both rosters and lineups that are the first three letters of the normalized name plus the jersey number for use in tabular formats like Excel.  
<sup>3</sup> Not all events have locations and not all games have locations. When available for NCAA games these should be considered approximate. If available for NBA games, these should be 1:1.

