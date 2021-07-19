# Sass Dev Template

## Installation and Use

A simple build/dev pipeline is provided with lite-server, node-sass, and postcss-cli.

```sh
# Install dev dependencies with:
npm i
# Run the dev environment with:
npm run start
```

## Sass Base and Utilities

### Normalize

This template contains a very simple reset/normalize which sets:

```css
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
```
### Units and Sizes

Basic units are configured for relative font sizing that respects the client's display zoom settings. The same units can be used for all sizing in all other elements as well.

Use **root em** (`rem`) units for all text, spacing, and sizing except where other units are required.

The `rem` unit is configured to equal `10px` at the `html` element level.

### Media Queries

A media query handler based on relative units (`em`) is provided via Sass Mixin. Usage:

```
@include respond(<arg>) {...}
```

#### respond() Arguments

- `phone`
	- `@media only screen and (max-width: 37.5em)` which handles >600px
- `tabPort`
	- `@media only screen and (max-width: 56.25em)` which handles >900px
- `tabLand`
	- `@media only screen and (max-width: 75em)` which handles >1200px
- `bigDesktop`
	- `@media only screen and (min-width: 112.5em)` which handles <1800px

### Global Sass Variables

Some variables are provided for reference of the convention used in this template:

- `$colorWhite` (#fff)
- `$colorBlack` (#000)
- `$defaultFontSize` (1.6rem)
