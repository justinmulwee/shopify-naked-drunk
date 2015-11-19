Naked Drunk - A Shopify Theme
---------------------------------------------
This is for Bourbon SASS developers who want to create a Shopify theme almost from scratch. This barebones theme retains Shopify's basic functionality, but has no styles or presentational markup.

I was going to strip down Shopify's own <a href="https://github.com/Shopify/skeleton-theme">Skeleton theme</a>, but found that [Capra Labs](http://thisiscapra.com/blog/naked-a-shopify-theme/) had already done this. I forked that and added added Thoughtbot's SASS libraries: Bourbon, Neat, and Bitters. Documentation at [Bourbon.io](http://bourbon.io).

Compiling the Style
---------------------
The sass folder will be ignored by Shopify. To get our styles to work, compile them into one file in the assets folder. If you have the Sass gem installed, you can just open this theme's folder in a terminal and paste this:
```
sass --sourcemap=none --watch sass/style.scss:assets/style.css.liquid
```
Alternatively, you could use a frontend compiler like Codekit or Prepros to do this.

Structure
---------------
```
├── assets
│   └── Javascript, CSS, and theme images
├── config
│   └── custom Theme Settings
├── layout
│   ├── theme.liquid
│   └── optional alternate layouts
├── sass
│   └── bourbon
│   └── neat
│   └── base
│   └── style.scss
├── snippets
│   └── optional custom code snippets
├── templates
│   ├── 404.liquid
│   ├── article.liquid
│   ├── blog.liquid
│   ├── cart.liquid
│   ├── collection.liquid
│   ├── index.liquid
│   ├── page.liquid
│   ├── product.liquid
│   └── search.liquid
```
