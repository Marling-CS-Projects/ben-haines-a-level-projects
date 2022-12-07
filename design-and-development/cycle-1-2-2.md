# 2.2.5 Cycle 5

## Design

### Objectives

Add enemies to the level, make sure they kill the player on collide and have a small patrol distance.

* [x] Add Enemies&#x20;
* [x] Make the Enemies patrol left to right
* [x] Make the player die on the collision with the Enemy&#x20;

### Usability Features

* No new usability features.

### Key Variables

| Variable Name | Use                                                          |
| ------------- | ------------------------------------------------------------ |
| .pos          | The X and Y coordinates of whatever thing you put before it  |
| .startingPos  | The X and Y coordinates of the starting position             |
| Distance      | How far the enemy will roam from the starting position       |

### Pseudocode

{% code lineNumbers="true" %}
```
  --(I will add enemies to the level with the method shown in cycle 3)--
  --(V this is just to get the enemies moving V)--
  
  function patrol(distance = 1000, speed = 200, dir = 1) {
    starting.pos() = enemy.pos()
    this.on(go.game){
       enemy.move(500)
       dir = -dir
       enemy.move(500)
```
{% endcode %}

## Development

### Outcome

The Enemy moved left and right a set distance when the game started as intended.

### Challenges

It took quite a while to get from the pseudocode to the code I used in the game, I wasn't sure at all where to start so it took a while to get the code working.

I still cant get the enemy sprites to 'flip' upon changing direction, although it doesn't matter too much I would still like to, at some point, add this in to make the game look better.

&#x20;

## Testing



### Tests

| Test | Instructions  | What I expect                                                    | What actually happens                                                                                           | Pass/Fail |
| ---- | ------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Run Code      | To see the enemy sprites in the level but not doing anything yet | The enemy sprites are in the level                                                                              | Pass      |
| 2    | Run Code      | the enemy moving left and right on a loop                        | Error message   ".Pos not defined" this is probably a problem with the line of code before rather than the .Pos | Fail      |
| 3    | Run Code      | the enemy moving left and right on a loop                        | The enemy moves left then right but then stops. I just need to loop it.                                         | Fail      |
| 4    | Run Code      | the enemy moving left and right on a loop                        | Error message.                                                                                                  | Fail      |
| 5    | Run New Code  | the enemy spawns in ,the enemy moving left and right on a loop   | Worked as expected                                                                                              | Pa        |
|      |               |                                                                  |                                                                                                                 | Pass      |

### Evidence

<pre data-line-numbers><code><strong>function patrol(distance = 1000, speed = 200, dir = 1) {
</strong><strong>  return {
</strong><strong>    id: "patrol",
</strong><strong>    require: ["pos", "area",],
</strong><strong>    startingPos: vec2(0, 0),
</strong><strong>    add() {
</strong><strong>      this.startingPos = this.pos;
</strong><strong>      this.on("collide", (obj, side) => {
</strong><strong>        if (side === "left" || side === "right") {
</strong><strong>          dir = -dir;
</strong><strong>        }
</strong><strong>      });
</strong><strong>    },
</strong><strong>    update() {
</strong><strong>      if (Math.abs(this.pos.x - this.startingPos.x) >= distance) {
</strong><strong>        dir = -dir;
</strong><strong>      }
</strong><strong>      this.move(speed * dir, 0);
</strong><strong>    },
</strong><strong>  };
</strong>};

</code></pre>

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>
