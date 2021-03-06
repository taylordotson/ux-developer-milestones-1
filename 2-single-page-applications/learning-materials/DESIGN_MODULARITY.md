# Introduction to Modularity

Modularity is the root concept behind all modern development. It's the practical application of the DRY principle. Keeping your code DRY is easy when you modularize it. It also makes a large code base easily manageable for a team of developers.

## Splitting JavaScript into Different Files

Up to this point in the course, you've had a single JavaScript file for each of the exercises you've worked on. The first step in modularity is to start making different JavaScript files that contain code for a specific domain of the application.

For example, you may have code for building your database and getting information out of it, as well as code that deals with making your data available in the DOM for human beings to consume. To modularize this code, you take all code that deals with the database and put it in one file, and the DOM manipulation code in a different one.

> databaseFactory.js

```js
const FlowerDatabase = [
    {
      "id": 1,
      "commonName": "Rose",
      "species": ["Hulthemia", "Hesperrhodos", "Platyrhodon", "Gymnocarpae"]
    },
    {
      "id": 2,
      "commonName": "Daisy",
      "species": ["Aster breweri", "Aster chezuensis", "Aster protoflorian", "Gymnocarpae"]
    }
];

const getFlower = function (id) {
    return FlowerDatabase.filter((flower) => flower.id === id)
}
```

> domController.js

```js
// Use a method defined in a different JavaScript module
const flower = getFlower(1)

// Update the DOM
document.getElementById("currentFlower").innerHTML = `${flower.commonName}`;
```

## Splitting CSS into Different Files

Likewise, modularizing your CSS code achieves the same goals of easier maintenance, DRY code, and flexibility.

Imagine that you have CSS classes for common page elements in a multi-page web site. Instead of having a monolithic CSS file for each page where the common styles are duplicated, you would break them out into smaller files that can be included in each page, and eliminating that duplicated CSS.

> layout.css

```css
body {
  font-size: 1.1em;
  color: DarkSlateGray;
}

footer {
  font-size: 0.75em;
  line-height: 0.9em;
}
```

> navigation.css

```css
nav {
  margin: 0 0 20px 0;
}
```

> home.css

```css
/* Here you place classes that ONLY apply to the home page */
.aboutMe {
  font-size: 1.4em;
  font-weight: bold;
}
```

Then, for each HTML page of your site, you include each CSS file.

```html
<html>
  <head>
    <title>My Web Site - Home Page</title>
    <link href="./styles/layout.css" rel="stylesheet"></link>
    <link href="./styles/navigation.css" rel="stylesheet"></link>
    <link href="./styles/home.css" rel="stylesheet"></link>
  </head>

  <body>
    <nav>
      <ul>
        <li>Home</li>
        <li>Resume</li>
        <li>Projects</li>
      </ul>
    </nav>

    <article class="aboutMe">
      I am a student at Nashville Software School
    </article>
  </body>
</html>
```
