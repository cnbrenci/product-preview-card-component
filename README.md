# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Links

<!--todo: when I submit - Solution URL: [Add solution URL here](https://your-solution-url.com) -->
- [Live Site URL](https://cnbrenci.github.io/product-preview-card-component/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- `font-size: 62.5%` trick

### What I learned

I learned about using different images depending on the size of the viewport.
[This](https://aboutbits.it/blog/2021-08-04-responsive-images) article breaks down a few options.
I first tried using `img` `srcset` but this approach is only good if the image is the same at different sizes, just different resolutions.
Since in this project, the image is cropped differently for the different sizes, it doesn't work. The image doesn't change to 
the correct crop as you resize in a chromium browser. 

```html
<section class="hero">
  <img 
    src="./images/image-product-mobile.jpg" 
    alt="Flat lay of perfume surrounded by leaves" 
    sizes="(min-width: 600px) 300px, (max-width: 599px) 343px"
    srcset="./images/image-product-desktop.jpg 300w, ./images/image-product-mobile.jpg 343w"
  />
</section>
```

A better option is using the `<picture>` tag since this gives finer control of which photo to use for different screen size.

```html
<section class="hero">
  <picture>
    <source srcset="images/image-product-desktop.jpg" media="(min-width: 600px)" />
    <img src="images/image-product-mobile.jpg" alt="Flat lay of perfume surrounded by leaves" />
  </picture>
</section>
```

Note that the CSS is selecting on `img` rather than `picture` to apply styles:

```css
.hero img {
  border-radius: 10px 10px 0 0;
  width: 100%;
}
```

Other handy trick to center the component on the screen which I've used multiple times now: 

 ```css
 body {
  display: grid;
  height: 100vh;
  justify-content: center;
  align-items: center;
  align-content: center;
 }
 ```

### Continued development

I want to continue to evolve my process, and start adding in additional tools like trying out css pre-compilers, etc.

I also want to add accessibility into the process as well. Coming up I'm going to do an accessibility pass on all past projects, get familiar with the tools and rules so I can be thinking about accessibility thoroughly throughout development.

### Useful resources

- [This article](https://aboutbits.it/blog/2021-08-04-responsive-images) on responsive images helped me understand the different options and in what instance you'd want to use each technique.

## Author

- Website - [cassibrenci.dev](https://www.cassibrenci.dev)
- Frontend Mentor - [@cnbrenci](https://www.frontendmentor.io/profile/cnbrenci)

## Acknowledgments

I would like to acknowledge my accountability buddy in life @mlooper5 for working on this project together with me in parallel :-D 