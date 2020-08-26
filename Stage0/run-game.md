# run-game

## Feature

This module defines a run-game cron job that
interacts with other modules to run the game.

The run-game cron job does the following:

1. It calls play-game module to display current state of the game

2. It calls collision module to check collision of ball with any instance
of paddle or wall

3. If collision occurs, it calls ball module to update direction of ball

4. If collision occurs with wall behind a paddle, it calls score module
to update score. It then calls score module to check if score is winning score.

5. If game is in a winning state, it returns back to game engine

6. It calls ball module to move the ball

## Acceptance Criteria

### Scenario: -describe-a-scenario-of-this-module

  Given -give-initial-values-and-conditions

  When -event-happens

  Then -module-does-this

### -add-scenario-if-needed
