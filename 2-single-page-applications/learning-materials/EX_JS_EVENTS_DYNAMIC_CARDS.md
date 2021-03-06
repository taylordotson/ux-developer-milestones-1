# Dynamic Cards

## Setup

These commands are a helpful quick start. You may choose to ignore them completely and create your own directory structure. If you choose to use this recommendation, just copy the commands below and paste. It doesn't matter what directory you are currently in.

```bash
mkdir -p ~/workspace/exercises/spa/cards && cd $_
touch index.html
touch cards.js
touch cards.css
```

## Instructions

1. Create an HTML page that contains a text area and a button labeled *Create*.
1. When the user enters in text into the text area and then clicks the create button, create a new card element in the DOM. You decide the height/width of the card.
1. When the user clicks the *Delete* button, the containing card, and no other cards, should then be removed from the DOM. Not just made invisible, actually [removed](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild) from the DOM.

### Notes

1. In order to know which delete button the user clicked on, each one **must** have a unique value in its `id` attribute.
1. Remember your factory and generator functions. Generator should yield a unique identifier. Factory should generate DOM string.
1. You can't attach an event listener to an element until it has been added to the DOM.

## Submit Your Exercise
Upon completion, [submit your exercise](http://bit.ly/NSSExerciseSubmission) for review.