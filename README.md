# King-of-Ark
King of the hill game on the ark blockchain

The goal of this repo is to define the basic idea of how a king of the hill game could work on the Ark blockchain. 

Since Ark supports sending 64 chars of free text with every transaction it should be possible to setup something similar on the Ark blockchain!

- One Wallet would be the 'battleground'
- Every transaction sent to this wallet would be an 'entry'
- The vendorfield of every transaction would define the entrys properties


### Similar games which could inspire this game
- [Survival Game - Create Your Wolf](https://codegolf.stackexchange.com/questions/25347/survival-game-create-your-wolf)

### A basic example of a possible king of the hill game to understand the idea behing King of Ark

**R**ock **P**aper **S**cissors **L**izard Sp**o**ck* king of the hill [rules](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fe/Rock_Paper_Scissors_Lizard_Spock_en.svg/2000px-Rock_Paper_Scissors_Lizard_Spock_en.svg.png):

1) The first transaction to the wallet was with the vendorfield: PRLORPS

2) The second transaction was with the vendorfield: PRRSOOO

--> Transaction 2 would now 'battle' against the current King of the Hill which is transaction 1

--> The 'battle' would go char by char which means:

--> 1) P vs P = draw, 2) R vs R = draw 3) L vs R = Rock wins -> Transaction 2 is now the new King of the Hill since Rock crushes Lizard.

# The game
TODO
