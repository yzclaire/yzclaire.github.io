---
title: "Optimization Project- Basketball Players Draw"
categories:
  - Blog
tags:
  - Post Formats
  - notice
---


# NBA_Front_Office_Optimization
Optimizing basketball team performance under a salary cap

## Project Link

## Project Goal
Optimize NBA salary cap allocation for a NBA franchise to maximize team performance (winning games) subject to budget constraints imposed by the salary cap.

## Background: 
NBA teams have one goal. They want to win a championship. In order to do that, they want to build the best team by picking the combination of players that increases their odds of winning. They’re constrained by a salary cap which places a limit on the total amount of money they can pay the players on their team. The other team building constraint is each roster must contain at least one player of each of the five main positions (point guard, shooting guard, small forward, power forward, and center). 

Chances of winnings is a variable that we concern. For people who are familar with NBA games probably know, there exists player statistics such as [win shares(WS)](https://www.basketball-reference.com/about/ws.html), [Box Plus/Minus (BPM)](https://www.basketball-reference.com/about/bpm2.html), and [value over replacement player (VORP)](https://www.basketball-reference.com/about/bpm2.html), are performance scores calculated based on each player's contribution to past games. We are going to see if there is correlation between chances of winings with these player statistics. If yes, we can use players' prior/historical stats as a presenation/expectation of chances of winnings.


## Project plan:
- Problem to solve: Pick NBA players to build a team 
- Objective:  Maximize chances of winnings 
- Constraints:
  * Salary cap : $102M 
  * Roster size : min 8, max 17 
  * Position : at least one player for each of the 5 positions (PG, SG, SF, PF, C)

## Interest Findings:
- The top 3 players in Win Shares showed up frequently in our optimal lineups (Giannis, Rudy G, Harden)
    * Giannis and Harden were the top 2 MVP vote getters as well
- Our models tended to pick a few super stars(expensive players) and supplement the roster with unknown(less expensive) players
- The Win Share based models leaned towards picking more center-position players while our second model incorporating all 3 statistics picked a more positionally-balanced roster
- The Free Agent model picked the top 4 available free agents in Win Shares


## Data sources: 
Player salary data: https://www.basketball-reference.com/contracts/players.html 

Player performance data: https://www.basketball-reference.com/leagues/NBA_2019_advanced.html



