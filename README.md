# Task Summary
My idea was to make a music news website using everything I had learnt in my first week of training.

## Layout Idea:

* Nav bar (*col-md-12*)
* Jumbotron Carousel (*col-md-12*)
* Thumbnails which link to other articles (*col-md-3*)
* Videos section (*col-md-6*)
* Footer Contact bar (*col-md-12*)

## Other pages Ideas:
* More Articles page
* More Videos page
* Reviews
* Best new Music

## HTML Layout

### nav bar
I decided to program the website by starting from the literal top. I made the navigation bar using W3Schools tutorial and the Bootstrap website. I wanted the user to have the option of having a fixed nav bar so they could navigate all over the website very easily. This was easily implement using the bootstrap class:
```HTML
<nav class="navbar navbar-default navbar-fixed-top">
```

I also used collapse method by making the nav bar mobile friendly:
```HTML
<button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
```

### carousel

I then moved on to the carousel. I used a W3Schools and Bootly to find code for a carousel which would mimic a news real from other websites. The carousel uses the bootstrap library to automatically run through the featured news on the website. It uses data targets to do this.

```HTML
<li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
<li data-target="#carousel-example-generic" data-slide-to="1"></li>
<li data-target="#carousel-example-generic" data-slide-to="2"></li>
```
I also added links to the seperate article page within the slide show to allow the user to read the story in one click.

### News Thumbnails

A bootstrap technique I used through my website and can be seen on the home page are thumbnails. They are a very easy tool to provide a neat block structure within rows. They are also very good at being responsive.

### Collapse Button

In my website I wanted the user to have the option to see more similar content by clicking a button, and then revealing more onto the page. After doing some research I found bootstrap button techniques which allowed me to do this.

```HTML
<div class="container  more-button">
<button type="button" class="btn btn-primary btn-block center-block btn-info" data-toggle="collapse" data-target="#more">Older news...</button>
<div id="more" class="collapse">
```

I'd place the button within the same container as the information/code I wanted the user to see. The data target targets the same ID references in the *div* of the the information needed to be revealed. the *data-toggle="collapse"* is also used to allow the collapse function to work.

## css

### Inspecting

Overriding bootstrap css was difficult at times, however I found the *Inspect* tool very useful when understanding what variable to target in the stylesheet. This worked most efficiently when styling the *navbar*, *buttons*, and *thumbnails*.

### @media
I mainly used the *@media* to make the content responsive for mobile devices, and control what content went where when the screen resized. This came very useful for the carousel:

```css
@media (min-width: 992px) {
	#myCarousel {padding-right:33.3333%;}
	#myCarousel .carousel-controls {display:none;}
}
@media (max-width: 991px) {
	.carousel-caption p,
	#myCarousel .list-group {display:none;}
}
```
I also used it for to maintain the space between the nav bar and Carousel:


```css
@media screen and (max-width: 768px) {
    body { padding-top: 100px; }
}

@media screen and (min-width: 768px) {
    body { padding-top: 220px; }
}
```

### Style and colour
When it came to the styling on my website, I wanted it to be similar to existing websites and keep it quite simple. I used a basic colour palette aquired online and used those same colours through the whole website. I wanted to use a simple font but not a default font. I decided to go on google fonts and found one called oxygen. I put the script in the head of the index.html:
```html
<link href="https://fonts.googleapis.com/css?family=Oxygen" rel="stylesheet">
```
I then put the appropriate CSS in the main body tag:
```css
body {
  padding-top: 19%;
  font-family: 'Oxygen', sans-serif;
  color: black;
  background: white;
}
```

## Methods to make page and items responsive:

There was a number of techniques I used to make the page and Items responsive.
One useful one I found was a piece of meta information you can place in the head of the HTML:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
```
This will help with the items fitting the width of the device the user is using.

Another technique I used was within the column bootstrap tag through the HTML:

```html
<div class="col-xs-12 col-md-6 col-lg-3 thumbnail">
```
Within this, I could control how many thumnail icons were on one row when the width is resized. In the example here there would be 4 on a row when large, 2 on a row when medium, and 1 on a row when on a phone device.

Things such as videos and Images had to be responsive as well. This was achieved with simple bootstrap classes such as *img-responsive* for images:

```HTML
<img src="./images/SNL Aziz Ansari.JPG" class="img-responsive"alt="">
```
and for the videos, giving it a unique class, and adjusting the width and height:
```CSS
.video-page{
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 80%;
  height: auto;
}
```
