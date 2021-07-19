# Sass Dev Template

This template:

- Sets up boilerplate common to most static-site Sass projects
- Can be extended to work in web application frontends
- Provides some opinionated extras for element sizing/spacing, screen size response, and webfont hosting
- Provides a basic dev and build pipeline with lite-server, node-sass, and postcss-cli. The build will compile `main.scss`, insert vendor prefixes, then minify the output to `/css/style.css`.

This is just how I prefer to set things up for simple Sass projects/experiments/studies at the moment.

## Installation and Use

In order:

```sh
# Install dev dependencies with:
npm i
# Run a build for initialization or deployment with:
npm run build:css
# Run the dev environment with:
npm run start
```

## Sass Base and Utilities

### Reset/Normalize

- `sass/base/_base.scss`

There's a very rudimentary reset/normalize which sets:

- margin and padding to 0 with a universal selector
- inherited box-sizing on a universal selector with `::before` and `::after`
- `border-box` box-sizing on the `html` element

### Units and Sizes

- `sass/base/_base.scss`

Basic units are configured for relative font sizing that also respects the client's display zoom settings. The same configured units can be used for all sizing in all other elements as well.

Use **root em** (`rem`) units for all text, spacing, and sizing except where other measure units are required.

At the `html` element level, **1.0rem = 10px**.

### Hosted Webfonts

- `sass/base/_fonts.scss`

`@font-face` declarations should go in `sass/base/_fonts.scss`. The webfont files can go in a `/font` directly in the project root, organized within that directory by typeface.

### Images

- `/img`
- `/img/svg`

### Media Queries

- `/sass/abstracts/_mixins.scss`

A media query handler based on relative units (`em`) is provided via Sass Mixin. Usage:

```
@include respond(<breakpoint>) {...}
```

#### respond() Breakpoint Arguments

- `small`
	- `@media only screen and (max-width: 37.5em)` which handles >600px
- `midPort`
	- `@media only screen and (max-width: 56.25em)` which handles >900px
- `midLand`
	- `@media only screen and (max-width: 75em)` which handles >1200px
- `large`
	- `@media only screen and (min-width: 112.5em)` which handles <1800px

These default breakpoints should be touch/mouse interface aware. It's highly recommended to customize these brekapoints per project.	
	
### Global Sass Variables

- `/sass/abstracts/_variables.scss`

Some variables are provided for reference of my preferred conventions:

- `$colorWhite` (#fff)
- `$colorBlack` (#000)
- `$colorPrimary` (#af5fff)
- `$defaultFontSize` (1.6rem)

### Extras

- A Sass mixin for vertical and horizontal center placement:
	- `@import absCenter;`
- Some example utility classes in `sass/base/_utilities.scss`
- Some example breakpoint variables for creating media queries without the handler

## To Do:

- convert `@import`s to `@use`/`@forward`s
