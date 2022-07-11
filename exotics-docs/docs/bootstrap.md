# Bootstrapping

Our bootstrap phase is our token distribution and protocol liquidity raise period. It will include the launch of many small revenue generating games. These will gradually increase in complexity and make greater use of the protocols liquidity.

Our initial game is a twist on the classic dice game but modified to enable growth from zero initial balance. Check back frequently as we have a number of games in the pipeline.

## Dice game

Our first game we have kept incredibly simple (KISS) and is a game based on the outcome of a weighted dice. It uses the [parimutuel betting](https://en.wikipedia.org/wiki/Parimutuel_betting) system to calculate probabilities and payouts. This has the effect that the odds are not known until the pool of wagers is closed, to offset this we will reward early players of the game with XTC tokens.

As this game uses a pooled payout it runs on a frequency and is not an instant win game (although our future games may be). A new role takes place every 10 minutes. XTC tokens are distributed as rewards to all players of the game, to further incentive early betting (which are at a disadvantage due to changing odds) the incentives will be greatest 10 minutes (are earlier) before the role starts, they drop by 10% each minute up until the game starts.

The game works by assigning weight to the face of a 6 sided die. This weight is assigned based on the total sum of all wagers on this number.

As part of our Q4 roadmap we will be implementing a _jackpot_ feature where rolls could be eligble for a bonus payout. To play the game visit our [dapp]() and choose a roll to bet on.

## Fairness

Roll results are provided by [chainlink VRF](https://docs.chain.link/docs/chainlink-vrf/) providers. This ensures a fair and tamperproof way of deciding results.

## Calculations

The following calculations and parameters are applied to the game.

**Protocol fee**: An amount of the total wager added to the protocol owned liquidity

**Revenue fee**: An amount of the total wager distributed to XTC stakers

**Odds**: (wager - fees) * total selected outcome / sum all outcomes

**Roll ID**: A timestamp of when the roll will take place

**Decimal Odds**: 1 / (wagers / totalWagers)
