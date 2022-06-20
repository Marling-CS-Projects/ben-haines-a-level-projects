# 2.2.2 Cycle 2

## Design

### Objectives

In this cycle I aim to create the building blocks for my level by adding solid platforms that the player can traverse, and set up an easier way to build levels.

* [x] Add a floor and platforms to the level
* [x] Set up a better way of making levels&#x20;

### Usability Features

* No new usability features.

### Key Variables

| Variable Name | Use                                                              |
| ------------- | ---------------------------------------------------------------- |
|               |                                                                  |
| Solid         | Makes an object solid so that the player cannot fall through it. |

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

| Test | Instructions  | What I expect       | What actually happens                                                                                        | Pass/Fail |
| ---- | ------------- | ------------------- | ------------------------------------------------------------------------------------------------------------ | --------- |
| 1    | Run code      | Player to spawn In  | The Player Spawned as expected.                                                                              | Pass      |
| 2    | Press buttons | Player to move      | The player does move in both directions and jumps but the sprite  does not flip (this is not too big a deal) | Pass      |

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
