Naked Drunk - a bourbon sass theme framework for Shopify
---------------------------------------------

This is a barebones starting point for developers who wish to create a Shopify theme from scratch using Thoughtbot's SASS libraries: Bourbon, Neat, and Bitters. It retains Shopify's basic functionality but has no styles, presentational markup or theme settings. It is not intended as a complete theme but as the basis for building one. Doing so will require an understanding of Sass, Bourbon, Shopify and Liquid.

As you can see, it's unstyled except for the defaults that come with Bitters.
![screenshot](http://i.imgur.com/AMaHfeb.png)
Why
----
Shopify has created two themes meant for developers: [Skeleton](https://github.com/Shopify/skeleton-theme) and [Timber](http://shopify.github.io/Timber/). Despite being small, Skeleton is still bloated with presentational markup. It's minimal but complete, thus not ideal for from-scratch designs. And while it's not *terribly* outdated, Shopify appears to have mostly abandoned it in favor of their more complex framework, Timber. Timber is much larger, with non-semantic markup and a myriad of baked-in options, similar to Bootstrap. 

I wanted a starting point that included Bourbon, Neat and Bitters, but was otherwise completely bare, whereas Skeleton and Timber feel like I'm customizing someone else's theme and navigating their idiosyncracies.

I was going to start by stripping down Shopify's own <a href="https://github.com/Shopify/skeleton-theme">Skeleton theme</a>, but found that [Capra Labs](http://thisiscapra.com/blog/naked-a-shopify-theme/) had already done this. I forked that, added the SASS libraries, and made some updates by consulting Timber's code.

Making It Work
---------------------
Shopify will ignore any folders other than the default (assets, config, layout, snippets and templates). So while Shopify theming allows Sass out of the box, you cannot normally organize style into folders of partials. This is contrary to Bourbon and to advanced Sass organization in general. Fortunately we can get around this by locally compiling all our sass into one vanilla css file in the assets folder. You must do this or **all your styles will be ignored**.

If you have the Sass gem installed, simply open the theme's folder in a terminal and paste the following:
```
sass --sourcemap=none --watch sass/style.scss:assets/style.css.liquid
```
If you don't like the Terminal, any preprocessor such as Codekit or Prepros can easily handle this.

Structure
---------------
```
├── assets
│   └── compiled css
│   └── optional javascript & images
├── config
│   └── custom Theme Settings
├── layout
│   ├── theme.liquid
│   └── optional alternate layouts
├── sass
│   └── style.scss
│   └── bourbon/
│   └── neat/
│   └── base/
│   └── optional style folders
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
