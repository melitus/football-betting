# football-betting
This demostract how to get live football matches via an oracle contract and push the info to the smart contract for the end-user 


## Use case: 
- Users bet on boxing matches.
- The user can pull a list of bet-able boxing matches.
- The user can choose a match and place a bet on the winner.
- The user can bet any amount above a specified minimum.
- If the user’s pick loses, the user loses the entire amount of the bet.
- If the user’s pick wins, the user gets a portion of the pot based on the size of his/her bet and the total amount bet on the loser of the match, after the house (the contract owner) takes a small percentage of the winnings.


## How it Works: Oracle
The oracle pushes data regarding upcoming & past matches onto the ethereum blockchain. Its main function is to provide data on what football matches are available, and most importantly, who won them. The oracle is trusted to provide the correct winner for each match. Provides the following main user stories:

- enter a new boxing match record
- update status of a match (pending, underway, decided, etc.)
- declare the winner of a match

## How it Works: Contract
Allows bets to be placed on matches, collects the bets, and pays out the winnings (a small percentage going to the house). Available matches are pulled directly from the oracle.

The process of betting is as such:

- place a bet, specifying a match id, a chosen winner, and an amount to bet (must be above a set minimum); the funds to cover the bet are transferred in the function call
- on a draw, all bets are refunded in full
- on a loss, all funds sent are just gone forever
- on a win, a percentage of the total pot is transferred to bettor, proportional to the size of his/her bet, and minus a small cut for the house
Provides for the following main user stories:

- query the matches currently available for betting
- query past (decided) match results
- place a bet
- check the status of a bet or match

## How it Works: Client
No client currently exists, as of this writing, for the oracle. The client allows users to:

- see a list of bettable and decided matches
- see a list of their own bets
- query the total amount bet (by all users combined) on a particular match
place a bet
- query the status of a bet or match

