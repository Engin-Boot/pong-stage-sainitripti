# game-engine

## Feature

This module defines the starting point of the game.
It also defines the lifetime of the game.

It creates instances of all the components of the game,
the ball, two paddles, score for each paddle and four walls.

It then starts run-game cron job and user-input cron job.
It stops the cron jobs when the game is either in winning state
or in quit state.

It calls the result module in case of winning state.

It returns back to home module.

## Acceptance Criteria

### Scenario: -describe-a-scenario-of-this-module

  Given -give-initial-values-and-conditions

  When -event-happens

  Then -module-does-this

### -add-scenario-if-needed
