# 2.2.7 Cycle 7

## Design

### Objectives

In this cycle I aim to add another form of obstacle to my level, this time adding a static one instead of a moving one like the enemy.&#x20;

* [x] &#x20;Add another type of obstacle

### Usability Features

* No new usability features.

### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |

### Pseudocode

{% code lineNumbers="true" %}
```
-- (Adding the sprite into the level the same way as in cycle 3) -- 

player.onCollide("obstacle") {
   go("lose")
}

```
{% endcode %}

## Development

### Outcome

This cycle wasn't too difficult because it was essentially the same code as enemies - just removing the patrol function. However because of how you add sprites and how you use the '.onCollide' function I had a small problem&#x20;

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

### Challenges

Again this cycle wasn't too difficult as I was just reusing older code

&#x20;

## Testing



### Tests

| Test | Instructions | What I expect                                        | What actually happens | Pass/Fail |
| ---- | ------------ | ---------------------------------------------------- | --------------------- | --------- |
| 1    | Run Code     | The player to die on colliding with the water block  | What was expected     | Pass      |

### Evidence

{% code lineNumbers="true" %}
```
  Walt.collides("WaterL", (WaterL) => {
    go("lose")
  });

  Walt.collides("WaterR", (WaterR) => {
    go("lose")
  });

  Walt.collides("WaterM", (WaterM) => {
    go("lose")
  });


```
{% endcode %}

<figure><img src="../.gitbook/assets/image (1) (3).png" alt=""><figcaption></figcaption></figure>
