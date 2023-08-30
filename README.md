# Frontend Mentor - Single price grid component solution

This is a solution to the [Single price grid component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/single-price-grid-component-5ce41129d0ff452fec5abbbc).

## Table of contents

- [Frontend Mentor - Single price grid component solution](#frontend-mentor---single-price-grid-component-solution)
  - [Table of contents](#table-of-contents)
  - [Overview](#overview)
    - [The challenge](#the-challenge)
    - [Screenshot](#screenshot)
    - [Links](#links)
  - [My process](#my-process)
  - [Documentation](#documentation)
    - [HTML](#html)
    - [Styling](#styling)
      - [Website](#website)
        - [Layout](#layout)
        - [Components](#components)
      - [Mobile](#mobile)
    - [Built with](#built-with)
  - [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See a hover state on desktop for the Sign Up call-to-action

### Screenshot

![](./screenshot.jpg)

### Links

- Solution URL: [Solution](https://www.frontendmentor.io/solutions/single-price-grid-component-geBXHOdZi6)
- Live Site URL: [Live](https://elaborate-halva-3a1868.netlify.app/)

## My process

## Documentation

### HTML

```HTML
<body>
<main class="container">
    <section class="title">
      <h1 class="fw-700">
        Join our community
      </h1>
      <h2 class="fw-700">
        30-day, hassle-free money back guarantee
      </h2>
      <p class="fw-400">
        Gain access to our full library of tutorials along with expert code reviews.
        Perfect for any developers who are serious about honing their skills.
      </p>
    </section>
    <section class="cost">
      <h1 class="fw-700">
        Monthly Subscription
      </h1>
      <h2>
        <p>
          &dollar;29
        </p>
        <span class="fw-400">per month</span>
      </h2>
      <h3 class="fw-400">
        Full access for less than &dollar;1 a day
      </h3>
      <button class="fw-700">
        Sign Up
      </button>
    </section>
    <section class="about">
      <h1 class="fw-700">
        Why Us
      </h1>
      <p class="fw-400">
        <span>
          Tutorials by industry experts
        </span>
        <span>
          Peer &amp; expert code review
        </span>
        <span>
          Coding exercises
        </span>
        <span>
          Access to our GitHub repos
        </span>
        <span>
          Community forum
        </span>
        <span>
          Flashcard decks
        </span>
        <span>
          New videos every week
        </span>
      </p>
    </section>
  </main>
</body>
```

I structured my code by containing the sections in `<main>` and split the sections into three using `<section>`. For each of the sections, I've split the text into headings, paragraphs. For the last section, I've split the paragraph into spans because I needed each sentence to be in a new line. Which I later styled by making the span `display: block`.

### Styling

#### Website

I first added the css reset to the css file and added `:root` variables for primary and neutral colors. I've also added utility classes which I used in the HTML tags.

```css
/* Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --p-cyan: hsl(179, 62%, 43%);
  --p-light-cyan: hsl(178, 48%, 52%);
  --p-bright-yellow: hsl(71, 73%, 54%);
  --n-light-gray: hsl(204, 43%, 93%);
  --n-grayish-blue: hsl(218, 22%, 67%);
}

/* Utilities */
.fw-700 {
  font-weight: 700;
}

.fw-400 {
  font-weight: 400;
}
```

##### Layout

Looking at figma, I realized that the content is centered to the page like [[QR Code Component]] and [[3 Column Preview Card Component]] projects. So I made the `<body>` of the HTML `display: flex`. I've also added the background color using the `:root` variables and added font-family and font-size.

```css
body {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;

  background-color: var(--n-light-gray);
  font-family: karla, sans-serif;
  font-size: 16px;
}
```

I then used [grid](https://developer.mozilla.org/en-US/docs/Web/CSS/grid) to layout the content in main because the first row has one column and the second row has two columns.

```css
/* Use grid for the sections */
main {
  display: grid;
  grid-template-columns: repeat(2, 1fr);

  border-radius: 8px;
  box-shadow: 0px 15px 30px 0px rgba(0, 81, 171, 0.15);
}

.title {
  grid-column: 1/3;
}
```

##### Components

For the three sections, `.title`, `.cost`, and `.about`, I've used figma. Each of the three sections are straight forward.

```css
.title {
  grid-column: 1/3;
  background: white;
  height: 216px;
  width: 635px;
  border-radius: 8px 8px 0 0;
}

.title h1 {
  margin: 40px 0 24px 40px;
  color: var(--p-cyan);
  font-size: 24px;
  letter-spacing: -0.3px;
}

.title h2 {
  margin: 0 0 11px 40px;
  color: var(--p-bright-yellow);
  font-size: 18px;
  letter-spacing: -0.225px;
}

.title p {
  margin: 0 40px 40px 40px;
  color: var(--n-grayish-blue);
  font-size: 16px;
  line-height: 26px;
  letter-spacing: -0.2px;
}
```

As for the other two sections, the design and code is similar to the code above.

#### Mobile

```css
@media screen and (max-width: 600px) {
  main {
    display: flex;
    flex-direction: column;
  }

  .title {
    height: 259px;
    width: 311px;
  }

  .cost {
    height: 228px;
    width: 311px;
  }

  .about {
    height: 227px;
    width: 311px;
  }
}
```

For mobile design, I used `display: flex` to make the sections into rows. Then I changed the height and width of the three sections.

As for the stylings, I've updated the margins of each of the section's content to match the figma.

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid

## Author

- Frontend Mentor - [@SLuo490](https://www.frontendmentor.io/profile/SLuo490)
- LinkedIn - [@SLuo490](https://www.linkedin.com/in/sluo490/)
