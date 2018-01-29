# King-of-Ark
King of the hill game on the ark blockchain

# The game

- One Wallet is the `battleground`
- Every transaction sent to this wallet is an `entry`
- The vendorfield of every transaction would defines the `entrys` properties.
- Every new `entry` fights against the current `King of Ark` on the `battleground`. If the new entry wins -> it will become the new `King of Ark`.

# How to become the new `King of Ark` ?

Work in progress: See [Properties discussion](https://github.com/geckogecko/King-of-Ark/issues/1)

The battle between every `entry` is based on [Rock Paper Scissors Lizard Spock](http://bigbangtheory.wikia.com/wiki/Rock_Paper_Scissors_Lizard_Spock)

![Rock Paper Scissors Lizard Spock image](https://upload.wikimedia.org/wikipedia/en/c/cc/Rock_paper_scissors_lizard_spock.png "Rock Paper Scissors Lizard Spock rules")

You are able to define two 'poperties' for your entry:

## Properties

### 1) The action properties

The action properties define which actions of 'Rock Paper Scissors Lizard Spock' your entry uses and in which order. 
They are mapped to single letters the following way:

```
- Rock = R
- Paper = P
- Scissors = S
- Lizard = L
- Spock = O
```

Example: 
The current `King of Ark` has the following action properties: 
`PRLORPSPRLORPS`


Which means the first action the current `King of Ark` uses against your entry would be: Paper, then Rock, then Lizard,...

These actions are now mapped against the numbers in the `transactionID` of your entry. This mapping defines the damage a win with the corresponding action does to your opponent.  

Example: 
The current `King of Ark` has the following action properties and `transactionID`:
TransactionId: `de74619de372bcdd245211e15c33c21f84c74e2b62158f6cd20e4e6594537888`
Properies:`PRLORPSPRLORPS`

which gives the following mapping: 

- A win with **P** does **7 damage**
- A win with **R** does **4 damage**
- A win with **L** does **6 damage**


### 2) The health properties

The health of your entry is defined by the number of health properties your entry has. One health proeprty is defined as `+`.

Example:
Current `King of Ark` has the following properties:
TransactionId: `de74619de372bcdd245211e15c33c21f84c74e2b62158f6cd20e4e6594537888`
Properies:`PRLORPSPRLORPSRLORPS++++++++++++++++++++++++++++++++++++++++++++`

 The amount of `+` is **54**. Which means the current `King of Ark` has 54 health. 
 
 ## The fight

- The fight ends if one of the two entry has 0 or less life.
- The fight ends if the new Entry is out of attack Properties and was not able to 'kill' the current `King of Ark`. -> The current `King of Ark` stays the King.
- If on entry is out of attack porperties the other entry can deal the rest of his attack properies for free on him.

Example:

Current King of Ark:
TransactionId: `as56df19de372bcdd245211e15c33c21sd123fsdf58f6cd20e4e6594537888`
Properies:` SOOORS++++++++++++++++++++++++++++++++++++++++++++++++++++++++++`

New Entry:
TransactionId: `de74619de372bcdd245211e15c33c21f84c74e2b62158f6cd20e4e6594537888`
Properies:` PRLORPSPRLORPS++++++++++++++++++++++++++++++++++++++++++++++++++`

The fight:
```
1) S (Scissor) vs P (Paper) -> S wins and does **5** damage ->  45 life left for 'new entry'
2) O (Spock) vs R (Rock) -> O wins and does 4 damage -> 41 life left for 'new entry'
3) O (Spock) vs L (Lizard) -> L wins and does 6 damage -> 52 life left for 'King of Ark'
..
```

