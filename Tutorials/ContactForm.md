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

#Step Three : Making it Stylish

Now we are going to do a few things...

1. Using the Bootstrap predefined classes to make the form look prettier. These are `form-control` to the form fields and `btn` to the submit button.
2. Using the Bootstrap grid system and some `<br>` tags to align the form fields so they are spaced out correctly.
3. Add some of our own CSS for final touches.

###Step Three Part 1 : New Classes 

If you like you can read up on how Bootstrap makes some nice forms [here](http://getbootstrap.com/css/#forms). Otherwise you can just try adding `class="form-control"` to each of the text inputs (`<input type="text" ...`).

You can also do the same for the `<textarea...` tag.

That should make the fields look a bit nicer. How about that button? Add `class="btn"` to the submit input (`<input type="submit"...`). Find out more about buttons and all the colours you can choose [here](http://getbootstrap.com/css/#buttons-options).

Not bad eh?

###Step Three Part 2 : Space it out! ALL THE DIVS!

Now to fix up all that spacing. This can get very fiddly and is a tad complicated, like I still don't know how a lot of it works. But its all documented [here](http://getbootstrap.com/css/#grid) if you want to know more.

Basically it enables you to divide the width into 12 parts and decide how many of those a element on the page should take up.

1. Move the name and email fields into a singe line using bootstraps `row` class.
2. Put each of the fields into their own `div` that will specify how wide they are.
3. Next we are going to add `<br>` tags to put some vertical spacing between the rows.

To save you the hassle, this is what your form should look like now...

```html
<form>
  <div class="row">
    <div class="col-lg-6"><input type="text" class="form-control" placeholder="Name"></div>
    <div class="col-lg-6"><input type="text" class="form-control" placeholder="Email"></div>
  </div>
  <br>
  <div class="row">
      <div class="col-lg-12">
      <textarea rows="4" placeholder="Message" class="form-control"></textarea>
      </div>
  </div>
  <br>
  <input type="submit" value="Send" class="btn">
</form>
```

###Step Three Part 3 : Final touches with custom CSS

Lastly we don't want the form taking up the whole width of the page. Lets fix that...

Open your `style.css` file to add some custom styling.

