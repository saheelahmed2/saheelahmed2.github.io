<p align="center">
  <a href="https://saheelahmed2.github.io">
    <img alt="SaheelAhmed" src="https://avatars.githubusercontent.com/u/18718883?s=400&u=f9d11c18443d5ec454e15cfb2b96b08891336755&v=4" height="auto" width="60" style="border-radius:50%"/>
  </a>
</p>
<h1 align="center">
  saheelahmed2.github.io
</h1>

<p align="center">
  <a href="https://github.com/saheelahmed2/saheelahmed2.github.io/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT license." />
  </a>
  <img src="https://travis-ci.org/saheelahmed2/saheelahmed2.github.io.svg?branch=source" alt="Travis CI status" />
</p>

This is the Github repository for my website, [saheelahmed2.github.io](https://saheelahmed2.github.io)/[saheelahmed.xyz](https://saheelahmed.xyz).

This website is inspired & built upon [gatsby-starter-minimal-blog](https://github.com/LekoArts/gatsby-starter-minimal-blog) starter using  @lekoarts/gatsby-theme-minimal-blog Gatsby theme. It introduces a concept called "shadowing" which allows users to customise and replace files in the `src` directory. You can read more about [shadowing in Gatsby Themes](https://www.gatsbyjs.com/docs/how-to/plugins-and-themes/shadowing/).

Used GatsbyJS as the static site generator, because it allows for doing lots of cool things in the future, like interweaving React and Markdown with [MDX](https://mdxjs.com/).

## ✨ Features

- MDX
- Fully customizable through the usage of Gatsby Themes (and Theme UI)
- Light Mode / Dark Mode
- Typography driven, minimal style
- Tags/Categories support
- Code highlighting with [prism-react-renderer](https://github.com/FormidableLabs/prism-react-renderer) and [react-live](https://github.com/FormidableLabs/react-live) support. Also allows adding line numbers, line highlighting, language tabs, and file titles.
- RSS Feed for blog posts
- Google Analytics Support
- SEO (Sitemap, OpenGraph tags, Twitter tags)
- Offline Support & WebApp Manifes

## 🚀 Getting Started

### Creating the website

Use git to fork & clone the site and navigate into it:
```sh
git clone git@github.com:saheelahmed2/saheelahmed2.github.io.git
cd saheelahmed2.github.io

# install dependencies
yarn

# start hot-reloading server
gatsby develop
```
> **Note:** The central branch is `source` and not `main`, because Github Pages forces deployment of any user page to the `main` branch. Change the default branch from `main` to something else and use `main` as a site deployment only. Travis CI builds the site to main automatically. Read more [here](https://www.gatsbyjs.com/docs/how-to/previews-deploys-hosting/how-gatsby-works-with-github-pages/#:~:text=your%20publishing%20source.-,Deploying%20to%20a%20GitHub%20Pages%20subdomain%20at%20github.io,-For%20a%20repository).

After running the above code, you can see the website running on http://localhost/8000

If you want to learn more about how you can use a Gatsby starter that is configured with a Gatsby theme, you can check out this shorter or longer tutorial. The tutorials don't exactly apply to this starter however the concepts are the same.

## 📝 Modifying theme

> **Important Note:** Please read the guide [Shadowing in Gatsby Themes](https://www.gatsbyjs.com/docs/how-to/plugins-and-themes/shadowing/) to understand how to customize the underlying theme!

This starter creates a new Gatsby site that installs and configures the theme [`@lekoarts/gatsby-theme-minimal-blog`](https://github.com/LekoArts/gatsby-themes/tree/master/themes/gatsby-theme-minimal-blog).

Have a look at the theme's README and files to see what options are available and how you can shadow the various components including Theme UI. 

To overwrite parts of the theme, add files in this repository at
```sh
src/@lekoarts/gatsby-theme-minimal-blog/
```
So for example, to replace the "hero" text that shows up at the front of the homepage, add the file:
```sh
src/@lekoarts/gatsby-theme-minimal-blog/texts/hero.mdx
```
The Theme UI config can be configured by shadowing its files in `src/gatsby-plugin-theme-ui/`.

### Code Highlighting

Since the underlying theme ships with [prism-react-renderer](https://github.com/FormidableLabs/prism-react-renderer) and [react-live](https://github.com/FormidableLabs/react-live) certain additional features were added to code blocks. You can find an overview / usage example in the [example repository](https://github.com/LekoArts/gatsby-themes/tree/master/examples/minimal-blog/content/posts/fantastic-beasts-and-where-to-find-them/index.mdx)! If you want to change certain code styles or add additional language tabs, you need to shadow the file `src/@lekoarts/gatsby-theme-minimal-blog/styles/code.js`.

**Language tabs:**

When you add a language (such as e.g. `js` or `javascript`) to the code block, a little tab will appear at the top left corner.

````
```js
// code goes here
```
````

**Code titles:**

You can display a title (e.g. the file path) above the code block.

````
```jsx:title=your-title
// code goes here
```
````

Or without a specific language:

````
```:title=your-title
// code goes here
```
````

**Line highlighting:**

You can highlight single or multiple (or both) lines in a code block. You need to add a language.

````
```js {2,4-5}
const test = 3
const foo = 'bar'
const harry = 'potter'
const hermione = 'granger'
const ron = 'weasley'
```
````

**Hide line numbers:**

If you want to hide line numbers you can either globally disable them (see Theme options) or on a block-by-block basis. You can also combine that with the other attributes.

````
```noLineNumbers
// code goes here
```
````

**react-live:**

Add `react-live` to the code block (and render the component) to see a preview below it.

````
```js react-live
const onClick = () => {
  alert("You opened me");
};
render(<button onClick={onClick}>Alohomora!</button>);
```
````

### Adding content

#### Adding a new blog post

New blog posts will be shown on the index page (the three most recent ones) of this theme and on the blog overview page. They can be added by creating MDX files inside `content/posts`. General setup:

1. Create a new folder inside `content/posts`
1. Create a new `index.mdx` file, and add the frontmatter
1. Add images to the created folder (from step 1) you want to reference in your blog post
1. Reference an image as your `banner` in the frontmatter
1. Write your content below the frontmatter

**Frontmatter reference:**

```md
---
title: Introduction to "Defence against the Dark Arts"
date: 2019-11-07
description: Defence Against the Dark Arts (abbreviated as DADA) is a subject taught at Hogwarts School of Witchcraft and Wizardry and Ilvermorny School of Witchcraft and Wizardry.
tags:
  - Tutorial
  - Dark Arts
banner: ./defence-against-the-dark-arts.jpg
---
```

**The fields `description` and `banner` are optional!** If no description is provided, an excerpt of the blog post will be used. If no banner is provided, the default `siteImage` (from `siteMetadata`) is used.

The `date` field has to be written in the format `YYYY-MM-DD`!

#### Adding a new page

Additional pages can be created by placing MDX files inside `contents/pages`, e.g. an "About" or "Contact" page. You'll manually need to link to those pages, for example by adding them to the navigation (in `navigation` option of the theme). General instructions:

1. Create a new folder inside `content/pages`
1. Create a new `index.mdx` file, and add the frontmatter
1. Write your content below the frontmatter
1. Optionally add files/images to the folder you want to reference from the page

**Frontmatter reference:**

```md
---
title: About
slug: "/about"
---
```

#### Changing the "Hero" text

To edit the hero text ("Hi, I'm Lupin...), create a file at `src/@lekoarts/gatsby-theme-minimal-blog/texts/hero.mdx` to edit the text.

#### Changing the "Projects" part

To edit the projects part below "Latest posts", create a file at `src/@lekoarts/gatsby-theme-minimal-blog/texts/bottom.mdx` to edit the contents.

### Changing your fonts

By default, the underlying theme and thus this starter uses "IBM Plex Sans" as its font. It's used throughout the site and set as a `font-family` on the `html` element.

If you want to change your default font or add any additional fonts, you'll need to change two things:

1. The configuration for `gatsby-omni-font-loader` => Responsible for loading the font CSS files
1. The Theme UI config and its `fonts` key (see [Theme UI Typography Docs](https://theme-ui.com/theming#typography)) => Responsible for setting the `font-family` in the example

After adjusting the configuration for `gatsby-omni-font-loader` you'll need to shadow the theme's Theme UI config and overwrite the `fonts` key. For the sake of this explanation it's assumed that you replaced "IBM Plex Sans" with "Roboto Mono".

Create a file at `src/gatsby-plugin-theme-ui/index.js` with the following contents:

```js
import { merge } from "theme-ui";
import originalTheme from "@lekoarts/gatsby-theme-minimal-blog/src/gatsby-plugin-theme-ui/index";

const theme = merge(originalTheme, {
  fonts: {
    body: `"Roboto Mono", monospace`,
  },
});

export default theme;
```

As defined in the [Theme Specification](https://theme-ui.com/theme-spec#typography) `body` is the default body font family.

**Another example:** You didn't replace "IBM Plex Sans" but added "Roboto Mono" additionally since you want to use it for your headings.

Then you'd not overwrite `body` but add a `heading` key:

```js
import { merge } from "theme-ui";
import originalTheme from "@lekoarts/gatsby-theme-minimal-blog/src/gatsby-plugin-theme-ui/index";

const theme = merge(originalTheme, {
  fonts: {
    heading: `"Roboto Mono", monospace`,
  },
});

export default theme;
```

### Change your `static` folder

The `static` folder contains the icons, social media images and robots.txt. Don't forget to change these files, too!