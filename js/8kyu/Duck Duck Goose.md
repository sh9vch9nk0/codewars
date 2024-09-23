# Codewars JavaScript Solutions

## Duck Duck Goose

The objective of [Duck, duck, goose](https://en.wikipedia.org/wiki/Duck,_duck,_goose) is to walk in a circle, tapping on each player's head until one is chosen.

Task: Given an array of Player objects (an array of associative arrays in PHP) and an index (1-based), return the `name` of the chosen Player(`name` is a property of `Player` objects, e.g `Player.name`)

Example:

```
duck_duck_goose([a, b, c, d], 1) should return a.name
duck_duck_goose([a, b, c, d], 5) should return a.name
duck_duck_goose([a, b, c, d], 4) should return d.name
```

```
// PHP only
duck_duck_goose([$a, $b, $c, $d], 1); // => $a["name"]
duck_duck_goose([$a, $b, $c, $d], 5); // => $a["name"]
duck_duck_goose([$a, $b, $c, $d], 4); // => $d["name"]
```

### Solution

```
      function duckDuckGoose(players, goose) {
        let i = goose - 1;

        while (i >= players.length) {
          i -= players.length;
        }

        return players[i].name;
      }
```
