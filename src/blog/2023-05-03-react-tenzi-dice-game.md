---
title: React Tenzi Dice Game
description: >-
  This is a project, that was built following up "React Basics" module. I
  improved the course project by building new features and changing the design
  of the project.
author: Anna Veselova
repoName: react-tenzies-pj
date: 2023-05-02T19:58:46.928Z
tags:
  - post
  - featured
image: /assets/blog/tenzi-game.png
imageAlt: The image of the "React Tenzi Dice Game" project
---

Welcome to the project!

_**How did I build it?**_

I built it using npm create-react-app on VS Code and local server. The project has 2 components. All the functionality is happening inside the App component:

1. An array of dice objects is generated and their properties are passed to the Die component as props by mapping through the array.
2. rollDice function is created, which either returns new dice or keeps those dice, which isHeld property is a truthy value. It may start or finish the game, depending on tenzies state. If the game is over, it clears the roll counter and timer states.
3. holdDice function is created inside the App component, too. It's responsible for toggling die.isHeld property on dice click and changing the state of the dice array.

![null](/assets/blog/holddice.png)

4. In the useEffect I find out whether all dice are held or at least some of them. If all of them are held and have the same value, I finish the game by changing the start and tenzies states. I also change the results state by adding a new result object to the array of results.

The Die component takes props and conditionally renders a die and style it, depending on the props.value and props.isHeld. The holdDice prop function is passed to the component's onClick event.

_**Going above and beyond: **_

1. I added the timer and the roll counter to the project.

![null](/assets/blog/timer-tenzies.png)

2.  I created 2 useEffects to save the current and best results of the game in local storage. To calculate the best result I used the Array.reduce method.

![](/assets/blog/results-tenzies.png)

3. I set the game to start both on a "roll" button click and on a die click for a better UI.

4. I rendered the real dice instead of numbers by adding the number of spans with the "dot" class equal to the props.value.

5. In terms of styling I added some watermarks here and there and allocated a separate div for the results.
