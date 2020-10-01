# README


## Improvements


### Players should pass the ball
- Players literally don't pass the ball, even the goal keeper.
- Once, the ball is in play, the default behavior is to run with the ball towards the opponents net and once within a threshold distance, shoot!
- But, this is not ideal behavior, particularly when there are other players who potentially have a higher chance of scoring.
- Ex: Shooting from the center is better than shooting from the flanks.


### No shooting from flanks
- Currently, players shoot from the flanks, mostly the left flank towards the goal when they are within the threshold distance of shooting.
- But, the threshold distance is only based on the `X` coordinate.
- So, it so happens that players are shooting from the corner and the opponents goal-keeper has enough time to collect the ball.
- Instead, we want the players to close in on the goal diagonally and then shoot once inside the inner box.


### Goal keeper never crosses the inner box
- When the goal keeper gets the ball, the goal keeper tends to run with the ball towards the opponents net.
- Instead, we want the goal keeper to pass the ball to a player and guard the net.


### Tackle at the future position
- When a player tackles the opponent with a ball, that seems to happen at the older location of the opponent, a place the opponent has moved on from.
- Instead, we want to attack the opponent at the potential future location.
