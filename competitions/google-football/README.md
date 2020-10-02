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


### Ability to detect and break loops in movement

Source: https://www.kaggle.com/c/google-football/discussion/187381#1034619 from Taaha Khan

> Not necessarily a bug, but an interesting thing that I found: in [this game](https://www.kaggle.com/c/google-football/submissions?dialog=episodes-episode-3657442), at around 0:35 time, the ball is right by the edge of bounds, and the agents are all confused as to what should be done (this loop was only broken when the second half reset). Maybe a sort of a clock should be put in place so that agents can't just stall out the rest of the game and force a win if they are ahead, sort of like a shot-clock in basketball.
>
> I recommend contestants to code in something that has the ability to detect and break loops in movement so that this issue can't be exploited in the game.