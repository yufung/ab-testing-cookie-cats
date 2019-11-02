# A/B Testing - Cookie Cats
Mobile Games A/B Testing with Cookie Cats

## Problem Statement
Cookie Cats is a hugely popular mobile puzzle game developed by Tactile Entertainment. It is a classic "connect three" style puzzle game where the player must connect tiles of the same color in order to clear the board and win the level. As players progress through the game they will encounter gates that force them to wait some time before they can progress or make an in-app purchase. In this project, we will analyze the result of an A/B test where the first gate in Cookie Cats was moved from level 30 to level 40. In particular, we will analyze the impact on player retention.

## Data Dictionary
Feature|Type|Description
---|---|---
**userid**|_id_|A unique number that identifies each player.
**version**|_string_|Whether the player was put in the control group (gate_30 - a gate at level 30) or the group with the moved gate (gate_40 - a gate at level 40).
**sum_gamerounds**|_integer_|The number of game rounds played by the player during the first 14 days after install.
**retention_1**|_boolean_|Did the player come back and play 1 day after installing?
**retention_7**|_boolean_|Did the player come back and play 7 days after installing?

## Results
### 1-day retention

- There was a slight decrease in 1-day retention when the gate was moved from level 30 (44.8%) to level 40 (44.2%).
- However, according to our chi-squared test, there was no significant difference in retention rates between the two versions at the 5% significance level. We do not have enough evidence to reject our null hypothesis that retention rate is the same for the two versions.
- From our bayesian analysis, the probability that 1-day retention is greater when the gate is at level 30 is 96.7%.

### 7-day retention

- There was also a slight decrease in 7-day retention when the gate was moved from level 30 (19.0%) to level 40 (18.2%).
- According to our chi-squared test, there was a significant difference in retention rates at the 1% significance level. We reject our null hypothesis and accept our alternative hypothesis that 7-day retention rate is higher when the gate is at level 30.
- From our bayesian analysis, the probability that 7-day retention is greater when the gate is at level 30 is 100%.

## Conclusion and Recommendations
- There is strong evidence that 7-day retention is higher when the first gate is at level 30 than when it is at level 40. We should not move the gate from level 30 to level 40.
- Close to 4,000 players (4.4%) did not play a single round after installation and more than 20,000 players (23%) played five rounds or less. We can try to collect player feedback, for example, through an in-app survey.
