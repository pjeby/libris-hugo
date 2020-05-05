# Libris Hugo

A port of the [Stackbit Libris](https://github.com/stackbithq/stackbit-theme-libris) theme for use with Hugo.  [Live Demo](https://pjeby.github.io/libris-hugo/)

[![](images/screenshot.png)](https://pjeby.github.io/libris-hugo/)

Note: I am still refactoring things to be more Hugo-friendly, so things may change a lot.  If you update your local copy of this theme to a new version, *you should expect things to break*.  The theme is currently quite functional (even more so than the original in some aspects), but I expect to still be refactoring various things in the future, like:

* configurable language support for prism highlighting
* improved page components system and DRY rendering thereof
* list pagination
* proper kind/type/section/layout hierarchy mapping (a lot of stuff is still organized by layout only)
* better separation between the theme and the example site (some site stuff may still be in the theme)

And any or all of these changes might be backward-incompatible with the effective "API" of a previous release.

## Creating Documentation Sections

A site can have one or more "books" of documentation as top-level sections; e.g. `content/docs`, `content/man`, `content/book1`, `content/book2` etc.  Each section must have an `_index.md` (the top level/overview page), and can have a single sublevel of folders containing an `_index.md` file for each subsections of that section.  For example:

- Documentation root page: `content/docs/_index.md`

  (Note: if you put any other pages in the section root next to this file, they will be linked at the bottom of this page, but will not appear in the section's sidebar navigation, or on any overview pages.)

- Parent section pages: `content/docs/<section_name>/_index.md`

- Child section pages: `content/docs/<section_name>/<page_name>.md`

Documentation pages should contain the following front matter. `title` is required for all pages, and `weight` is needed to change the order from simple alphabetical order.   `type` is only needed for pages under a directory other than `content/docs`.

```yaml
---
- weight: defines the order of the child section page.
- type: docs  # required if not under /content/docs
- title: >-
    Defines the page title, and navigation menu item label.
- summary: >-
    Can be defined on a parent section pages to render the description
    of the section in the Overview page (`overview.html`). This field is ignored
    for child section pages.
---
```

Each book of documentation can have a page that uses `layout: overview` to render an overview of the subsections of that "book" of documentation.  (It must also set `type: docs` if it is outside the `content/docs/`  directory.)

### Example

Here is an example to a folder structure, several sections and pages within a single documentation "book" (`docs`):

```
.
├── content
│   ├── docs
│   │   ├── getting-started
│   │   │   ├── _index.md        [section parent page]
│   │   │   ├── installation.md  [section child page]
│   │   │   └── quick-start.md   [section child page]
│   │   ├── guides
│   │   │   ├── _index.md        [section parent page]
│   │   │   ├── features.md      [section child page]
│   │   │   └── overview.md      [section child page]
│   │   ├── faq
│   │   │   └── _index.md        [section parent page]
│   │   └── _index.md            [documentation root page, "Welcome To Libris"]
│   └── ...
└── ...
```

`content/docs/guides/overview.md`:

```yaml
---
title: Overview
weight: 1           # position guides/overview first
---
```

`content/docs/guides/features.md`:

```yaml
---
title: Features
weight: 2           # position guides/features second
---
```



![Navigation Example](images/libris-navigation-example.png "Navigation Example")



### Callouts

To add a callout to your documentation, simply use the following html markup:

```html
<div class="important">
  <strong>Important:</strong> 
  This is the "Important" callout block of text. It indicates a warning or caution.
  Use it for an important message. 
</div>
```

```html
<div class="note">
  <strong>Note:</strong> 
  This is the "Note" callout block of text. It signifies a general note.
</div>
```

### Syntax Highlighter

To enable syntax highlighting in your code blocks, add a language identifier. For example, to syntax highlight JavaScript code, specify `javascript` next to the tick marks before the fenced code block:

~~~md
```javascript
if (condition) {
  code to run if condition is true
} else {
  run some other code instead
}
```
~~~

## Editing the Homepage

The homepage content uses `content/_index.md`. You can edit all of the homepage sections by editing this file's front matter.

## Main Navigation

The items of the main menu located at the top can be defined either inside the page front matter or inside the `config.yml` file.

To add a page menu item, you should define the `menu` parametter in the front matter of the page. For instance:

```yaml
---
title: Welcome to Libris
menu:
  main:
    weight: 2
    name: Docs
---
```

To add a global menu item, you should define it inside the root `menu` field inside `config.yml`. For instance:

```yaml
menu:
  main:
    - identifier: github
      name: GitHub
      url: "https://github.com/"
      weight: 6
```

## Additional Templates

Besides the usual templates (`blog`, `page`, `post`) and documentation templatee mentioned above (`docs`), there are two additional templates that can be used for pages:

- `overview` - used to list all the subsections of the current docs section in a neat grid.
- `showcase` - used to showcase the users of your product.

## Social Links

To display social icons in the footer, update the `social.json` file located in the `data` folder. You can use any icon supported by [Font Awesome](https://fontawesome.com/icons?d=gallery&s=brands) and just need to specify the appropriate Font Awesome class name as the `icon` value.

## Color palettes

Libris supports the following color palettes:

- blue (default)
- green
- navy
- violet

To change the color palette, update the `palette` variable in config.yaml.

## Credits

- [Lato](https://fonts.google.com/specimen/Lato). Licensed under the [Open Font License](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL_web).
- [Font Awesome icons](https://fontawesome.com/). Licensed under the [Font Awesome Free License](https://fontawesome.com/license/free).
- [Unsplash images](https://unsplash.com/). Licensed under the (Unsplash License)[https://unsplash.com/license].
- [Prism syntax highlighter](https://prismjs.com/). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
- [Reframe.js](https://github.com/dollarshaveclub/reframe.js). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
- [Smooth Scroll](http://github.com/cferdinandi/smooth-scroll). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
- [Gumshoe](https://github.com/cferdinandi/gumshoe). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
- [clipboard.js](https://zenorocha.github.io/clipboard.js). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
