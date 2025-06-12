# Switchshop Pokémon full-stack challenge

Welcome to the Switchshop Pokémon full-stack challenge!

The aim of this code challenge is to test your full-stack capabilities in a fun, interesting way.

There's no time-limit on this task, and we won't be looking at git commits with time in mind. Everyone's busy, and we appreciate you taking the time to complete our task and fitting it around your other commitments.

The app is bootstrapped with the NextJS starter pack. At Switchshop we use Material UI as a component library and axios for data-fetching. You are free to use whichever packages or plugins you wish and not stick with MUI and axios if you have other preferences.

## Overview

There's been a huge Pokémon tournament and all the player details and battle results have been recorded.

We'd like you to build an application that performs some analysis on the Pokémon trainer battles and from there displays the analysis and battles in a leaderboard. This should then be displayed in the frontend. The layout and user-features are up to you the focus will be on the quality of data you pull out. This challenge is designed for you to show off and impress us with your execution, so have fun with it! Feel free to imagine your input data is much bigger and show off your ability to work with big data in your code.

### Assumptions about the input data
- 2 players per battle
- 6 Pokémon per battle
- When a player loses all their Pokémon they have lost the battle
- When a player forfeits a battle they have lost the battle

### CSV input schema

#### Players
```
ID: number
Name: string
pokemon1ID: number
pokemon2ID: number
pokemon3ID: number
pokemon4ID: number
pokemon5ID: number
pokemon6ID: number
```
#### Battles
```
ID: number
player1ID: number
player2ID: number
pokemonLostByPlayer1: number
pokemonLostByPlayer2: number
damageDealtByPlayer1: number
damageDealtByPlayer1: number
```
#### Forfeits
```
ID: number
battleID: number
playerID: number
```

### Notes
- You will need to use git for this challenge.
- Please commit only once for each step in the instructions.
- Do not bundle multiple steps in each commit.
- Please name each commit with the name of the appropriate stage, ie "Step 1".
- Please use Typescript for your solution.

## Instructions

### Preparing
Please do not create a public fork of this repo. This is to stop other applicants from seeing your solution. See how to share the repo with us at the end of the steps.

Clone this repo down to your local machine and run `npm install` to install the project dependencies. To start the dev server, run `npm run dev`

### Step 1
Please import your given CSV data files into an SQLite database. Please install and use [Prisma](https://www.prisma.io/), their [seeding guide is here](https://www.prisma.io/docs/orm/prisma-migrate/workflows/seeding) you can choose not to use the Prisma API and stick with raw SQL queries if you wish, both are used in the role.

### Step 2
Write some typescript code which pulls data from the database and is able to identify all the player IDs where the player won the battle. Keep a track of the total damage each player has done across their battles where they won.

What is the average amount of attributed damage per player? Put this in the commit message.

Edit the database schema and store the total damage each player has done where they have done damage in the database.

### Step 3
- In `/pages/api/api.js` create an endpoint that pulls the amount of damage done per player with Pokémon IDs from the database and serve it to the user. This will be used in Step 5.

### Step 4
- In `/pages/api/api.js` create an endpoint that pulls down the first 151 Pokémon from https://pokeapi.co/ and serves it to the user. This will also be used in the next step.

- The API returns more data for each Pokémon than we'd like. We're only interested in the 'name' and 'id' fields. Modify your endpoint to remove all other fields on each Pokémon and serve the reduced data to your frontend.

### Step 5
Create a leaderboard which shows players in order of damage done where they won from step 2. You should be able to click on a player and see the Pokémon they used.

Feel free to add any other data insights you can come up with.

## Submitting your work

To submit the challenge, either upload it to your Github in a private repo and provide us access (preferred) or zip up the project (minus the node modules) and return it back to us via email.

If you're following the GitHub route please give read access to: louisotto@switchshop.co.uk, matthewslater@switchshop.co.uk, and harrymenen@switchshop.co.uk
