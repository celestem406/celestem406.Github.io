---
layout: post
title: Space Invader Game
description: 
summary: 
tags: 
---
Today, we started off by doing another game. Today’s game is called Space Invaders, which will basically be a set of circles  which will be 30 circles or 3 by 10 and there will be a box on the other side. So on the other side will be a square which will release squares that will eliminate the circles once the squares move upwards towards the game.

In the first file we started on, which was the intex html file we basically had to
The first thing we did was link up our style css file and our app.js file which is something that is really important and that is something that should be done first. The style css file should be liked with a link tag and the app.js file should be linked with a script tag. I will insert the example of these.
```
<link rel="stylesheet" href="styles.css"></link>
  <script src="app.js" charset="utf-8"></script>
```
Then we are adding the score, now to make the score visible we have to add an h3 tag which will display the score, then we have to add a span id result so it can display the score while we play. At the end it will look sort of like this
```
<h3>Score:<span id="result"></span></h3>
```
Lastly to get the grid we have to add divs which define a section of the file. We need 225 divs, which will make the grid 15x15. 

Next I worked on the style.css file which will be the styling for our grid so it will look like a grid.
The width and height of the grid will be 300px, and the width of the squares are 20 px so they will fix inside the grid. So then after, there will be 4 items: invader, shooter, ladder and boom. Then I gave them each a color, which looks like this.
```
.invader {
	background-color: purple;
	border-radius: 10px;
}
.shooter {
	background-color: blue;
}
.laser {
	background-color: yellow;
}
.boom {
	background-color: red;
```
Now that we have done that we can move onto our app.js file and start with a ‘DOMContentLoaded’ which is basically the exterior of all the code which will go inside it. Here we will be using queryselector which is used to return the element that matches inside the document. These are the first three lines of code. Then, we will be telling the javascript what we want and where we want it. The first line will be telling the javascript that we want the width of the grid to be 15, and the second one is that we want the shooter to start at 202 which is the starting point and then the invaders to start at 0.
```const resultsDisplay = document.querySelector('#results')
let width = 15
let currentShooterIndex = 202
let currentInvaderIndex = 0
let results = 0
let direction = 1
let invadersId
```
So then now we define the alien invaders, which will basically put them into like the place they are supposed to be.
```
const alienInvaders = [
  0,1,2,3,4,5,6,7,8,9,
  15,16,17,18,19,20,21,22,23,24,
  30,31,32,33,34,35,36,37,38,39
```
So now we check the grid and assign each item to a position. This is what the shooter in the game looks like. 
```
squares[currentShooterIndex].classList.add('shooter')
```
So, after this we write a function that will be based on a loop, which we will put on a time loop. If we don’t do this the aliens in the game will just go through.
```
//move the alien invaders
function moveInvaders() {
  const leftEdge = alienInvaders[0] % width === 0 
  const rightEdge = alienInvaders[alienInvaders.length -1] % width === width -1
 ```
Later, when i tried to check if the game worked, I went to the developer and it told me that ‘move invaders’ wasn’t defined as well as ‘alien invaders’ I tried looking through the code, and I switched some things and it wouldn't work. So, Kajari said that when we encountered a problem to keep working and that is when I started working on the post. 
