# Interaction Sequences

## Startup Sequence

1. User clicks PLAY GAME on home screen.
Home module calls game engine module.
Game engine module is the entry point in the game.

2. game engine module creates instances of paddle, ball, score and wall

3. game engine module creates run-game cron job

4. game engine module creates user-input cron job

5. run-game cron job does the following:

    It calls play-game module to display current state of the game

    It calls collision module to check collision of ball with any instance
    of paddle or wall

    If collision occurs, it calls ball module to update direction of ball

    If collision occurs with wall behind a paddle, it calls score module
    to update score. It then calls score module to check if score is winning score.

    If game is in a winning state, it returns back to game engine

    It calls ball module to move the ball

6. user-input cron job does the following:

    It checks for user input

    It calls player-controls module to decide action for user input

    If action is UP or DOWN, it calls paddle module to move UP or DOWN

    If action is ESC, it returns back to game engine

7. If game reaches winning state, stops run-game cron job,
stops user-input cron job and calls result module to display result

8. If game reaches QUIT state, calls quit-game module.
If quit-game module returns RESUME state, go to step 3.
If quit-game module returns END state, delete instances of ball, paddle,
score and walls. Return to home screen.

## Movement Initiation

run-game cron job calls ball module to move the ball
if game is not in winning state

## One score

The run-game cron job calls collision module
to check collision of ball with any instance of paddle or wall.
Collision module returns id of instance with which the ball collides

If collision occurs with wall behind a paddle, cron job calls score module
to update score of player with opposite side paddle
