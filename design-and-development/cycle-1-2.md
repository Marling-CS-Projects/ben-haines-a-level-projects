# 2.2.3 Cycle 3

## Design

### Objectives

In this cycle I aim to create a better level, meaning I would like to add more platforms, a background and an ending point for at least one level.

* [x] Add more floors and platforms to the level
* [x] Add a Background
* [x] Add a way to end the level

### Usability Features

* No new usability features.

### Key Variables

| Variable Name | Use                                                              |
| ------------- | ---------------------------------------------------------------- |
|               |                                                                  |
| Solid         | Makes an object solid so that the player cannot fall through it. |
| Add           | Adds whatever into the levels.                                   |

### Pseudocode

```
const LEVELS = [
  [
    "                     PP                         ",
    "    PP                            PP            ",
    "                                              E ",
    "GGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGG",
    ]
    
  "G": () => [
    sprite("ground"),
    area(),
    solid(),
    "ground"
  ],
  "P": () => [
    sprite("Platform"),
    area(),
    solid(),
    "Platform"
  ],
  "E": () => [
    sprite("End"),
    area(),
    solid(),
    "End"
  ],
  
  Player.collides(End) {
    Player.freeze
    nextLevel
  }
```

## Development

### Outcome

I have made an easier way to create my levels by assigning each feature a character that i can input into the 'Levels' constant to more quickly change and create levels.

I've added a way to end the level - similarly to Mario, when the player collides with a certain sprite (castle in Mario) the level will end and will progress the player to the next level.

### Challenges

I found it quite difficult to get the actual level to end - it keeps coming up with a "player has already been declared" error.

The player.Freeze function would not work despite it being declared.

The new way of making levels, while making it easier, is still messy and takes up around 300 lines per level. I will try and add it to a different file to keep my code readable and understandable.&#x20;

## Testing

Evidence for testing

### Tests

| Test | Instructions                                                           | What I expect                                                                              | What actually happens                                                                                                        | Pass/Fail |
| ---- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | <p>Preliminary Test</p><p>Run code - make sure it still works fine</p> | Player and Platform to spawn in, and the player does not fall through it.                  | The Player and Platform Spawned as expected. The player did not fall through.                                                | Pass      |
| 2    | Run new code with Levels const                                         | Platforms to be added to the level.                                                        | The platforms were  added to the level.                                                                                      | Pass      |
| 3    | Add end point and run code.                                            | When the player collides with the end point the level ends and progresses to the next one. | It worked fine (as far as i could tell) but I only have one level at the moment so it returns the player to the home screen. | Pass      |

### Evidence

```
const LEVELS = [
  [
    " BB                  pp                         ",
    "  pp                             pp             ",
    "                                           CC   ",
    "GGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGG",
    ]
    
  "G": () => [
    sprite("ground"),
    area(),
    solid(),
    origin("bot"),
    "ground"
  ],
  "p": () => [
    sprite("platform"),
    area(),
    solid(),
    origin("bot"),
    "platform"
  ], 
  "C": () => [
    sprite("CashBarrel"),
    area(),
    solid(),
    origin("bot"),
    "CashBarrel"
  ], 
  "B": () => [
    sprite("Background"),
    area(),
    solid(),
    origin("bot"),
    "Background"
  ],     
  
  
  
  
  Walt.onCollide("CashBarrel", (CashBarrel) => {
    destroy(CashBarrel);
    score.value += 11000000
    score.text = "$" + score.value
    wait(1, () => {
      let nextLevel = levelNumber + 1;
      if (nextLevel >= LEVELS.length) {
        go("start");
      } else {
        go("game", nextLevel);
      }
    })
  });
```
