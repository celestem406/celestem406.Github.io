---
layout: post
title: Moving Monsters 
description: 
summary: 
tags:
---
Today, we started off with typing club once again. Then, Kajari instructed us to work on our game that we have been working on for the past weeks. Today, we had to place both monsters on each side of the top of the canvas. We had to place monster one on the top left side whose coordinates are 0,0. The reason why the cordinates for the first monster is 0,0 is because the monster is on the top of the canvas width. Now, for monster number 2, the coordinates are 448,0. This is because the width stays the same while the height increases, because we want monster 2 to the right side of the canvas. Below I have included a sketch of what kajari provided for me as a reference.
```  
    y                                                                                   
x   0 -----------------------------------------------------------------------------------------canvas.width = 512                                                                 Monster(448,0)            |
    |                                                                                    |      |
    |                                                                                    |      |
    |                                                                                    |______|
    |                                                                                           |
    |                                                                                           |
    |                                                                                           |
    |                                                                                           |
    |                                              Hero(256,240)                                |
    |                                               _______                                     |
    |                                               |     |                                     |
    |                                               |     |                                     |
    |                                               |_____|                                     |
    |                                                                                           |
    |                                                                                           |
    |                                                                                           |
    |                                                                                           |
canvas.height = 480-----------------------------------------------------------------------------
```    
One setback I encountered was that to get the correct placement of the monsters I had to take away the width of the monster from the width of the whole canvas so the monster could be on the right side. This prevented the monster to get stuck in the white space to the right of the canvas.