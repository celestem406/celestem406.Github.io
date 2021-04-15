---
layout: post
title: Creating Connect four Game
description: 
summary: 
tags:
---
As usual today I did  typing club for a bit and then I asked Kajari about a problem I noticed on my github page a couple weeks ago. The problem was that I messed up the dates, so I will have to create a pr for it and push the changes up.

This week we worked on game 3. The game was connect 4, and we followed the same youtube tutorial we have been following for the past 3 weeks. [This is the youtube tutorial we have been following]  (https://www.youtube.com/watch?v=lhNdUVh3qCc) . So for this game as usual we had to have 3 files. 

 In the html file, we were creating the 7 by 6 grid that will be the connect 4 game. I will be creating the grid with the term ‘<div>’ which basically defines the section that we are using.  In this file, we also added a code that will determine who wins the game, and with this code the game will show us who won. The code ‘<div>’ so they can become a square. Then the colors for player one and player 2 are chosen. Player one is red and player 2 is blue. The follwing code will be placed twice because we want player one to be one color and player 2 to be another color.
```
.player-one {
  background-color: yellow;
  border-radius: 10px;
  ```
In our style.css file we are going to style the game and basically create how tall, and what the game will look like. So when we added div’s in the html file they basically connect to the styling of the game as the grid will be inside the boundaries.

In the app.js file we are writing all our javascript code. 
First I added a ‘DOMContentLoaded’ this is basically like a jar, and when we write code on this file it will all be done inside. Then I will list out and this will be for every time we click a square, and this will be done with a loop. After this, we will be writing if statements that will align with the game. Then we will write a code which basically informs the player that you cant go there, which just means to choose a different spot on the grid.
```
} else alert('cant go here')
      checkBoard()
```
Then, we have to create a function that basically allows the computer to check wether something is right or wrong. So these are the winning arrays that will be checked to see if the player actually won and has 4 dots connected.
```
const winningArrays = [
    [0, 1, 2, 3],
    [41, 40, 39, 38],
    [7, 8, 9, 10],
    [34, 33, 32, 31],
    [14, 15, 16, 17],
    [27, 26, 25, 24],
    [21, 22, 23, 24],
    [20, 19, 18, 17],
    [28, 29, 30, 31],
    [13, 12, 11, 10],
    [35, 36, 37, 38],
    [6, 5, 4, 3],
    [0, 7, 14, 21],
    [41, 34, 27, 20],
    [1, 8, 15, 22],
    [40, 33, 26, 19],
    [2, 9, 16, 23],
    [39, 32, 25, 18],
    [3, 10, 17, 24],
    [38, 31, 24, 17],
    [4, 11, 18, 25],
    [37, 30, 23, 16],
    [5, 12, 19, 26],
    [36, 29, 22, 15],
    [6, 13, 20, 27],
    [35, 28, 21, 14],
    [0, 8, 16, 24],
    [41, 33, 25, 17],
    [7, 15, 23, 31],
    [34, 26, 18, 10],
    [14, 22, 30, 38],
    [27, 19, 11, 3],
    [35, 29, 23, 17],
    [6, 12, 18, 24],
    [28, 22, 16, 10],
    [13, 19, 25, 31],
    [21, 15, 9, 3],
    [20, 26, 32, 38],
    [36, 30, 24, 18],
    [5, 11, 17, 23],
    [37, 31, 25, 19],
    [4, 10, 16, 22],
    [2, 10, 18, 26],
    [39, 31, 23, 15],
    [1, 9, 17, 25],
    [40, 32, 24, 16],
    [9, 17, 25, 33],
    [8, 16, 24, 32],
    [11, 17, 23, 29],
    [12, 18, 24, 30],
    [1, 2, 3, 4],
    [5, 4, 3, 2],
    [8, 9, 10, 11],
    [12, 11, 10, 9],
    [15, 16, 17, 18],
    [19, 18, 17, 16],
    [22, 23, 24, 25],
    [26, 25, 24, 23],
    [29, 30, 31, 32],
    [33, 32, 31, 30],
    [36, 37, 38, 39],
    [40, 39, 38, 37],
    [7, 14, 21, 28],
    [8, 15, 22, 29],
    [9, 16, 23, 30],
    [10, 17, 24, 31],
    [11, 18, 25, 32],
    [12, 19, 26, 33],
    [13, 20, 27, 34],
  ]
  ```
Overall, this game was really interesting to see how we could change the colors of the players, the overall style of the game and how the grid was created.