# Summary

Simple collision detection library for 2D games.

## Features

As first implementation is mainly used for simple 2D games based in terminal, the core features are:

- collision detection between shape and point
- collision detection between two shapes
- collision detection between two points

## How to use

Each collidable shape should implement the `Collidable` trait, which has a method `get_border` indicating the border of the shape.

```rust
struct Point {
    x: f64,
    y: f64,
}

impl Collidable for Point {
    fn get_border(&self) -> Border {
        Border::Point(self.x, self.y)
    }
}
```

Then when you want to check if two shapes collide, you can use the check_collisions function returning a boolean value if the collidables collide.

```rust
let point = Point { x: 0.0, y: 0.0 };
let point2 = Point { x: 1.0, y: 1.0 };

// in this case returns false
let collision = check_collisions(&point, &point2);
```
