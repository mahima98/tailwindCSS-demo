---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# Tailwind CSS

An introduction to tailwind css and
new features added to Tailwind CSS v3

Presented by Mahima Ramgolam

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# What is Tailwind CSS?

<br>

- ## CSS framework made up of utility classes
<br>

```html
<div class="text-red-100"></div>
<div class="px-4 py-2 mx-2"></div>
<div class="border border-r border-l-2"></div>
<button class="bg-red-500 hover:bg-red-600"></button>
<button class="sm:text-sm md:text-md lg:text-4xl"></button>
```

<br>

<img src="/padding.png" class="h-40 rounded shadow" />

<br>

- ## Much lower-level than Bootstrap, Materialize etc..
<br>
<br>

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

h2 {
  opacity: 75%;
}
</style>

# Example/

<div grid="~ cols-3 gap-4">
<div grid="col-span-2">

#### Desktop version

<img src="/desktopflex.png" class="h-40 rounded shadow" />

</div>
<div>

#### Mobile version

<img src="/mobileflex.png" class="h-40 rounded shadow" />

</div>
</div>

<br>
<br>

#### HTML

```html
<html>
  <body>
    <div class="wrapper">
      <button class="myButton">Hover me</button>
    </div>
  </body>
</html>
```

---

<div grid="~ cols-2 gap-4">
 
 <div>
 
 ## Using normal css

 <br>

```html
<style>
  .wrapper {
    display: flex;
    width: 100%;
    height: 150px;
    justify-content: center;
    align-items: center;
  }
  .myButton {
    padding: 10px 20px;
    background-color: rgb(101, 238, 220);
    border-radius: 10px;
    font-size: 25px;
  }
  .myButton:hover {
    background-color: rgb(13, 85, 85);
  }
  @media (max-width: 800px) {
    .myButton {
      padding: 8px 16px;
      background-color: pink;
      font-size: 16px;
    }
  }
</style>
```

 </div>

 <div>

## Using Tailwind Css

<br>

```html
<div class="flex w-full h-[150px] justify-center items-center">
  <button
    class="px-4 py-2 md:px-8 md:py-4 bg-red-300 rounded-md hover:bg-teal-400 md:bg-blue-200 md:text-xl"
  >
    Hover me
  </button>
</div>
```

 </div>
</div>

---

## Modifiers

Tailwind includes modifiers for just about everything you’ll ever need, including:

- **Pseudo-classes**, like :hover, :focus, and :first-child
- **Pseudo-elements**, like ::before, ::after, ::placeholder, and ::selection
- **Media queries**, like responsive breakpoints, dark mode.
  These modifiers can even be stacked to target more specific situations.

<div grid="~ cols-2 gap-4">
<div>

```html
//using tailwind

<button class="md:hover:first-child:text-purple-600 text-black">
  Save changes
</button>
```

</div>

<div>

```html
//using traditional css
<style>
  .myButton {
    color: black;
  }
  @media (max-width: 800px) {
    .myButton:hover:first-child {
      padding: 8px 16px;
      background-color: purple;
    }
  }
</style>
```

</div>
</div>

---

# Live Demo

##### Construct a simple page using commonly used features( Grid / flex)

<br>

<img src="/demolive.jpg" class="h-100 rounded shadow" />

---

# New features added to tailwind

<br>

- ## Color box shadow utilities
- ## Fancy underline styles
- ## Multi-column layout
- ## Portrait and landscape mode
- ## Just-in-Time (JIT) engine

<style>
  h1 {
    text-decoration: underline;
  }

  h2 {
    margin-bottom: 4px;
  }

</style>

---

# Color box shadow utilities

Use the shadow-{color} utilities to change the color of an existing box shadow. By default colored shadows have an opacity of 100%, but you can adjust this using the opacity modifier. [Learn more](https://tailwindcss.com/docs/box-shadow-color#setting-the-box-shadow-color)

<br>

  <img src="/shadow.png" class="h-30 rounded shadow" />
  <br>

```html
<button class="bg-cyan-500 shadow-lg shadow-cyan-500/50 ...">Subscribe</button>
<button class="bg-blue-500 shadow-lg shadow-blue-500/50 ...">Subscribe</button>
<button class="bg-indigo-500 shadow-lg shadow-indigo-500/50 ...">
  Subscribe
</button>
```

---

# Fancy underline styles

Now you can change underline colors, thickness, and more:

<img src="/fancy.png" class="h-15 rounded" />

```html
<p>
  I’m Mahima, a frontend developer based in Mauritius. Currently am doing a demo
  on
  <a href="#" class="underline decoration-sky-500 decoration-2">Tailwind CSS.</a
  >. Now am in the section
  <a
    href="#"
    class="underline decoration-pink-500 decoration-dotted decoration-2"
    >Fancy underline style</a
  >
  and have
  <a
    href="#"
    class="underline decoration-indigo-500 decoration-wavy decoration-2"
    >portrait and landscape mode</a
  >
  next.
</p>
```

---

# Multi-column layout

Use as the newspaper layout kind. These are actually super useful, and are great for things like footer navigation layouts too.

<div grid="~ cols-2 gap-8">
<div>
<img src="/multicolumn.png" class="h-70 rounded shadow" />
</div>
<div>

```html
<div class="columns-2 sm:columns-3">
  <p>...</p>
  <!-- ... -->
</div>
```

</div>
  </div>

---

# Portrait and landscape modifiers

Use the new portrait and landscape modifiers to conditionally add styles when the viewport is in a specific orientation:

```html
<div>
  <div class="portrait:hidden">
    <!-- ... -->
  </div>
  <div class="landscape:hidden">
    This experience is designed to be viewed in landscape. Please rotate your
    device to view the site.
  </div>
</div>
```

##### using normal CSS

<div grid="~ cols-2 gap-8">
<div>

```html
<style>
  @media (orientation: landscape) {
    body {
      flex-direction: row;
    }
  }
</style>
```

</div>
<div>

```html
<style>
  @media (orientation: portrait) {
    body {
      flex-direction: column;
    }
  }
</style>
```

</div>
</div>

<style>
  h5 {
    font-size: 12px;
  }
  </style>

---

# Just-in-Time (JIT) engine

The new engine generates the styles you need for your project on-demand, and might necessitate some small changes to your project depending on how you have Tailwind configured.

taiwind.config.js

```html
module.exports = { mode: 'jit', // ... }
```

<br>

- #### **Lightning fast build times.**
- #### **Every variant is enabled out of the box.** Variants like focus-visible, active, disabled
- #### **Generate arbitrary styles without writing custom CSS** ultra specific value can be applied ex. `top-[-113px]`
<br>

<br>
<br>

### Examples

```html
<div class="text-[#FF0000] top-[-113px] w-[4rem]"></div>
```

---

# why use Tailwind CSS?

- ## It is Highly Customizable.
- ## It Has Common Utility Patterns.
- ## It Enables Building Complex Responsive Layouts Freely.
- ## Just in Time engine. (JIT mode)

<style>
h2 {
  margin-bottom: 6px;
}
</style>

---

# Thank youu.
