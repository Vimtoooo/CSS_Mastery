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