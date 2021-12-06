---
title: "Bet"
draft: false
categories:
    - Documentation
tags:
    - "Bet"
    - Manual Pages
---

With Spike, you can now run bets. These allow users to set up wagering scenarios where all users, including the bet creator, can stand to win or lose a lot of Spike Bucks.

## Creating a Bet

Create a bet using a command with this form:
```md
$bet Title
Description of the bet
:emoji: bet_amount win_amount What this wager means
:emoji: bet_amount win_amount What this wager means
...
```
Please ensure emoji get fully rendered. Don't send just the `:emoji_code:`. Only Discord default emoji and guild emoji for the guild Spike is in are valid. Don't use emoji from another guild.

Your bet will be assigned a unique ID, which you as the creator will need to end it later.

## Wagering on a Bet

To see a list of active bets, type `$activebets`. Visit any of these bet embed messages to wager. **Please also check that Spike is online.** Following the rest of these instructions while Spike is offline will result in you not actually wagering or removing your wager.

To bet on one or more wagers, simply react with the correct emoji below the message. You must have the funds in your wallet at the time of betting, and they will be removed immediately upon betting. If you remove your bet before it closes, you will be refunded the bet amount. See below for payout information.

**Note: Bet creators cannot bet on any of their own bets.**

## Ending a Bet

To end a bet, the creator must send a message of the form `$endbet bet_id :winning_emoji:`. 

* Be sure to send the fully rendered emoji, not just the `:code:`.
* Bets can only have one winner.
* Only the bet creator can end a bet.

## Payout Information

Payouts come first from the pot of bets, then from the creator's personal wallet. If the pot + creator's wallet can pay out the specified winning amount to all winners, it will be paid out. If not, all winners will receive their bet + 1, and the creator's wallet will be wiped to zero. Should the pot still have money after paying winners, the creator gets to keep the rest.

