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

### Adjacent Sibling Selector:

The **adjacent sibling selector (`+`)** is used to style an element that comes right after a specific element. Both of them must have the same parent, and "adjacent" means **immediately next to each other**.

#### Basic Syntax:

For example:

```html
<h2>Heading</h2>
<p>This paragraph is styled</p>
```

With this CSS:

```css
h2 + p {
  font-weight: bold;
}
```

The paragraph is styled because it directly follows and h2 element.

#### Example of Usage:

For this particular example, we will manipulate with the <i>adjacent sibling selector</i> to precisely target the first `<p>` element and style it to our likings. See below:

```html
<html>
<head>
    <title>Adjacent Sibling Selector</title>
    <style>
        h2 + p {
            color: blue;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <h2>Basketball Game Overview</h2>
    <p>The basketball game was an exciting match between the **Los Angeles Lakers** and the **Golden State Warriors**, featuring intense offense and solid defense from both teams.</p>
    
    <p>During the first half, the Lakers held a slight lead, with LeBron James making key plays, while Stephen Curry of the Warriors kept the game tight with impressive three-pointers.</p>
    
    <p>This paragraph is not directly after an h2, so it should not be affected.</p>
    
    <p>In the second half, the Warriors fought back, with Klay Thompson hitting critical shots, but the Lakers secured their win with solid defense and a game-winning dunk by Anthony Davis.</p>
</body>
</html>
```

##### Result:

![Adjacent Sibling Selector](Assets/Photos/Adjacent%20Sibling%20Selector.jpg)

### General Sibling Selector:

The **general sibling selector (`~`)** selects elements that are sibling of a specified element and come after it.

#### Basic Syntax:

For example:

```html
<div>
  <p>Paragraph 1</p>
  <h2>Heading</h2>
  <p>Paragraph 2</p>
  <p>Paragraph 3</p>
</div>
```

With this CSS:

```css
h2 ~ p {
    color: blue;
}
```

After applying this CSS, the result will be:

* Paragraph 1 remains unchanged (it's not a sibling that comes after h2).
* Paragraph 2 and 3 becomes blue (it's a sibling that comes after h2).

#### Example of Usage:

```html
<html>
<head>
    <title>General Sibling Selector</title>
    <style>
        h1 ~ p { color: #ff69b4; }
    </style>
</head>
<body>
    <h1>Welcome to the Party!</h1>
    <p>Grab a drink.</p>
    <p>Say hello to new friends.</p>
    <div>Dance floor area</div>
    <p>Take a selfie!</p>
    <p>Enjoy the snacks.</p>
</body>
</html>
```

##### Result:

![General Sibling Selector](Assets/Photos/General%20Sibling%20Selector.jpg)

### Recap - Selector Mastery + Combination:

We have learned how to combine CSS selectors using **descendant, child, adjacent sibling and general sibling** combinators.

* **Descendant Selector (`div p` for example)**: Used to target elements that are nested within other elements, for accuracy and precision.
* **Child Selector (`>`)**: For applying styles to elements that are direct children of another element.
* **Adjacent Sibling Selector (`+`)**: Used to style an element that comes right after a specific element.
* **General Sibling Selector (`~`)**: They select elements that are sibling of a specified element and come after it.

#### Example of a Webpage:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Recap Challenge</title>
    <style>
		.rooms > p { color: #40e0d0; }
		.facilities p { color: #2e8b57; }
		div + p, p { color: #f4a300; }
    </style>
</head>
<body>
    <section>
  		<h1>Welcome to Paradise Resort</h1>
  
  		<div class="rooms">
    		<h2>Ocean View Rooms</h2>
    		<p>Room 101</p>
    		<p>Room 102</p>
  		</div>

  		<div class="facilities">
    		<h2>Resort Facilities</h2>
    		<div>
      			<p>Infinity Pool</p>
      			<p>Spa & Wellness Center</p>
    		</div>
    		<p>Beach Access</p>
  		</div>

  		<p>Beachfront Restaurant</p>
  		<p>Sunset Bar</p>
  		
	</section>
</body>
</html>
```

##### Result:

![Recap - Selector Mastery](Assets/Photos/Recap%20-%20Selector%20Mastery.jpg)

## Interactive Pseudo-Classes:

### Pseudo-Classes:

Interactive pseudo-classes let you change the look of elements when users do things like move their mouse over them, click them, or select them. They help make your website feel more responsive and fun to use.

#### Basic Syntax:

The syntax of pseudo-classes:

```css
selector:pseudo-class {
  property: value;
}
```

