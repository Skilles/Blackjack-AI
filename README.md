# Blackjack-AI
Simple Blackjack using a genetic algorithim

## Algorithim
This project uses the NEAT library to generate random neural networks that then train against the house in order to get the highest fitness (in this case W/L ratio). 
Those with the highest scores are then rebreeded to create the next generation.

## Results
The bot achieved a win rate of 44% over ~680 generations. Using optimal playing strategy for Blackjack, the win percentage is 42.99%. The higher than optimal win rate was likely due to only 1 deck being used in between shuffles (most Casinos use 4).

## Information
My latest results are using a recurrent network (yes the config is named feedforward), but I believe using a feedforward network would yield similar results.

The neural net has access to three inputs: total value of hand, revealed house card value, and the total value of cards in the deck (only here for speeding up the evolution).

The output is a hit, otherwise the bot stays.

## Future
In the future, I might implement betting and see the bots profit (likely to be negative since BJ is a house-favored game) which would significantly increase the complexity of the network.

## Issues
Since the game runs in pygame, there is likely some overhead that occurs when drawing game states and actions (only one generation is drawn). 
I featured some design fitness restrictions such as killing the network if the loss ratio is too high. In reality, these restrictions might affect the quality of the training but it does speed it up.
