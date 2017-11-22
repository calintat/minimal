# MinNight

A sleek toggleable night-mode theme for [Hugo](https://gohugo.io). Built on top on the great [Minimal](https://github.com/calintat/minimal) theme. Keeps all of the great Minimal stuff, like custom accent color, Google Fonts, FontAwesome menu icons, and layers on:

- A night-mode toggle, for eye easy reading
- A tags/categories list page template from [Xmin](https://github.com/yihui/hugo-xmin)
- Updated tag/category labels to hyperlinks back to list of sames
- Different list templates for posts and projects

A live demo is available [here](https://natedayta.com).

## Installation

You can install the theme either as a clone or submodule.

I recommend the latter. From the root of your Hugo site, type the following:

```
$ git submodule add https://github.com/nathancday/min_night themes/min_night
$ git submodule init
$ git submodule update
```

Now you can get updates to Minimal in the future by updating the submodule:

```
$ git submodule update --remote themes/min_night
```

I use this theme via the `R` pacakge `blogdown`, you can do the same in R.

```
library(blogdown)
new_site(theme = "nathancday/min_night")
```

## Configuration

After installation, take a look at the `exampleSite` folder inside `themes/minimal2`.

To get started, copy the `config.toml` file inside `exampleSite` to the root of your Hugo site:

```
$ cp themes/minimal/exampleSite/config.toml .
```

This file is the centerpiece for easy theme customizations. Some noteable features are described next.

## Features

- The accent colour can be changed by using the `accent` field in `config.toml`. This is the color that will be used as the background of your site in dark-mode. Dark colors work best.

- You can also change the background color of the main page by using `backgroundColor`. The navbar and footer are always light and dark in the their respective modes.

- Add colored 5px borders at the top and bottom of pages by setting `showBorder` to `true`. Even if this is set to `false` the `accent` color will still be used for the main page background in dark-mode.

Example:
```toml
[params]
    accent = "red"
    showBorder = true
    backgroundColor = "#f5f5f5"
```
You can use either hex codes or color names ("red"), I reccomend using hex codes for more specific color assignments.

### Fonts

The theme uses [Google Fonts](https://fonts.google.com) to load its font. To change the font:

```toml
[params]
    font = "Raleway" # should match the name on Google Fonts!
```

### Syntax highlighting

The theme supports syntax highlighting thanks to [highlight.js](https://highlightjs.org). You can change the color scheme via the `highlightStyle` param. Checkout out the options [here](https://highlightjs.org/static/demo/), make sure your main languages render well. For best results with dark-mode, I reccommend choosing a light background style that matches your `accent` color. You control the languages that are highlighted with the `highlightLanguages` param.

The style and languages should be written in hyphen-separated lowercase, for example:

```toml
[params]
    highlight = true
    highlightStyle = "solarized-dark"
    highlightLanguages = ["r", "go"]
```
