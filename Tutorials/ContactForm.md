#Creating a Contact Form

Today we will be making something like this....

![Contact Form](http://i.imgur.com/cWmD8dV.jpg "Contact Form")

When someone fills it out you will get sent an email with the information they put in the form.

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

Add a new section at the bottom for the `<form>` tag.

```css
form{
  width: 50%;
}
```

That is better right? Maybe we should centre it though?

We can make it automatically scale the margins to put it in the middle. To do that just add `margin: auto;` to your css file like below.

```css
form{
  width: 50%;
  margin: auto;
}
```

Much Better!

Next we are going to make it work :D

#Step Four : Hooking the form into a web service

[Formspree](https://formspree.io/) is a great open source tool that will send an email to you when someone submits your form to their web service.

1. We are going to add an `action` to the form so the form knows to send the information to the Formspree web service.
2. Then we will add some `name` attributes to the fields so that those fields come through in the emails from formspree.
3. Lastly we can add some custom attributes to do some cool things like cc in other email addresses, so that the whole team will get the email or maybe add a thank you page that a user would get redirected to.

###Step Four Part 1 : Form Action

The `action` attribute on a form determines where the data from the form is sent when the user clicks submit.

To do this add `action="https://formspree.io/your@email.com"` to your `<form...` opening tag.

So that it looks like this ...

```html
<form action="https://formspree.io/your@email.com">
```

Use one of your emails to start with and I will show you how to add other emails in Part 3.

### Step Four Part 2 : Name Attributes

Formspree will only be able to detect the fields that you have added `name` attributes to. So lets go through now and add them so we see them coming through in the emails.

Go through and add names you will be useful to you.

For example I think adding `name="Email"` to the email field would be quite useful.

eg. `<input type="text" class="form-control" placeholder="Email" name="Email">`

At this stage you can test the form to see if you get an email (make sure that you have used an email address you have access too right now). Try to submit the form and you will get directed to a page telling you to verify your email address, just follow their instructions and you should be fine.

At this point you should be all set XD

### Step Four Part 3 : Adding Extras

First lets add some more email addresses so that we all get them.

This can be done by adding another field to the form, only this field will be hidden so the user can't see it, but the information will still be passed to Formspree.

The example below will include the two email addressses another@email.com and yetanother@email.com. This works by cc'ing them in the email sent by Formspree.

```html
<input type="hidden" name="_cc" value="another@email.com,yetanother@email.com" />
```

You may also notice that when the user submits the form they will get sent to the Formspree website. We probably don't want that. So lets add some more hidden information to tell Formspree where to direct the user after they have submitted the form.

```html
<input type="hidden" name="_next" value="http://codegenie.tech" />
```

In the example above I have used `http://codegenie.tech`, but you could make your own Thank You page and use that instead if you felt so inclined.

One last thing you can do is tell Formspree what you want the subject of the email to be...

```html
<input type="hidden" name="_subject" value="CodeGenie User contacted you!" />
```

#Step Five : Finished

Done! Hopefully everything works and that wasn't too difficult. If you don't manage to complete it in todays session we will finish it off next week.

Otherwise here is the complete code

```html
<form action="https://formspree.io/your@email.com">
  <div class="row">
    <div class="col-lg-6"><input type="text" class="form-control" placeholder="Name" name="Name"></div>
    <div class="col-lg-6"><input type="text" class="form-control" placeholder="Email" name="Email"></div>
  </div>
  <br>
  <div class="row">
    <div class="col-lg-12">
    <textarea name="Message" rows="4" placeholder="Message" class="form-control"></textarea>
    </div>
  </div>
  <br>
  <input type="hidden" name="_cc" value="another@email.com,yetanother@email.com" />
  <input type="hidden" name="_next" value="http://codegenie.tech" />
  <input type="hidden" name="_subject" value="CodeGenie User contacted you!" />
  <input type="submit" value="Send" class="btn">
</form>
```

