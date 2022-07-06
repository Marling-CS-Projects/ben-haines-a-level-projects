# 2.2.4 Cycle 4

## Design

### Objectives

In this cycle i aim to have the camera move with the player both along the y and x axis.

* [x] Have the camera move with the player along the X axis &#x20;
* [x] Have the camera move with the player along the Y axis&#x20;

### Usability Features

* No new usability features.

### Key Variables

| Variable Name                | Use                                             |
| ---------------------------- | ----------------------------------------------- |
| camPos()                     | sets the camera position using coordinates      |
| player.pos.y or player.pos.x | The x and y position of the player in the game  |
|                              |                                                 |

### Pseudocode

```
Player => {

   Var Camera = camPos()
   
    if(Camera.y > player.pos.x){
       camPos(Camera.x, player.pos.y)
    } 
    
    if(Camera.y > player.pos.y){
       camPos(Camera.x, player.pos.y)
    } 
    
    
```

## Development

### Outcome





### Challenges

It took me a while to figure out the logistics of how I wanted the camera to move, eventually i landed on the code shown above however this was relatively 'framey'

&#x20;

## Testing



### Tests

| Test | Instructions | What I expect | What actually happens | Pass/Fail |
| ---- | ------------ | ------------- | --------------------- | --------- |
| 1    |              |               |                       | Pass      |
| 2    |              |               |                       | Pass      |
| 3    |              |               |                       | Pass      |

### Evidence

```
```
