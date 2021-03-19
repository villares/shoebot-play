# shoebot-play

Some experiments with the wonderful **`shoebot`**, the *easy vector graphics with Python* library & environment.

##### Tips for going from Processing Python to shoebot (and maybe the other way too)

On **shoebot** color arguments are from `0` to `1` and not `0` to `255`, unless yous specify with `colormode()` (similar to Processing's `colorMode()`)

| shoebot                  | <sub>comment and/or example</sub>                                                                                                           | Processing              | <sub>comment and/or example</sub>             |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- | --------------------------------------------- |
| `colormode()`            | Default is `RGBA` and range from `0` to `1` for each channel. One can get behaviour similar to Processing with `colormode(RGBA, range=255)` | `colorMode()`           | `RGB` or `HSB` (both include alpha)           |
| `nofill()`/ `nostroke()` |                                                                                                                                             | `noFill()`/`noStroke()` |                                               |
| `font()`                 | check how to use!                                                                                                                           | `textFont()`            |                                               |
| `fontsize()`             |                                                                                                                                             | `textSize()`            |                                               |
| `transform()`            | transform mode can be `CENTER` (from each object's center) or `CORNER` (from the coordinate system's origin)                                | [no equivalent]         | Processing is alwayss like shoebot's `CORNER` |
| `MOUSEX`, `MOUSEY`       |                                                                                                                                             | `mouseX`, `mouseY`      |                                               |
| `WIDTH`, `HEIGHT`        |                                                                                                                                             | `width`, `height`       |                                               |

###### Breaking state with custom attributes in optional arguments

*Note that in Processing `rect()` returns `None` and not an object you could transform! But in **shoebot** you can do this:*

`rect(20, 20, 100, 100, fill=(1, 0, 0))`

*which is the same as*

```python
r = rect(20, 20, 100, 100)
r.fill = color(1, 0, 0)
# This instantly draws a red rectangle regardless of the
# current state fill color. Likewise you could also use:
r.translate(x, y=None)
r.rotate(degrees=0, radians=0)
r.scale(x, y=None)
r.skew(x, y=None)
# The transformations are then applied only to rectangle r.
```

With the `text()` command you can also use the state-less *font* and *fontsize* parameters:

`text("hello", 20, 20, font="Helvetica")`
