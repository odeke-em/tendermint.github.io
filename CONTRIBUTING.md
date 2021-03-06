# Contributing

## 5-Second Editing Guide

``` bash
# Edit Documenation
./content/intro/
./content/docs/
yarn run docs

# Edit Community > Software Ecosystem
./src/store/json/software.json

# Edit Community > Team
./src/store/modules/people.js

# Edit Community > Careers
./src/store/json/careers.json

# For careers, the 'weight' key is how necessary the role is:
# 4 = featured on homepage
# 3 = high
# 2 = medium
# 1 = low
# 0 = job is not listed

# Edit Community > Presentations
./src/store/modules/presentations.js
```

## Edit Documentation (Detailed Guide)

### New Documentation Page
To add a new page, create a markdown file in `./content/docs/` or `./content/intro/`. The title of the page is based on its filename. For example, 'this-is-awesome.md' will have a title of 'This is Awesome'.

By default, pages are ordered alphabetically based on filename. If you want to have a custom order for your documentation, label the files with numbers. Like this:

    ▾ try-this/
        #01-blah-blah.md
        #02-bob-lob-law-app.md
        #03-blargh.md
        #04-balhooney.md

### New Documentation Section
To add a new section to documentation, add a new directory under `.content/docs/`.

### Include Images

To include an image in documentation, place the image in the `./src/assets/images/` directory. Link to the image in the following format:

    <img alt="Application Architecture" src="../assets/images/tm-app-example.png">

The `../assets/images/` portion of the imgsrc is immutable because markdown-based docs are built into Vue components located in `./src/content/`.

### Build
Please run the following command to build all documentation.

    yarn run docs

## Editing Tips

### Include Images

To include an image in a documentation page, place the image in the `./src/assets/images/` directory. Link to the image in the following format:

    <img alt="Application Architecture" src="../static/images/tm-app-example.png">

The `../assets/images/` portion of the imgsrc is immutable because all markdown posts are built into Vue components located in `./src/content/`

### Link to the Site
If you want to link to other pages in the Tendermint site, please use the full path. This will prevent the user's browser from reloading the entire website. For example:

    # won't work
    [block hash](./tendermint-types#block-hash)

    # will work
    [block hash](/docs/specs/tendermint-types#block-hash)

### Link to Headings (e.g. `<h1><h2><h3>`)
HTML IDs are automatically generated for headings. You can link to them, but please remember to use the slug case format. 'this-is-slug-case'

    # won't work
    [block hash](./tendermint-types#Block.Hash)

    # will work
    [block hash](/docs/specs/tendermint-types#block-hash)
