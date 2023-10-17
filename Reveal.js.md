<!-- markdownlint-disable MD001 MD036 -->
# Reveal.js

## Tools versions

|  Os / Tool | Version |
| :--------: | :-----: |
| Linux Mint |   19.3  |
|  reveal.js |  4.1.0  |

## Todo

N/A

## Bulk Note

N/A

## About

> reveal.js is an open source HTML presentation framework. It's a tool that enables anyone with a web browser to create fully-featured and beautiful presentations for free.

## Installation procedure

**Full Setup**

```sh
git clone https://github.com/hakimel/reveal.js.git
cd reveal.js && npm install
```

## Getting start

To quickly execute reveal.js

```sh
cd reveal.js && npm start
```

## Content

#### Markup

Simple example :

```html
<html>
  <head>
    <link rel="stylesheet" href="dist/reveal.css">
    <link rel="stylesheet" href="dist/theme/white.css">
  </head>
  <body>
    <div class="reveal">
      <div class="slides">
        <section>Horizontal Slide</section>
        <section>
          <section>Vertical Slide 1</section>
          <section>Vertical Slide 2</section>
        </section>
      </div>
    </div>
    <script src="dist/reveal.js"></script>
    <script>
      Reveal.initialize();
    </script>
  </body>
</html>
```

#### Markdown

Simple example :

```html
<section data-markdown>
  <textarea data-template>
    ## Slide 1
    A paragraph with some text and a [link](http://hakim.se).
    ---
    ## Slide 2
    ---
    ## Slide 3
  </textarea>
</section>
```

Include plugin

```html
<script src="plugin/markdown/markdown.js"></script>
<script>
  Reveal.initialize({
    plugins: [ RevealMarkdown ]
  });
</script>
```

External Markdown

```html
<section data-markdown="example.md"
  data-separator="^\n\n\n"
  data-separator-vertical="^\n\n"
  data-separator-notes="^Note:"
  data-charset="iso-8859-15">
</section>
```

Note :

- data-markdown: defines the external Markdown
- data-separator: defines a regular expression for horizontal slides
- data--separator-vertical: defines a regular expression for vertical slides
- data--separator-notes: specifying the beginning of the current slide's speaker notes

Element and Slide Attributes  
Can be added through HTML comments

```html
<section data-markdown>
  <script type="text/template">
    - Item 1 <!-- .element: class="fragment" data-fragment-index="2" -->
    - Item 2 <!-- .element: class="fragment" data-fragment-index="1" -->
  </script>
</section>
<section data-markdown>
  <script type="text/template">
  <!-- .slide: data-background="#ff0000" -->
    Markdown content
  </script>
</section>
```

Using bracket

```html
<section data-markdown>
  <textarea data-template>
    ``js [1-2|3|4]
    let a = 1;
    let b = 2;
    let c = x => 1 + 2 + x;
    c(3);
    ``
  </textarea>
</section>
```

#### Backgrounds

Simply add a data-background in a section

| Attribute                   | Default   | Description                                                        |
| :-------------------------- | :-------- | :----------------------------------------------------------------- |
| data-background-color       |           | All CSS color formats are supported.                               |
| data-background-image       |           | URL of the image to show.                                          |
| data-background-size        | cover     | See background-size on MDN.                                        |
| data-background-position    | center    | See background-position on MDN.                                    |
| data-background-repeat      | no-repeat | See background-repeat on MDN.                                      |
| data-background-opacity     | 1         | 0 is transparent and 1 is fully opaque.                            |
| data-background-video       |           | A single video source, or a comma separated list of video sources. |
| data-background-video-loop  | false     | Flags if the video should play repeatedly.                         |
| data-background-video-muted | false     | Flags if the audio should be muted.                                |
| data-background-size        | cover     | Use cover for full screen or contain for letterboxing.             |
| data-background-opacity     | 1         | 0 is transparent and 1 is fully opaque.                            |
| data-background-iframe      |           | URL of the iframe to load                                          |
| data-background-interactive | false     | Make it possible to interact with the iframe contents.             |

Use `backgroundTransition` to set background transition.  

If you want to use a parallax scrolling background configure it when initializing reveal.js

#### Code

Simple example

```html
<section>
  <pre><code data-trim data-noescape>
  (def lazy-fib
    (concat
    [0 1]
    ((fn rfib [a b]
      (lazy-cons (+ a b) (rfib b (+ a b)))) 0 1))
  )
  </code></pre>
</section>
```

Note :

- data-trim: surrounding whitespace within the `<code>` is automatically removed
- data-noescape: defines a regular expression for horizontal slides

#### Theming

Simple example

```html
<link rel="stylesheet" href="lib/css/monokai.css">
<script src="plugin/highlight/highlight.js"></script>
<script>
  Reveal.initialize({
    plugins: [ RevealHighlight ]
  });
</script>
```

