---
layout: post
title:Frogger Game 
description: 
summary: 
tags:
---
In the morning, today Kajari approved our pull requests from last week. Then, we got to work on the Frogger game from this week. This week we worked on a frog game, it was really fun and the overall game is actually pretty challenging to complete. 
 
First thing we have to do is link the stylesheet with a link tag, and also link out javascript on the html file, which looks something like this for the stylesheet:
```
<link rel="stylesheet" href="style.css">
```
Then we do the grid, which is going to be based on “div”s, this is a short example of how the grid will be set up on sublime, I will include a small part, not the whole thing. The time will be added onto here, which is 20 seconds, it will be added in here because it is part of the ‘background’ of the game.
```
<h3> Seconds left: <span id="time-left">20</span></h3>
    <h3 id="result"></h3>

    <div class="game">
      <div class="grid">
       <div></div>
       <div></div>
       <div></div>
       <div></div>
       <div class="ending-block"></div>
       <div></div>
       <div></div>
       <div></div>
       <div></div>
       <div></div>
       <div></div>
```
So now in the style sheet, we just have to add the styling to the grid, which will show up as the grid in the game. Here we are using the div’s to wrap around each other and create a grid using flex-wrap. The pixels of 20x 20 because 180 divided by 9 is 20, so we get the height and width of each pixel.During this, you will also be adding colors to the squares which will be 5, they can be any colors.
```
.grid {
  border: 1px solid;
  display: flex;
  flex-wrap: wrap;
  height: 180px;
  width: 180px;
}

.grid div {
  height: 20px;
  width: 20px;
}

.ending-block {
```
Now, for the app.js file, as most of these past games, we have added a ‘addEventListener’ as well as a ‘ DOMContent Loaded’ this is helpful because all our code will be done in this sorta section and everything will fall under here. So the first part of this file is basically just defining everything that has and will be used, mostly using ‘querySelector’. Then, we will be giving the frog directions and we will be using the up and down arrows on the computer, to do this with key codes.For example, on the examples I will be using key 37 is left so, when you click next the computer will read the code and make the frog move left. After this, you shouldn't have an obstacle, so you will do it after the frog can mobilize. Then create a loop for the first obstacle which will be on a loop or 3 squares, and so the second obstacle will be 5 squares. 
```
 //move the Frog
  function moveFrog(e) {
    squares[currentIndex].classList.remove('frog')
    switch(e.keyCode) {
      case 37:
        if(currentIndex % width !== 0) currentIndex -= 1
        break
      case 38:
        if(currentIndex - width >= 0) currentIndex -= width
        break
      case 39:
        if(currentIndex % width < width - 1) currentIndex += 1
        break
      case 40:
        if (currentIndex + width < width * width) currentIndex += width
        break
    }
```
This is the code for the loop of the car which is going left and right.
```
//move the car left on a time loop
  function moveCarLeft(carLeft) {
    switch (true) {
      case carLeft.classList.contains('c1'):
      carLeft.classList.remove('c1')
      carLeft.classList.add('c2')
      break
      case carLeft.classList.contains('c2'):
      carLeft.classList.remove('c2')
      carLeft.classList.add('c3')
      break
      case carLeft.classList.contains('c3'):
      carLeft.classList.remove('c3')
      carLeft.classList.add('c1')
      break
    }
  }

  //move the car right on a time loop
  function moveCarRight(carRight) {
    switch (true) {
      case carRight.classList.contains('c1'):
      carRight.classList.remove('c1')
      carRight.classList.add('c3')
      break
      case carRight.classList.contains('c2'):
      carRight.classList.remove('c2')
      carRight.classList.add('c1')
      break
      case carRight.classList.contains('c3'):
      carRight.classList.remove('c3')
      carRight.classList.add('c2')
      break
    }
  }
```
Now, we have to write up rules to win the game in the code area, which will allow the computer to say ‘YOU WON!” Also, there will be a win section and a loose section wich will basically identify how the frog won and how he lost and it will determine if the code matches. This is an example of the win code.
```
//rules for frog to win
  function win() {
    if (squares[4].classList.contains('frog')) {
      result.innerHTML = 'You WON!'
      squares[currentIndex].classList.remove('frog')
      clearInterval(timerId)
      document.removeEventListener('keyup', moveFrog)
   ```
[This is the final product of the game!](https://celestem406.github.io/Frogger/) 