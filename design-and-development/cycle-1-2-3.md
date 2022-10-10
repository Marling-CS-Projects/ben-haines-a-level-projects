# 2.2.6 Cycle 6

## Design

### Objectives

I aim to make the enemy kill the player upon colliding with them, and after the player has died display a you lose screen + stop the level.

* [x] Level stops when the player collides with an enemy
* [ ] Player Dies on collision with the enemy.
* [x] Display a you lose screen.

### Usability Features

* No new usability features.

### Key Variables

| Variable Name | Use                                                  |
| ------------- | ---------------------------------------------------- |
| .onCollide    |  if the thing specified collides with something else |

### Pseudocode

{% code lineNumbers="true" %}
```
Walt.onCollide("Enemy", (Enemy) => {
Walt.die
});
```
{% endcode %}

## Development

### Outcome

I've managed to make it so that when the player collides with the enemy the level will stop and display a 'Game Over' Screen, i have not, however, been able to make the player actually die upon colliding. Having the player actually die, though, would be somewhat redundant as the level stops anyway so it isn't that much of an issue.

### Challenges

I haven't managed to make the character die upon colliding as of yet, as '.die' is not necessarily a part of the Kaboom.js library and I need to create a 'killed' function, again this isnt necessarily important as the level just ends but i would like to add it at some point&#x20;

## Testing

### Tests

| Test | Instructions                                  | What I expect                                | What actually happens                      | Pass/Fail |
| ---- | --------------------------------------------- | -------------------------------------------- | ------------------------------------------ | --------- |
| 1    | Run Code                                      | Player to 'die' on colliding with the enemy  | Error message 'Walt.die' is not a function | Fail      |
| 2    | Run New Code                                  | Player to 'die' on colliding with the enemy  | Error message 'Walt.die' is not a function | Fail      |
| 3    | Run Code with scene code and no die function  |                                              |                                            | Fail      |
|      |                                               |                                              |                                            | Pass      |

### Evidence

{% code lineNumbers="true" %}
```
Walt.collides("Enemy", (Enemy) => {
    go("lose")
  });
```
{% endcode %}

<figure><img src="../.gitbook/assets/image (2) (2).png" alt=""><figcaption><p>The Death Screen</p></figcaption></figure>
