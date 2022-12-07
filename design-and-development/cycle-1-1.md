# 2.2.2 Cycle 2

## Design

### Objectives

In this cycle I aim to create the building blocks for my level by adding solid platforms that the player can traverse, and set up an easier way to build levels.

* [x] Add a floor and platforms to the level
* [x] Set up a better way of making levels

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
add( 'Platform' {
      Solid()
      Area()
      Scale()
      Pos(10,10)
      }
)
```

## Development

### Outcome

I can now add platforms into my level that my player can walk on and not fall through. However for me to create a full level using the add command will result in to much code, so I need to set up a constant of 'levels' and assign the platforms a character that I can input into the 'levels'.

### Challenges

Due to the simplicity of Kaboom.js there wasn't much of a challenge to making the levels.

## Testing

Evidence for testing

### Tests

| Test | Instructions                   | What I expect                                                             | What actually happens                                                         | Pass/Fail |
| ---- | ------------------------------ | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | --------- |
| 1    | Run code                       | Player and Platform to spawn in, and the player does not fall through it. | The Player and Platform Spawned as expected. The player did not fall through. | Pass      |
| 2    | Run new code with Levels const | Platform to be added to the level.                                        | The platform was added to the level.                                          | Pass      |

### Evidence

![](<../.gitbook/assets/image (6).png>)

{% tabs %}
{% tab title="First Tab" %}
```
const LEVELS = [
  [
    "                                                ",
    "                                                ",
    "                                                ",
    "GGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGG",
    ]
    
      "G": () => [
    sprite("ground"),
    area(),
    solid(),
    origin("bot"),
    "ground"
  ],
```
{% endtab %}
{% endtabs %}
