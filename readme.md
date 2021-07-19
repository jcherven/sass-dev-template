# Sass Dev Template

This template does the following:

- Sets up common boilerplate common to most static-site Sass projects
- Provides some opinionated extras for element sizing/spacing, screen size response, and webfont hosting
- Provides a basic dev and build pipeline with lite-server, node-sass, and postcss-cli. The build will compile the SCSS, add vendor prefixes, then minify the output to `/css/style.css`.

## Installation and Use

```sh
# Install dev dependencies with:
npm i
# Create the built, prefixed, and minified stylesheet from SCSS for your deployment with:
npm run build:css
# Run the dev environment with:
npm run start
```

## Sass Base and Utilities

### Normalize

- `sass/base/_base.scss`

This template contains a very simple reset/normalize which sets:

```css
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
```
### Units and Sizes

- `sass/base/_base.scss`

Basic units are configured for relative font sizing that respects the client's display zoom settings. The same units can be used for all sizing in all other elements as well.

Use **root em** (`rem`) units for all text, spacing, and sizing except where other units are required.

The `rem` unit is configured to equal `10px` at the `html` element level.

### Hosted Webfonts

`@font-face` declarations are in `/sass/base/_fonts.scss`. The webfont files should ideally be placed in `/font` directly in the project root, organized within that directory by typeface.

### Images

- `/img`
- `/img/svg`

### Media Queries

- `/sass/abstracts/_mixins.scss`

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

- `/sass/abstracts/_variables.scss`

Some variables are provided for reference of the convention used in this template:

- `$colorWhite` (#fff)
- `$colorBlack` (#000)
- `$defaultFontSize` (1.6rem)

## To Do:

- convert `@import`s to `@use`/`@forward`s
