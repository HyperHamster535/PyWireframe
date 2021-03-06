# Shapes

## What are they?
Shapes are functions that render a 3D object when executed.

## Executing a shape
To render a shape, just run the function with the desired parameters and it will render. Bear in mind that shapes do not re-render when the `refresh()` function is run. If you do want them to re-render, see [objects](https://pywireframe.readthedocs.io/Usage/Objects)

## Predefined Shapes
As of version 0.3, PyWireframe has three predefined shapes. They are `cube`, `pyramid3`, and `pyramid4`. All predefined shapes use the syntax `shape(x, y, z, size)`.

## Defining shapes
You can define your own shapes as well. When defining shapes, you create a function which contains a series of `line(x1, y1, z1, x2, y2, z2)` functions. These parameters should be coordinates relative to the shape's coordinates. Here's an example shape (a cube).

```python

def cube(x, y, z, size):
    line(x, y, z, x + size, y, z)
    line(x + size, y, z, x + size, y + size, z)
    line(x + size, y + size, z, x, y + size, z)
    line(x, y + size, z, x, y, z)

    line(x, y, z + size, x + size, y, z + size)
    line(x + size, y, z + size, x + size, y + size, z + size)
    line(x + size, y + size, z + size, x, y + size, z + size)
    line(x, y + size, z + size, x, y, z + size)

    line(x, y, z, x, y, z + size)
    line(x + size, y, z, x + size, y, z + size)
    line(x + size, y + size, z, x + size, y + size, z + size)
    line(x, y + size, z, x, y + size, z + size)

```

## Using your own shapes as objects

You can use your shapes as objects, but only if they are defined in the format `shape(x, y, z, size)`. I plan to add support for more formats in the future.