#Creating a Contact Form

For this we will be using a few new HTML Tags.

`<form>` - to define a form in a web page

`<input>` - to define an input

`<textarea>` - to define a large text input field

Pretty simple right?

#Lets get started!

#Step One : Make our Contact page pretty!

We are going to take our `Contact.html` and add the default elements to it like the navbar and the background. Start by copying everything from `index.html` and deleting everything we don't need.

I got rid of most things, but made sure to leave the below block of code to put the Contact Form in.

``` html
<div class="jumbotron">
  <h1 class="page-title">CodeGenie</h1>
  <p class="lead"></p>
</div>
```

#Step Two : Adding the basic form elements

Lets make a form :)

Put this into your `<Contact.html>` page right below the line `<p class="lead"></p>` in the jumbotron `<div>`.

``` html
<form>
  <input type="text" placeholder="Name">
  <input type="text" placeholder="Email">
  <textarea rows="4" placeholder="Message"></textarea>
  <input type="submit" value="Send">
</form>
```

How does that look?

Pretty ugly right?

