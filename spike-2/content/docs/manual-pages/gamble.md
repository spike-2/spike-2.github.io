---
title: "Gamble"
draft: false
categories:
    - Documentation
tags:
    - "Gamble"
    - Manual Pages
---

Welcome to the only casino in the world that accepts [Spike Bucks](/docs/manual-pages/spike-bucks)! Learn more about our games and services below.

## Games

### `$cointoss`
`$cointoss [wager] [heads|tails]`

The simple game of tossing a coin tries to stay as true to reality as possible. While a coin toss is fairly close to 50/50 odds, it isn't perfectly fair. In fact, depending on the person tossing the coin, the type of coin, and the coin-face chosen, the odds of winning are often closer to 49/51. $cointoss has 49/51 odds, in favor of Spike. To keep the game more balanced, the winnings have been raised so that the user will make more than double their wager when the win.

**Odds:** 51/49 in favor of Spike  
**Payout:** 2.2x wager

### `$dice`
`$dice [wager]`

The game of dice consists of rolling 2 fair. six-sided dice. 

Outcome|Win
---|---
Sum > 7|2.7x wager
Doubles|3.5x wager
Double Sixes|6x wager

### `$slots`
`$slots [wager]`

Slots may be the most simple to play, however, the winnings can be a bit complicated. When the users pulls the lever on the slot machine, 4 spinning reels, which can land on any one of eleven possible positions (14,641 permutations). 

Outcome|Example|Win
---|---|---
Two of a Kind|`aabc`|2.5x wager
Two of a Kind w/ Wildcard|`aab$`|5x wager
Two of a Kind w/ 2 Wildcards|`$$aa`|10x wager
Three of a Kind|`aaba`|6x wager
Three of a Kind w/ Wildcard|`$aaa`|12x wager
Four of a Kind|`aaaa`|16x wager
Four Wildcards (Jackpot)|`$$$$`|151x wager

To unlock access to the slots, you'll need to purchase access in the [Spike Store](/docs/manual-pages/spike-store/).

## Services

### `$wallet`
Check your balance of Spike Bucks. You can also check someone else's balance by @-mentioning them in the command invocation (i.e. `$wallet @user`)

### `$gift`
`$gift [amount] [user]`

Gift some of your Spike Bucks to a friend!

### `$leaderboard`
See how you rank amongst the rest of the server in Spike Bucks balance. Who's in the 1%? Spoiler Alert: It's probably Joshua Maxwell.