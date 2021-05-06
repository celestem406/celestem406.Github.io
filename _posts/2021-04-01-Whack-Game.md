---
layout: post
title: Whack a Mole Game 
description: 
summary: 
tags:
---
Today, I worked on typing club for about 30 minutes, then I sent my progress to Kajari. Then, we worked on a game which was a game where we had a specific amount of time to whack the mole. So, I followed the tutorial on youtube. [This is the youtube tutorial]  (https://www.youtube.com/watch?v=lhNdUVh3qCc) Then, I finished the game and I talked with Kajari through some specific parts of the game code. 
The first snippet we talked about was:
```
// in here it moves the mole frequently, and it moves the mole every 500 milliseconds?
function moveMole() {
  let timerId = null
  timerId = setInterval(randomSquare, 500)
}
moveMole()
``` 
 In this specific part of the code, its calling the function 'Random square' every 500 seconds or 1,000 milliseconds which moves the mole. 

```
square.forEach(id => {
  id.addEventListener('mouseup', () => {
    if(id.id === hitPosition){
      result = result + 1
      score.textContent = result
      hitPosition=null
    }
  })
})
``` 

In this part of the code, it is going through every square as it gives the square a specific id. Then, it checks if the square has been clicked on, on the third line if the square has been clicked on both the hitPosition and the id of the square have to be the same. Which, adds a point to the score. Then, it clears out the variable which is called hitPosition.

``` 
 if(currentTime === 0 ) {
    clearInterval(timerId)
    alert('GAME OVER! Your final score is' + result)
  }
  ```
  In this part of the code, we can see that that it basically times 60 seconds. When the time is about to end, if it is 0, it clears out the timerId variable. Then, it sends the pop up that the game is over.

``` 
square.forEach(className => {
    className.classList.remove('mole')
  })
  ```
  In this part it is removing the class called 'mole' from each of the square. 
  ```
  let randomPosition = square[Math.floor(Math.random() * 9)]
  randomPosition.classList.add('mole')
  ```
  In this part it is using math random position so that it could multiply by 9 which is the number of squares.
  
  In the end, I actually changed the speed of how long the mole would appear on each of the individual squares. On the tutorial, that I followed, it was originally 500 milliseconds so I decided to change the number to 750. The reason for this was because 500 was fast so by increasing the number it gave us a bit more time.
  [This is the final result of this game!](https://celestem406.github.io/Whack-a-mole/)