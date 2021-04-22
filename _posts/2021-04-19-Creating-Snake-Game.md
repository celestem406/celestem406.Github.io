---
layout: post
title: Creating Snake Game 
description: 
summary: 
tags:
Today Kajari is on a trip to India! We have to continue doing the rest of the games, so we can finish the youtube video which has 7 games in total. Today I started with a snake game, and then I created a Repository for the snake game, and I added the link to the repository.The game, to work will use the arrow keys to move the snake around the border, trying to collect as much apples as possible, while also not trying to collide with itself. The more apples the snake eats, the longer and faster the snake becomes.

To start off I made a file on the finder and we added 3 folders in that file on the terminal. Then I watched the video which was [this is the youtube video]  (https://www.youtube.com/watch?v=lhNdUVh3qCc)  
For this game we also used the <div> code, this code basically defines a section in an html document. The div code was mostly used in the html file. The reason for this was to make the grid, we followed the tutorial and the grid ended up being 10 by 10 which makes the whole grid 100 squares. 
```
<div class='grid'>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
```
Now to actually make the grid look like a grid in the style sheet we have to add the desired height and width for the border. For both the height and width the pixels were 200 each. So now each of the individual divs in our grid from the html folder are going to be given a height and width. For both of the height and width the pixels given are 20px.
```.grid div {
  width: 20px;
  height: 20px;
}
```
Now we are going to give the snake and the apple colors. I gave the snake the color green and then I gave the apple the color purple. 
```
.snake {
  background-color: green;
}
```

Now in our app.js file all of our javascript code will be here. Just like another game we worked on, all of the code will be inside the ‘DOMContentLoaded’. The first 3 lines of the app.js file are there so the file can see them and can select them. In this file, we are able to “draw the snake”. The following code is basically to find the difference between the head of the snake and the end of the snake. All <div>’s that have a value of 2 will be the head and all <div>’s with the value of 0 will be the tail.
```
let currentIndex = 0 //so first div in our grid
  let appleIndex = 0 //so first div in our grid
  let currentSnake = [2,1,0] 
  let direction = 1
  let score = 0
  let speed = 0.9
  let intervalTime = 0
  let interval = 0
```
Then, we will write if statements, these if statements basically tell the computer what to do. Since we will be using the arrow keys we make if statements. For example if we press the right arrow on our keyboard,the snake will go right. 
```
direction = -width // if we press the up arrow, the snake will go back ten divs, appearing to go up
    } else if (e.keyCode === 37) {
``` 
