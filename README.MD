# CSS Mastery

## Selector Mastery - Combination:

### Introduction:

In the previous repository, we looked at basic selector like **tags, classes, IDs, group selectors**, and **the universal selector**. These gave you the tools to start styling elements on the page.

Now we're stepping things up a bit. In this chapter, you'll lern some smarter ways to target elements, like <i>how to style an element only if it's inside another, or right after another.</i>

These techniques make your CSS cleaner, more flexible and easier to manage as your projects grow.

### Descendant Selector:

The first selector is the **descendant selector**. We use it when we want to style elements tht are inside another element, even if they are deeply nested. For example, ther are two paragraphs inside a container:

```html
<div class="container">
    <p>This is a paragraph inside a div.</p>
    <section>
        <p>This is a paragraph inside a section that is inside a div.</p>
    </section>
</div>
```

#### Basic Syntax:

Now, let's use a descendant selector to style all paragraphs inside the div:

```css
.container p {
    color: blue;
}
```

All paragraphs inside the `.container` div will turn blue, even the one nested inside the `selection` element.

#### Example of Usage:

```html
<html>
<head>
    <title>Descendant Selector</title>
    <style>
        .navigation li { color: purple; }
    </style>
</head>
<body>
    <ul class="navigation">
        <li>Home</li>
        <li>Team
            <ul>
                <li>Players</li>
                <li>Coaches</li>
            </ul>
        </li>
        <li>Tickets</li>
    </ul>
</body>
</html>
```

##### Result:

![Descendant Selector](Assets/Photos/Descendant%20Selector.jpg)

### Child Selector:

The **child selector (`>`)** is used when we want to style elements that are direct children of another element. Unlike the descendant selector, it only selects direct children, not deeper ones.

#### Basic Syntax:

For example, take this HTML document:

```html
<div class="parent">
  <p>This is a direct child</p>
  <section>
    <p>This is a grandchild (not a direct child)</p>
  </section>
</div>
```

Apply styling to direct children only:

```css
.parent > p {
    color: red;
}
```

After applying this CSS, only the first paragraph "This is a direct child" will be red. The second paragragh won't be affected because it's not a direct child of the div with class `parent`.

#### Example of Usage:

```html
<html>
<head>
    <title>Child Selector</title>
    <style>
        .team-container > div {
            background-color: lightblue;
            padding: 10px;
            margin: 5px;
        }
        .team-container .team > h3 {
            color: green;
            font-size: 20px;
        }
    </style>
</head>
<body>
    <div class="team-container">
        <div class="team">
            <h3>Basketball Team</h3>
            <ul>
                <li>LeBron James</li>
                <li>Stephen Curry</li>
                <li>Kevin Durant</li>
            </ul>
        </div>
        <div class="team">
            <h3>Football Team</h3>
            <ul>
                <li>Tom Brady</li>
                <li>Patrick Mahomes</li>
                <li>Davante Adams</li>
            </ul>
        </div>
        <div class="team">
            <h3>Soccer Team</h3>
            <ul>
                <li>Lionel Messi</li>
                <li>Cristiano Ronaldo</li>
                <li>Neymar Jr.</li>
            </ul>
        </div>
    </div>
</body>
</html>
```

##### Result:

![Child Selector](Assets/Photos/Child%20Selector.jpg)