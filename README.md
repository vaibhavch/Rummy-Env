# Rummy-Env
Rummy card game gym environment

* Implement an OpenAI Gym Rummy Card Game simulation environment


# Requirement
```
pip install gym
```
# Description
* Use two deck of cards to play (53+53+2).
* Two opening Cards are drawn. 
* Players take turns to play a card in an counter clockwise direction.
* All players start with 0 points. The first person go past -100 points then game over. The player which get highest points is the game winner.


# Scoring
* Rank 2 to 10 cards scores negative points respective to their ranks
* Queen: -12 points, Jack: -11 points, King: -13 points, Ace: -14 point
* Show: +25 points (or may be 0 points)
* Drop: -25 points


# Game Flow
1.	env.reset() -> Start Rummy game, env send the GameStart event to all player.
2.	env send NewRound event to all player.
3.	env send ShowPlayerHand event to each player to get the hand cards.
4.  env send play_strategy event to the player, the player choose a card and send PlayStrategy_Action event to env.
5.  env will send ShowStrategyAction event to all players to tell them the player's action.
6.  After all players take a card, env will send ShowStrategyEnd event to tell the players that which one win this strategy.
7.  After last Strategy, env will send RoundEnd event to announce which player win this round, if the loser's score < min_score, env send GameOver event to all players and exit the game, or send NewRound event to all players to continue game.


# Support Agent
* Human
* Random 

# Environment learning simulation ideas
* Genetic Algorithm
* Proximal policy optimization
