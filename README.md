# Bootstrap Icons Extension For Quarto

This extension provides support including icons provided by [SimpleIcons](https://simpleicons.org). Icons can be used in HTML documents only.

## Installing

```bash
quarto install extension pbosetti/simpleicons
```

This will install the extension under the `_extensions` subdirectory.
If you're using version control, you will want to check in this directory.

## Using

To embed an icon, use the {{< bi >}} shortcode. For example:

```
{{< bi alarm >}}

{{< bi alarm-fill >}}

{{< bi balloon-heart  size=5em color=#2ecaf9 >}}

{{< bi emoji-sunglasses  size=5em color=#2ecaf9 label="Proud Happy Face" >}}

```

This extension provides support for over 2,000 bootstrap icons. You can browse all of the available icons here:

[https://simpleicons.org](https://simpleicons.org)

### icons color

To specify a color for icons, you can use css [named colors](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#named_colors) (i.e. `red`, `cornflowerblue` etc), [RGB color model](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#rgb_color_model) or [HSL color model](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#hsl_color_model).

The complete list of available named color is [here](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color).

```
{{< si github color=red >}}

{{< si python color=lightseagreen >}}
```

**Note that, when specifying color with either RGB or HSL model, DO NOT PUT SPACE BETWEEN VALUES. That is, do not write as `rgb(232, 96, 51)`, instead write as `rgb(232,96,51)`, otherwise it will not work.**

### icon sizing

You can actually use any size in `px`, `em`, `rem`, `vw`, `vh` css units.

```
{{< bi incognito size=37px >}}

{{< bi person-plus-fill size=3.1rem >}}

{{< bi postcard-heart size=2.7em >}}

{{< bi reddit size=9.8vw >}}

{{< bi slack size=7.6vh >}}

```

### class

It is also possible to assign css class using `class` argument so that multiple icons can be styled together.

```{css}
.styled {
  color: red;
}
```

```
{{< bi windows class=styled >}}

{{< bi ubuntu  class=styled >}}

{{< bi terminal-fill class=styled >}}
```

### Accessibility

If the icon is being used in place of some text, just add some descriptive text in the label argument.

```
{{< bi hand-thumbs-up-fill  size=7em color=cornflowerblue label="Thumbs up" >}}
```

## Example

Here is the source code for a minimal example: [example.qmd](example.qmd).

The output of `example.qmd` in [HTML](https://shafayetshafee.github.io/bsicons/example_html.html) format and in [revealjs](https://shafayetshafee.github.io/bsicons/example.html) format.

## Acknowledgement

The code for this extension is adapted from the [fontawesome](https://github.com/quarto-ext/fontawesome).
