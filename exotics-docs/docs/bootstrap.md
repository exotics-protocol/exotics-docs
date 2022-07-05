# Bootstrapping

Our bootstrap phase is our token distribution and protocol liquidity raise period. IT will include the launch of many small revenue generating games. These will gradually increase in complexity and make greater use of the protocols liquidity.

Our initial game is a twist on the classic dice game but modified to enable growth from zero initial balance. Check back frequently as we have a number of games in the pipeline.

## Dice game

Our first game we have kept incredibly simple (KISS) and is a game based on the outcome of a weighted dice. It uses the [parimutuel wagering]() system to calculate probabilities and payouts. This has the effect that the odds are not known until the pool of wagers is closed, to offset this we will reward early players of the game with XTC tokens.

As this game uses a pooled payout it runs on a frequency and is not an instant win game (although our future games may be). A new role takes place every _n_ seconds.

As part of our Q4 roadmap we will be implementing a _jackpot_ feature where rolls could be eligble for a bonus payout.

## Fairness

Roll results are provided by [chainlink VRF]() providers. This ensures a fair and tamperproof way of deciding results.

## Calculations

The following calculations and parameters are applied to the game.

**Protocol fee**: An amount of the total wager added to the protocol owned liquidity

**Revenue fee**: An amount of the total wager distributed to XTC stakers

**Odds**: (wager - fees) * total selected outcome / sum all outcomes
