# Tailwind 4 color palette in rgb()

## Why

Tailwind 4 included [a color palette](https://tailwindcss.com/docs/colors#default-color-palette-reference) that uses
`oklch()` CSS color notation. This format, while supported by all major browsers now,
is [not supported in browsers released in 2023 and sooner](https://caniuse.com/?search=oklch).

By including [palette-rgb.css](./palette-rgb.css) into your project, Tailwind will
use the `rgb()` notation instead increasing the browser compatibility of your website.

## Step 1

- Copy [palette-rgb.css](./palette-rgb.css) into your project
- Add `@import './palette-rgb.css';` after `@import 'tailwindcss';` in your CSS file

## Step 2 (optional)

To further increase browser compatibility of Tailwind 4, you may
opt out from using CSS `@layer` rule, which is
also [not widely supported by old browsers](https://caniuse.com/?search=%40layer).

To do so, you need to import each Tailwind layer
separately ([reference](https://github.com/tailwindlabs/tailwindcss/discussions/13188#discussioncomment-8737721)).
Combined with the RGB palette, the whole import stack should look like so:

```
@import 'tailwindcss/theme';
@import './palette-rgb.css';
@import 'tailwindcss/preflight';
@import 'tailwindcss/utilities';
```
