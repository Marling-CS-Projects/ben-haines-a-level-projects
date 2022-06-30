# 2.2.3 Cycle 3

## Design

### Objectives

In this cycle I aim to create a better level, meaning I would like to add more platforms, a background and an ending point for at least one level.&#x20;

* [x] Add more floors and platforms to the level
* [x] Add a Background
*
* [x] Add a way to end the level&#x20;

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

I can now add platforms into my level that my player can walk on and not fall through. However for me to create a full level using the add command will result in to much code, so I need to set up a constant of 'levels' and assign the platforms a character that I can input into the 'levels'.

### Challenges

I found it quite difficult to get the actual level to end - it keeps coming up with a "player has already been declared" error.

The player.Freeze function would not work despite it being declared.

## Testing

Evidence for testing

### Tests

| Test | Instructions                   | What I expect                                                             | What actually happens                                                         | Pass/Fail |
| ---- | ------------------------------ | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | --------- |
| 1    | Run code                       | Player and Platform to spawn in, and the player does not fall through it. | The Player and Platform Spawned as expected. The player did not fall through. | Pass      |
| 2    | Run new code with Levels const | Platform to be added to the level.                                        | The platform was added to the level.                                          | Pass      |

### Evidence

```
// Some code
```
