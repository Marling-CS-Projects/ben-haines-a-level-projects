# 2.2.9 Cycle 9

Design

### Objectives

My objective for this cycle is to add a simple and functional title screen to my game, I will start with a very bare bones 'Press \_\_\_\_\_\_ to start' screen that can be adapted in later cycles. This shouldn't prove to be too difficult as, like I said, this will be a very functional title screen made only to do its job.

* [x] &#x20;Add a title screen.

### Usability Features

* No new usability features.

### Key Variables

| Variable Name | Use                                               |
| ------------- | ------------------------------------------------- |
| Scene         |  Starts the game as something other than a level. |

### Pseudocode

{% code lineNumbers="true" %}
```
Start scene("Title Screen"){
  OnKeyPress('Enter') {
    go(GAME)
    };
  };
```
{% endcode %}

## Development

### Outcome

I have successfully managed to add a simple title screen to my game.

### Challenges

Overall i did not find this cycle too difficult and there were no real problems during development.

## Testing



### Tests

| Test | Instructions | What I expect                                              | What actually happens                  | Pass/Fail |
| ---- | ------------ | ---------------------------------------------------------- | -------------------------------------- | --------- |
| 1    | Run Code     | The game to run with a title screen.                       | The game ran with a title screen.      | Pass      |
| 2    | Run Code     | The rest of the game to start when the player press enter. | the game started when i pressed enter. | Fail      |

### Evidence

{% code lineNumbers="true" %}
```
scene("start", () => {
  
  add([
    sprite("TS"),
    pos(vec2(935, 448)),
    origin("center"),
    color(255, 255, 255),
    scale(7.7),
  ]);

  add([
    sprite("Title"),
    pos(vec2(950, 200)),
    origin("center"),
    color(255, 255, 255),
    scale(6),
  ]);

  add([
    sprite("Enter"),
    pos(vec2(1020, 450)),
    origin("center"),
    color(255, 255, 255),
    scale(4.5),
  ]);

  onKeyRelease("enter", () => {
    go("game");
  })
});
```
{% endcode %}

<figure><img src="../.gitbook/assets/Screenshot 2022-12-15 at 22.45.04.png" alt=""><figcaption></figcaption></figure>
