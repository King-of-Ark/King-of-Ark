# King-of-Ark
King of the hill game on the ark blockchain

# The Game

- One Wallet is the `battleground`
- Every transaction sent to this wallet is an `entry`
- The vendorfield of every transaction defines the `entrys` properties.
- Every new `entry` fights against the current `King of Ark` on the `battleground`. If the new entry wins -> it will become the new `King of Ark`.

# How To Become The New `King of Ark` ?

The battle between every `entry` is based on [Rock Paper Scissors Lizard Spock](http://bigbangtheory.wikia.com/wiki/Rock_Paper_Scissors_Lizard_Spock)

![Rock Paper Scissors Lizard Spock image](https://upload.wikimedia.org/wikipedia/en/c/cc/Rock_paper_scissors_lizard_spock.png "Rock Paper Scissors Lizard Spock rules")



## But how can I choose which properties my entry uses during a fight ?

### 1) The Action Properties

The action properties define which actions of 'Rock Paper Scissors Lizard Spock' your entry uses and in which order. 
They are mapped to single letters the following way:

```
Rock = R
Paper = P
Scissors = S
Lizard = L
Spock = O
```

Example: 
The current `King of Ark` has the following action properties: 
`PRLORPSPRLORPS`


Which means the first action the current `King of Ark` uses against your entry would be: Paper, then Rock, then Lizard,...

These actions are now mapped against the numbers in the `transactionID` of your entry. This mapping defines the damage a win with the corresponding action does to your opponent.  

Example: 
The current `King of Ark` has the following action properties and `transactionID`:
- TransactionId: `de74619de372bcdd245211e15c33c21f84c74e2b62158f6cd20e4e6594537888`
- Properies:`PRLORPSPRLORPS`

which gives the following mapping: 

- A win with **P** does **7 damage**
- A win with **R** does **4 damage**
- A win with **L** does **6 damage**


### 2) The Health Properties

The health of your entry is defined by the number of health properties your entry has. One health proeprty is defined as `+`.

Example:
Current `King of Ark` has the following properties:
- TransactionId: `de74619de372bcdd245211e15c33c21f84c74e2b62158f6cd20e4e6594537888`
- Properies:`PRLORPSPRLORPSRLORPS++++++++++++++++++++++++++++++++++++++++++++`

 The amount of `+` is **54**. Which means the current `King of Ark` has 54 health. 
 
### 3) The Health regeneration Properties

The health regeneration of your entry is defined by the number of `health regeneration` properties your entry has. One health `health regeneration` property is defined as `*`.

Health regeneration means: After every round your `entry` regenerates `health regeneration` amount of health

Example:
Current `King of Ark` has the following properties:
- TransactionId: `de74619de372bcdd245211e15c33c21f84c74e2b62158f6cd20e4e6594537888`
- Properies:`PRLORPSPRLORPSRLORPS******++++++++++++++++++++++++++++++++++++++`

 The amount of `*` is **6**. Which means the current `King of Ark` regenerates 6 health after every round. 
 
 ## The Fight

- The fight ends if one of the two entry has 0 or less life.
- If one entry is out of attack porperties the other entry can deal the rest of his attack properies for free on him.

Example:

Current King of Ark:
- TransactionId: `as56df19de372bcdd245211e15c33c21sd123fsdf58f6cd20e4e6594537888`
- Properies:` SOOORS++++++++++++++++++++++++++++++++++++++++++++++++++++++++++`

New Entry:
- TransactionId: `de74619de372bcdd245211e15c33c21f84c74e2b62158f6cd20e4e6594537888`
- Properies:` PRLORPSPRLORPSRLORPS++++++++++++++++++++++++++++++++++++++++++++`

The fight:
```
1) S (Scissor) vs P (Paper) -> S wins and does **5** damage ->  45 life left for 'new entry'
2) O (Spock) vs R (Rock) -> O wins and does 4 damage -> 41 life left for 'new entry'
3) O (Spock) vs L (Lizard) -> L wins and does 6 damage -> 52 life left for 'King of Ark'
..
```

 ## The Battlefield
 
 - The first 4 letters in the `battlefields` address define a 2D grid:
Example: `AQ32qQRFtAY8Fqyb563p2fcYBd4dMKSv5x` -> 32 x 85 grid

- The last 4 numbers in the transactionID of an entry define where the entry spawns on the battlefield
Example: `as56df19de372bcdd245211e15c33c21sd123fsdf58f6cd20e4e6594531082` -> spawn at 10;82

- An `entry` starts to move the closest way to the current King. 

- Entrys can 'see' 4 fields wide. If they spot another entry on their way to the current King they would attack this entry first. 

- The second letter of the `transactionID` defines in which round the entry enters the battlefield. Example: `as56df19de372bcdd245211e15c33c21sd123fsdf58f6cd20e4e6594531082` s -> 19 turns after the `entry` before. 

