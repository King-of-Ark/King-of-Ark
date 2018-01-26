# King-of-Ark
King of the hill game on the ark blockchain

The goal of this repo is to define the basic idea of how a king of the hill game could work on the Ark blockchain. 

### Similar games which could inspire this game
- [Survival Game - Create Your Wolf](https://codegolf.stackexchange.com/questions/25347/survival-game-create-your-wolf)

# The game

- One Wallet would be the `battleground`
- Every transaction sent to this wallet would be an `entry`
- The vendorfield of every transaction would define the entrys properties and how they fight against each other.
- Every new entry fights against the current `King of Ark` on the `battleground` if the new entry wins -> he will become the new `King of Ark`

## Properties  and how to win

Not defined yet: See [Properties discussion](https://github.com/geckogecko/King-of-Ark/issues/1)
