# Live Code

## Learning from my coach live code

In this instance TDD is not being practiced.

Use the README.md as a working document.

A tracking pixel is a logger that tracks when people are visiting a particular site.

It lets us know which parts of the website are visited by who and how often.

Can break down user stories into even smaller user stories.

Builds the html in the elements tab in google chrome.

Right click on the elements to edit the html.

Writing jquery in pure javascript in the console:

```javascript
var button = document.getElementById('create_button')
button.addEventListener('click', function(){
  console.log('hello')
})
```

Then copies that html and javascript into files on the local machine.

Always make sure you load the script after the page has loaded.

If your script works in the console, and not when loaded, this is likely the error, the code is not executing at the right time.

Two ways to fix it:

1. Move script tags to the bottom of the html. - This is not ideal as it only starts loading after everything else has loaded.
2. Use the following code in your .js file with all your own code in the middle.
```javascript
window.onload = function() {

  \\ put your js code in here

}
```

You can grab the value inside a text area using the following code:

```javascript
var textarea = document.getElementById('note_text')
var noteText = textarea.value
```

If you want to print it to the screen you need a container to print it in. E.g.

```html
<div id="notes"></div>
```
Then add the following to the js code:
```javascript
var container = document.getElementById('notes')
container.innerText = noteText
```

At this point the js code is put into a file called interface.js and a new file called notes.js is created.

note.js
```javascript
function Note(txt) {
  this.text
}

Note.prototype.toDOMElement() {

}
```


and interface.js is updated to:

interface.js
```javascript
window.onload = function() {

  var button = document.getElementById('create_button')
  button.addEventListener('click', function(){
    var textarea = document.getElementById('note_text')
    var noteText = textarea.value 

    // create note with text

    // get container
    var container = document.getElementById('notes')

    // ad the note's DOM element to the container
    container.appendChild(note.toDOMElement())
  })
}
```

Then

note.js
```javascript
function Note(txt) {
  this.text
}

Note.prototype.toDOMElement() {
  var paragraph = document.createElement('p')
  paragraph.innerText = this.text
}
```

Components have states and they know things about displaying themselves. The view on the server is more about which route.

You don't have to use the MVC model, in this situation note.js is not a model, but a compenent.
Each component is a UI component.
The goal of a component is to know what data it needs and what to show.

Uses console.log to get visibilty when an error comes up. The problem is that we forgot to return in the function. New problem arises and continues using console.log to get visibilty.

note.js becomes
```javascript
function Note(txt) {
  this.text = text
}

Note.prototype.toDOMElement() {
  var paragraph = document.createElement('p')
  paragraph.innerText = this.text
  return paragraph
}
```

and then this in order to cut the string length to 20

note.js becomes
```javascript
function Note(txt) {
  this.text = text
}

Note.prototype.toDOMElement() {
  var paragraph = document.createElement('p')
  paragraph.innerText = this.text.substring(0, 20) + '...'
  return paragraph
}
```

When you work on react.js the framework library takes over the interface.