Line Numbers & Highlights & Step-by-setp

To highlight code use data-line-numbers.  
To use step by step put a `|` betweend each lines

```html
<pre><code data-line-numbers="3-5|8-10|13-15">
<table>
  <tr>
    <td>Apples</td>
    <td>$1</td>
    <td>7</td>
  </tr>
  <tr>
    <td>Oranges</td>
    <td>$2</td>
    <td>18</td>
  </tr>
  <tr>
    <td>Kiwi</td>
    <td>$3</td>
    <td>1</td>
  </tr>
</table>
</code></pre>
```

#### Fragment

Simple example

```html
<p class="fragment">Fade in</p>
<p class="fragment fade-out">Fade out</p>
<p class="fragment highlight-red">Highlight red</p>
<p class="fragment fade-in-then-out">Fade in, then out</p>
<p class="fragment fade-up">Slide up while fading in</p>
```

| Name                    | Effect                                              |
| :---------------------- | :-------------------------------------------------- |
| fade-out                | Start visible, fade out                             |
| fade-up                 | Slide up while fading in                            |
| fade-down               | Slide down while fading in                          |
| fade-left               | Slide left while fading in                          |
| fade-right              | Slide right while fading in                         |
| fade-in-then-out        | Fades in, then out on the next step                 |
| fade-in-then-semi-out   | Fades in, then to 50% on the next step              |
| grow                    | Scale up                                            |
| shrink                  | Scale down                                          |
| strike                  | Strike through                                      |
| highlight-red           | Turn text red                                       |
| highlight-green         | Turn text green                                     |
| highlight-blue          | Turn text blue                                      |
| highlight-current-red   | Turn text red, then back to original on next step   |
| highlight-current-green | Turn text green, then back to original on next step |
| highlight-current-blue  | Turn text blue, then back to original on next step  |

Nested Fragments

```html
<span class="fragment fade-in">
  <span class="fragment highlight-red">
    <span class="fragment fade-out">
      Fade in > Turn red > Fade out
    </span>
  </span>
</span>
```

Fragments order

```html
<p class="fragment" data-fragment-index="3">Appears last</p>
<p class="fragment" data-fragment-index="1">Appears first</p>
<p class="fragment" data-fragment-index="2">Appears second</p>
```

#### Links

```html
<section>
  <a href="#/grand-finale">Go to the last slide</a>
</section>
<section>
  <h2>Slide 2</h2>
</section>
<section id="grand-finale">
  <h2>The end</h2>
  <a href="#/0">Back to the first</a>
</section>
<section>
  <a href="#/2">Go to 2nd slide</a>
  <a href="#/3/2">Go to the 2nd vertical slide inside of the 3rd slide</a>
</section>
```

Simple example

#### Layout

Layout provide a few different helper classes for controlling the layout and styling your content.

- r-stack: The r-stack layout helper lets you center and place multiple elements on top of each other.
- r-fit-text: The r-fit-text class makes text as large as possible without overflowing the slide.
- r-stretch: The r-stretch layout helper lets you resize an element, like an image or video, to cover the remaining vertical space in a slide.

#### Slide Visibility

The data-visibility attribute can be used to hide slides.

```html
<section>Slide 1</section>
<section data-visibility="hidden">Slide 2</section>
<section>Slide 3</section>
<section>Slide 1</section>
<section>Slide 2</section>
<section data-visibility="uncounted">Slide 3</section>
```

## Customization

#### Themes

| Name      | Effect                                                |
| :-------- | :---------------------------------------------------- |
| black     | Black background, white text, blue links (default)    |
| white     | White background, black text, blue links              |
| league    | Gray background, white text, blue links               |
| beige     | Beige background, dark text, brown links              |
| sky       | Blue background, thin dark text, blue links           |
| night     | Black background, thick white text, orange links      |
| serif     | Cappuccino background, gray text, brown links         |
| simple    | White background, black text, blue links              |
| solarized | Cream-colored background, dark green text, blue links |
| blood     | Dark background, thick white text, red links          |
| moon      | Dark blue background, thick grey text, blue links     |

#### Transitions

Simple example

```html
<section data-transition="zoom">
  <h2>This slide will override the presentation transition and zoom!</h2>
</section>

<section data-transition-speed="fast">
  <h2>Choose from three transition speeds: default, fast or slow!</h2>
</section>
```

Backgrounds Transitions

```js
Reveal.initialize({
  backgroundTransition: 'slide'
});
```

| Name     | Effect                                                                   |
| :------- | :----------------------------------------------------------------------- |
| -none    | Switch backgrounds instantly                                             |
| -fade    | Cross fade — default for background transitions                          |
| -slide   | Slide between backgrounds — default for slide transitions                |
| -convex  | Slide at a convex angle                                                  |
| -concave | Slide at a concave angle                                                 |
| -zoom    | Scale the incoming slide up so it grows in from the center of the screen |

