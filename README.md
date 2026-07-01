# Simple Icons Extension For Quarto

A Quarto shortcode extension for embedding [Simple Icons](https://simpleicons.org) SVG brand icons inline in HTML documents. Icons are fetched from the Simple Icons CDN at render time and inlined directly into the HTML output, so they work correctly with `self-contained: true`.

## Installing

```bash
quarto install extension pbosetti/simpleicons
```

This will install the extension under the `_extensions` subdirectory.
If you're using version control, you will want to check in this directory.

## Using

To embed an icon, use the `{{< si >}}` shortcode with the icon's slug name. For example:

```
{{< si github >}}

{{< si python >}}

{{< si docker size=2em color=#2496ED >}}

{{< si slack size=2em label="Slack" >}}
```

The slug is the lowercase identifier used by Simple Icons (the same string that appears in the CDN URL `https://simpleicons.org/icons/{slug}.svg`). Browse all 3,000+ available icons and their slugs at:

[https://simpleicons.org](https://simpleicons.org)

### Icon color

To specify a fill color, use the `color` argument. You can use CSS [named colors](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#named_colors), hex values, or the `rgb()`/`hsl()` functions.

```
{{< si github color=#181717 >}}

{{< si python color=#3776AB >}}

{{< si javascript color=gold >}}
```

**Note: when using `rgb()` or `hsl()`, do not include spaces between values — write `rgb(232,96,51)`, not `rgb(232, 96, 51)`.**

If no `color` is specified the icon inherits the SVG's default fill (typically black).

### Icon sizing

Any CSS length unit is accepted: `px`, `em`, `rem`, `vw`, `vh`.

```
{{< si rust size=3em >}}

{{< si typescript size=48px >}}

{{< si linux size=2.5rem >}}
```

The default size is `1em` (scales with surrounding text).

### CSS class

Assign a CSS class with the `class` argument to style multiple icons together.

```{css}
.brand {
  fill: steelblue;
}
```

```
{{< si github class=brand >}}

{{< si python class=brand >}}

{{< si javascript class=brand >}}
```

### Accessibility

If the icon conveys meaning (i.e. it is not purely decorative), provide a description via `label`. This replaces the icon's default `<title>` element and preserves `role="img"` for screen readers. Decorative icons (no `label`) are automatically marked with `aria-hidden="true"`.

```
{{< si github size=2em label="GitHub repository" >}}
```

## Example

See [example_simpleicons.qmd](example_simpleicons.qmd) for a working example.

## Acknowledgement

The structure of this extension is adapted from the [bsicons](https://github.com/shafayetShafee/bsicons) Quarto extension by Shafayet Khan Shafee, which was in turn adapted from [fontawesome](https://github.com/quarto-ext/fontawesome).
