# Codewars JavaScript Solutions

## PatternCraft - Visitor (7kyu)

The [Visitor Design Pattern](https://www.youtube.com/watch?v=KSEyIXnknoY) can be used, for example, to determine how an attack deals a different amount of damage to a unit in the StarCraft game.

The pattern consists of delegating the responsibility to a different class.

When a unit takes damage it can tell the visitor what to do with itself.

### Your Task

Complete the code so that when a `Tank` attacks a `Marine` it takes `21` damage and when a `Tank` attacks a `Marauder` it takes `32` damage.

The Marine's initial health should be set to `100` and the Marauder's health should be set to `125`.

You have 3 classes:

- `Marine`: has a `health` property and `accept(visitor)` method
- `Marauder`: has a `health` property and `accept(visitor)` method
- `TankBullet`: the visitor class. Has `visitLight(unit)` and `visitArmored(unit)` methods

### Solution

```
class Marine {
  constructor() {
    this.health=100;
  }

  accept(visitor) {
  return visitor.visitLight(this);
  }
}

class Marauder {
  constructor() {
    this.health=125;
  }

  accept(visitor) {
   return visitor.visitArmored(this);
  }
}

class TankBullet {
  visitLight(unit) {
    return unit.health-=21;
  }

  visitArmored(unit) {
    return unit.health-=32;
  }
}
```