#### Configuration Options

See [Configuration Options](https://revealjs.com/config/)

#### Presentation Size

We can customize presentation layout

```js
Reveal.initialize({
  width: 960,
  height: 700,
  margin: 0.04,
  minScale: 0.2,
  maxScale: 2.0,
  center: false
});
```

## Features

#### Vertical Slides

Simple example

```html
<section>Horizontal Slide</section>
<section>
  <section>Vertical Slide 1</section>
  <section>Vertical Slide 2</section>
</section>
```

Navigation mode can be tuned by setting `navigationMode` config option

- default
- linear
- grid

#### Auto-Animate

reveal.js can automatically animate elements across slides. All you need to do is add data-auto-animate to two adjacent slide `<section>` elements and Auto-Animate will animate all matching elements between the two.

Complex example with highlighting code. For more information [](https://revealjs.com/auto-animate/)

```html
<section data-auto-animate>
  <ul>
    <li>Mercury</li>
    <li>Jupiter</li>
    <li>Mars</li>
  </ul>
</section>
<section data-auto-animate>
  <ul>
    <li>Mercury</li>
    <li>Earth</li>
    <li>Jupiter</li>
    <li>Saturn</li>
    <li>Mars</li>
  </ul>
</section>
```

```html
<section data-auto-animate>
  <pre data-id="code-animation"><code data-trim data-line-numbers>
    let planets = [
      { name: 'mars', diameter: 6779 },
    ]
  </code></pre>
</section>
<section data-auto-animate>
  <pre data-id="code-animation"><code data-trim data-line-numbers>
    let planets = [
      { name: 'mars', diameter: 6779 },
      { name: 'earth', diameter: 12742 },
      { name: 'jupiter', diameter: 139820 }
    ]
  </code></pre>
</section>
<section data-auto-animate>
  <pre data-id="code-animation"><code data-trim data-line-numbers>
    let circumferenceReducer = ( c, planet ) => {
      return c + planet.diameter * Math.PI;
    }

    let planets = [
      { name: 'mars', diameter: 6779 },
      { name: 'earth', diameter: 12742 },
      { name: 'jupiter', diameter: 139820 }
    ]

    let c = planets.reduce( circumferenceReducer, 0 )
  </code></pre>
</section>
```

#### Auto-Slide

Presentations can be configured to step through slides automatically, without any user input. To enable this you will need to specify an interval for slide changes using the autoSlide config option. The interval is provided in milliseconds.

```js
// Slide every five seconds
Reveal.initialize({
  autoSlide: 5000,
  loop: true
});
```

#### Speaker View

```html
<section>
  <h2>Some Slide</h2>

  <aside class="notes">
    Shhh, these are your private notes 📝
  </aside>
</section>
<section 
  data-markdown="example.md"
  data-separator="^\n\n\n"
  data-separator-vertical="^\n\n"
  data-separator-notes="^Note:">
# Title
## Sub-title

Here is some content...

Note:
This will only display in the notes window.
</section>
```

Create simple note

#### Slide Numbers

Simple example

```js
Reveal.initialize({ slideNumber: true });
</section>
```

Format

| Value | Description                                                           |
| :---- | :-------------------------------------------------------------------- |
| h.v   | Horizontal . Vertical slide number (default)                          |
| h/v   | Horizontal / Vertical slide number                                    |
| c     | Flattened slide number, including both horizontal and vertical slides |
| c/t   | Flattened slide number / total slides                                 |

#### PDF Export

Simple example  

```js
// http://localhost:8000/demo?print-pdf
Reveal.configure({
  showNotes: true,
  showNotes: 'separate-page',
  pdfMaxPagesPerSlide: 1,
  pdfSeparateFragments: false
});
```

#### Overview Mode

Press Esc button

#### Fullscreen Mode

Press F button

## Plugins

1. Include the plugin script in the document. (Some plugins may require styles as well.)
2. Tell reveal.js about the plugin by including it in the plugins array when initializing.

```html
<script src="plugin/markdown/markdown.js"></script>
<script>
  Reveal.initialize({
    plugins: [ RevealMarkdown ]
  });
</script>
```

## Source

[Docs: creating a theme](https://github.com/hakimel/reveal.js/blob/master/css/theme/README.md)
[Docs: highlight.js](https://highlightjs.org/static/demo/.)
[Docs: reveal.js](https://revealjs.com/)
[Plugins: Built-in](https://revealjs.com/plugins/#built-in-plugins)
[Plugins: Third Party Plugins](https://github.com/hakimel/reveal.js/wiki/Plugins,-Tools-and-Hardware)
