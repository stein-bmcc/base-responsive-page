# Base Responsive Page

This is a basic responsive page with HTML5 and responsive CSS. It's meant as a starter set of files for student projects.

All of the file are left uncompressed and with comments. This is to make it easier for people to read them. Normally in a production site you would compress and minify the files to make the file size smaller.

## Base HTML5: index.html

This is a basic HTML5 file with a couple of additions.

1. The language in ```` <html class="no-js" lang="en-us"> ```` is set to American English. You can and should change this if your content&rsquo;s language is something else.
2. In that same element the *no-js* class has been added. This is related to Modernizr which is explained more next.
3. Modernizr is a feature detection script that allows you, the developer, to check whether the user's browser has HTML, CSS and JavaScript capabilities.
4. jQuery is a JavaScript library. While you don't have to use this one in particular, it is the most populr library. It's included here because it is very helpful to use JavaScript for certain places in the page. For example many responsive navigation solutions require JavaScript.

Speaking of navigation, that is not included here. There are a number of different solutions and which one you choose will depend on your navigation elements and choice based on the target audience, site type etc.


### Test Page: test-page.html

This is an example that adds content to the template from index.html to show how content might look when you first implement this page. Nothing has bee changed so the typography has not been properly styled and no other design choices (spacing, color etc.) have been made. It has all of the common (and some not so common) HTML5 Elements.

<p>I tood the content from <a href="http://twitter.com/cbracco">@cbracco</a>. Code on <a href="http://github.com/cbracco/html5-test-page">GitHub</a>.</p>

## Base CSS

These two files give a foundation to do all of your CSS including responsive styling.

### Normalized CSS Reset: normalized-reset.css

This is a version of Normalize [https://necolas.github.io/normalize.css/](https://necolas.github.io/normalize.css/) which is a CSS reset designed to help make all browsers look consistent. It has some opinionated styles and defaults related to typography that are are removed in this version. The reason for removing them is to force people who are learning about web design to creata all of the styling and spacing themselves. 

So, when this reset is applied the typography on the page won&rsquo;t look so great. Use the next CSS file to correct that.


### Base Responsive Styles: style.css

This CSS file has a few simple rules that you can put in as part of the base CSS for a responsive site.

#### Responsive Preparation

The first set applies a boder-box box model to all elements on the site. This makes doing a responsive layout much easier because it allows you to set a width property and then adding padding or margin won't change the overall width of the element and force you to adjust the width property accordingly. Paul Irish gets full credit for this and you can learn more [by reading his article](http://www.paulirish.com/2012/box-sizing-border-box-ftw/)

The second allows images to resize responsively. If you put an image in a container element that is narrower than the image it will adjust its size to fit the container. If the container is bigger than the image, the image will NOT grow. *Note: this is not a fully responsive image where different images are sent to different screen sizes* 

This CSS also affects the `<video>` element in the same way it works with the `<img>` element. This will not make embeded video (like from YouTube or Vimeo) responsive. See [this gist](https://gist.github.com/profstein/ff87675dd5e54c44185d) for that.

*Border-Box Explanation with Example*

For example you might make four .box elements appear next to each other by applying a rule like this:

````
.box{
    width: 25%;
    float: left;
}
````

But then the content in each box would touch the content for the other boxes. So you might want to add some padding. This is often easier to do in px or em then to calculate a percentage

````
.box{
    width: 25%;
    float: left;
    padding: 10px;
}
````

If you are using the normal content-box model then you would have to go in and subtract 20px (10px on each side) from the width. Even if you used % for the padding unit you would still have to subtract the amount of padding you added from the width.

With the border-box model, you just set the padding and you're done. And if you want to go and add borders later, no problem either.


*Embedded Video Styles*

These can be used to help add embedded video content, like YouTube videos, to your page. These styles require you set up your HTML in a specific way. See this CodePen for an example of it in use: [http://codepen.io/profstein/pen/mArLRj](http://codepen.io/profstein/pen/mArLRj).


#### Base Typographic Styles

The styles in this section are meant to be changed. The styings are not what youw would want to use on a production site. For example all of the headings are the same size. The idea is that this shows you what you can style and it is up to you to determine how to style it. 

At a minimum you should change the following:

* **html selector**: font-family to the base font you want, line-height to something bigger, probably in the 1.3–1.8 range.
* **p selector**: add in a bottom margin to separate paragraps. For example to add a blank line of 1em ````margin: 0 0 1em 0````
* **h1,h2,h3,h4,h5,h6**: change font-family to the font you want for your headings. 
* **All of the separate heading selectors**: Change the font-size and line-height (and margin, padding if needed) to set up a good typographic hierarchy. Alternatively you can replace this with a typographic scale from a site like: [http://type-scale.com/](http://type-scale.com/). You can also add in color here if you are using colors in your headings.
* Add your own custom styles to the bottom of the page. This will include things like color, layout, navigation, button styles, link styles etc.

