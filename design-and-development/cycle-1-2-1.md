# 2.2.4 Cycle 4

## Design

### Objectives

In this cycle I aim to have the camera move with the player both along the y and x axis.

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

The camera moved with the player well enough however it didn't run perfectly. However after a little while I realized that my code was really convoluted and i could instead swap it for -

```
player.onUpdate(() => {
   cam.Pos(player.Pos)
});   
```

This is obviously a much simpler method of setting up the camera, it also runs much smoother making the game look and run better.

### Challenges

It took me a while to figure out the logistics of how I wanted the camera to move, eventually i landed on the code shown above however this was relatively 'framey' (basically didn't work smoothly).

&#x20;

## Testing



### Tests

| Test | Instructions              | What I expect                                                  | What actually happens                                                                                    | Pass/Fail |
| ---- | ------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Run code and move player. | The camera to move with the player left and Right .            | The camera moves left and right with the player as expected but it wasn't very smooth.                   | Pass      |
| 2    | Run code and move player. | The camera to move with the player up and down only.           | The camera moves up and down  with the player as expected but it wasn't very smooth.                     | Pass      |
| 3    | Run code and move.        | The camera to move smoothly in both axis                       | The camera was very jumpy and did not run smoothly at all. However did still somewhat follow the player. | Fail      |
| 4    | Run code and Move         | The camera to move smoothly in both axis                       | The camera moved in both axis without a huge amount of latency however it was a little bit 'Framey'      | Pass      |
| 5    | Run code and Move         | The camera to move smoothly in both axis with the simple code. | The camera moved smoothly in both axis                                                                   | Pass      |

### Evidence

```
player.onUpdate(() => {
   camera.Pos(player.Pos)
}); 
```
