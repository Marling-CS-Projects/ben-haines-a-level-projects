# 2.2.1 Cycle 1

## Design

### Objectives

In this cycle I aim to create the basic mechanics for my game in Kaboom.js. I have made some basic sprites and I would like to be able to make my player sprite move, jump and fall due to gravity. For them to be able to move around I need to add a floor that stops the player falling straight through. If I can I would like to add a sprint feature in which the player moves at 2x speed.

* [x] Make the player sprite respond to Gravity
* [x] Add a floor that the player can't fall trough
* [x] Have the player be able to move right and left
* [ ] Have the player be able to sprint for a short burst

### Usability Features

* Controls - I will be using the standard controls for many PC games, WASD and SPACEBAR. A for left, D for right and SPACEBAR to jump. This is what most people are used to so it will be easy to pick up the controls.
* Sprites - By making my player and platforms look like a person and a floor. This helps people clearly understand who they control and what is part of the level.

### Key Variables

| Variable Name | Use                                                                        |
| ------------- | -------------------------------------------------------------------------- |
| Speed         | Determines the Speed of the player.                                        |
| .Grounded     | Determines whether or not the player is on the ground ready to jump again. |
| .Jump         | Determines the Height that the player will jump.                           |
| .Move         | Moves the player                                                           |
| Pos()         | Position                                                                   |

### Pseudocode

```
Spawn Player pos(100,100)


Speed = 100

onKeyPress('D')[
   player.move(Speed)
   ]
   
onKeyPress('A')[
   player.move(-Speed)
   ]
   
onKeyPress('space')[
   if player.grounded 
     player.jump
   ]
```

## Development

### Outcome

I now have the ability to move the player left and right and for the player to jump. The player will move at a predetermined speed and will fall after jumping.

### Challenges

Due to the simplicity of Kaboom.js there wasn't much of a challenge to making the character move

## Testing

Evidence for testing

### Tests

| Test | Instructions  | What I expect      | What actually happens                                                                                       | Pass/Fail |
| ---- | ------------- | ------------------ | ----------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Run code      | Player to spawn In | The Player Spawned as expected.                                                                             | Pass      |
| 2    | Press buttons | Player to move     | The player does move in both directions and jumps but the sprite does not flip (this is not too big a deal) | Pass      |

### Evidence

![](<../.gitbook/assets/image (6).png>)

{% tabs %}
{% tab title="First Tab" %}
```
  const SPEED = 500;

  keyDown("d", () => {
    if (Walt.isFrozen) return;
    Walt.flipX(false);    //flipx flips the sprite
    Walt.move(SPEED, 0);
  });
  
  keyDown("a", () => {
    if (Walt.isFrozen) return;
    Walt.flipX(true);
    if(toScreen(Walt.pos).x > 20) {
      Walt.move(-SPEED, 0);
    }
  });

  keyPress("space", () => {
   if (Walt.grounded()) {
      Walt.jump(1250)
    }
  });
```
{% endtab %}
{% endtabs %}
