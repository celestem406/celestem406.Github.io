---
layout: post
title: Tetra Game
description: 
summary: 
tags: 
---
Today, we worked on the last and final game on the youtube video. This is the reference of the youtube video, [this is the video we have been using](https://www.youtube.com/watch?v=lhNdUVh3qCc&t=4509s)

First I started out adding all the folders that we needed on terminal, then I followed her tutorial, and I downloaded all of the images that were on the ‘instruction” page. Make a separate folder for images and have them there ready and downloaded. So then you have to put the app.js into the js file and put the style.css into the css file, along with checking if the index.html file is there and working correctly. I then moved onto the writing of the code, while I followed the tutorial on youtube.

So, now to start with the code, I started with the index.htm file, and the main thing you want to add to this link the other files to here, basically what we have been doing the past weeks, it's a way for the computer to find the files and to check through them in a reference type way. 

On the javascript file, I added an ‘addEventListener’, then you have to choose the height and width of each individual square and each of the boards that we will be using. For the grid of the game I choose 10sq width and 20 height. So, now I went back into my html file and I had to add 200 ‘divs’ on the html file because one for each square. Then, on the app.js file, basically bring in tetrominos, and tetrominoes are basically the geometric shapes which are the ones we will be using today, and on the tutorial she placed them on a 4by4 so they can rotate and switch every time it drops down. There will be 5 tetrominoes, I will include one. 
```
//The Tetrominoes
  const lTetromino = [
    [1, GRID_WIDTH + 1, GRID_WIDTH * 2 + 1, 2],
    [GRID_WIDTH, GRID_WIDTH + 1, GRID_WIDTH + 2, GRID_WIDTH * 2 + 2],
    [1, GRID_WIDTH + 1, GRID_WIDTH * 2 + 1, GRID_WIDTH * 2],
    [GRID_WIDTH, GRID_WIDTH * 2, GRID_WIDTH * 2 + 1, GRID_WIDTH * 2 + 2]
  ]
```
So now she mentions something about a draw function and an undraw function, which is code. For the undrawn function it basically gets rid of the class name functions from the 200 divs that I wrote before. I will show example of the undraw function
```
//undraw the shape
  function undraw() {
    current.forEach(index => {
      squares[currentPosition + index].classList.remove('block')
      squares[currentPosition + index].style.backgroundImage = 'none'
   ```
Now, to stop the tetromino from moving further, to make it stop, I wrote this code to basically stop the tetromino from moving when it reaches the bottom of the grid. Then, to make the tetromino move left and right there has to be a code which for example, if the squares go into a div containing block too, then it should move left. There are 2 codes, one for left and one for right, I will input the left one here. Then, add a code to make sure that the tetromino will rotate, which I will include with the example of the left code. 
```
//move left and prevent collisions with shapes moving left
  function moveright() {
    undraw()
    const isAtRightEdge = current.some(index => (currentPosition + index) % width === width - 1)
    if (!isAtRightEdge) currentPosition += 1
    if (current.some(index => squares[currentPosition + index].classList.contains('block2'))) {
      currentPosition -= 1
    }
    draw()
//Rotate the Tetromino
  function rotate() {
    undraw()
    currentRotation++
    if (currentRotation === current.length) {
      currentRotation = 0
    }
    current = theTetrominoes[random][currentRotation]
    draw()
  }
```
Then, on the same file, on the app.js file, I had trouble with this part which is why I am including it, write a code to show previous other tetrominoes. This will be the part on the side which will show the coming tetrominos that will drop in the game. Then write the function display shape.
```
//show previous tetromino in scoreDisplay
  const displayWidth = 4
  const displaySquares = document.querySelectorAll('.previous-grid div')
  let displayIndex = 0

  const smallTetrominoes = [
    [1, displayWidth + 1, displayWidth * 2 + 1, 2], /* lTetromino */
    [0, displayWidth, displayWidth + 1, displayWidth * 2 + 1], /* zTetromino */
    [1, displayWidth, displayWidth + 1, displayWidth + 2], /* tTetromino */
    [0, 1, displayWidth, displayWidth + 1], /* oTetromino */
    [1, displayWidth + 1, displayWidth * 2 + 1, displayWidth * 3 + 1] /* iTetromino */
```
Now on the html page to show the score which will be helpful, you have to create a code which will go in the index.html file and will go before all of the divs that have been put, this will be done wil H1 tags. Then, make a code to let the computer know that the game is over.
```
 //Game Over
  function gameOver() {
    if (current.some(index => squares[currentPosition + index].classList.contains('block2'))) {
      scoreDisplay.innerHTML = 'end'
      clearInterval(timerId)
  ```
[This is what the final game looks like!](https://celestem406.github.io/Tetris-tutorial/) 

