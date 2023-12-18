## [Week 7](https://github.com/SkillDistillery/SD41/blob/main/java1/README.md)

### Web 101

#### Internet Basics
#### Clients and Servers
#### URIs and URLs
#### HTTP: Hypertext Transfer Protocol
#### Lab - Viewing Requests

### HTML Basics

#### HTML
#### Hello World
#### HTML Attributes
#### Headings
#### HTML Forms
#### Labs

`helloWorld.html`

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1">
	 	<title>Hello World</title>
	</head>
	<body>
		<h1>Hello Deonna</h1>
		<h1>H1 Title</h1>
		<h2>H2 Title</h2>
		<h3>H3 Title</h3>
		<h4>H4 Title</h4>
		<h5>H5 Title</h5>
		<h6>H6 Title</h6>
	</body>
</html>
```

`helloWorld.html`

```html
<h1>Form #1</h1>
<form>
	<form action="helloWorld.html">
	<input type="text" name="firstName">
	<input type="submit" value="Submit First Name">
</form>

<br>

<h2>Form #2</h2>
<form>
	<form action="helloWorld.html">
	<input type="date" name="date">
	<input type="password" name="password">
	<input type="submit" value="Submit Date">
</form>
```

`Elements and Structure - codecademy.com`

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1">
	 	<title>Hello World</title>
	</head>
	<body>
  <h1>The Brown Bear</h1>
  <div id="introduction">
    <h2>About Brown Bears</h2>
    <p>The brown bear (<em>Ursus arctos</em>) is native to parts of northern Eurasia and North America. Its conservation status is currently <strong>Least Concern</strong>.<br /><br /> There are many subspecies within the brown bear species, including the Atlas bear and the Himalayan brown bear.</p>
    <h3>Species</h3>
    <ul>
      <li>Arctos</li>
      <li>Collarus</li>
      <li>Horribilis</li>
      <li>Nelsoni (extinct)</li>
    </ul>
    <h3>Features</h3>
    <p>Brown bears are not always completely brown. Some can be reddish or yellowish. They have very large, curved claws and huge paws. Male brown bears are often 30% larger than female brown bears. They can range from 5 feet to 9 feet from head to toe.</p>
  </div>
  <div id="habitat">
    <h2>Habitat</h2>
    <h3>Countries with Large Brown Bear Populations</h3>
    <ol>
      <li>Russia</li>
      <li>United States</li>
      <li>Canada</li>
    </ol>
    <h3>Countries with Small Brown Bear Populations</h3>
    <p>Some countries with smaller brown bear populations include Armenia, Belarus, Bulgaria, China, Finland, France, Greece, India, Japan, Nepal, Poland, Romania, Slovenia, Turkmenistan, and Uzbekistan.</p>
  </div>
  <div id="media">
    <h2>Media</h2>
    <img src="https://content.codecademy.com/courses/web-101/web101-image_brownbear.jpg" alt="A Brown Bear"/>
    <video src="https://content.codecademy.com/courses/freelance-1/unit-1/lesson-2/htmlcss1-vid_brown-bear.mp4" width="320" height="240" controls>Video Not Supported</video>
  </div>
</body>
</html>
```

```hmtl
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1">
	 	<title>Brown Bears</title>
	</head>

<body>
  <a href="./index.html">Brown Bear</a>
  <a href="./aboutme.html">About Me</a> <!--aboutme.html should be in same folder-->
  <h1>The Brown Bear</h1>
  
  <ul>
    <li><a href="#introduction">Introduction</a></li>
    <li><a href="#habitat">Habitat</a></li>
    <li><a href="#media">Media</a></li>
  </ul>
  
  <div id="introduction">
    <h2>About Brown Bears</h2>
    <p>The brown bear (<em>Ursus arctos</em>) is native to parts of northern Eurasia and North America. Its conservation status is currently <strong>Least Concern</strong>.<br /><br /> There are many subspecies within the brown bear species, including the
      Atlas bear and the Himalayan brown bear.</p>
    <a href="https://en.wikipedia.org/wiki/Brown_bear" target="_blank">Learn More</a>
    <h3>Species</h3>
    <ul>
      <li>Arctos</li>
      <li>Collarus</li>
      <li>Horribilis</li>
      <li>Nelsoni (extinct)</li>
    </ul>
    <h3>Features</h3>
    <p>Brown bears are not always completely brown. Some can be reddish or yellowish. They have very large, curved claws and huge paws. Male brown bears are often 30% larger than female brown bears. They can range from 5 feet to 9 feet from head to toe.</p>
  </div>
  <div id="habitat">
    <h2>Habitat</h2>
    <h3>Countries with Large Brown Bear Populations</h3>
    <ol>
      <li>Russia</li>
      <li>United States</li>
      <li>Canada</li>
    </ol>
    <h3>Countries with Small Brown Bear Populations</h3>
    <p>Some countries with smaller brown bear populations include Armenia, Belarus, Bulgaria, China, Finland, France, Greece, India, Japan, Nepal, Poland, Romania, Slovenia, Turkmenistan, and Uzbekistan.</p>
  </div>
  <div id="media">
    <h2>Media</h2>
    <a href="https://en.wikipedia.org/wiki/Brown_bear" target="_blank"><img src="https://content.codecademy.com/courses/web-101/web101-image_brownbear.jpg" alt="A Brown Bear"/></a>
    <video src="https://content.codecademy.com/courses/freelance-1/unit-1/lesson-2/htmlcss1-vid_brown-bear.mp4" height="240" width="320" controls>Video not supported</video>
  </div>
</body>

</html>
```

`Tables - codecademy.com`

```html
<!DOCTYPE html>
<html>
<head>
  <title>Ship To It - Company Packing List</title>
  <link href="https://fonts.googleapis.com/css?family=Lato: 100,300,400,700|Luckiest+Guy|Oxygen:300,400" rel="stylesheet">
  <link href="style.css" type="text/css" rel="stylesheet">
</head>
<body>

  <ul class="navigation">
    <li><img src="https://content.codecademy.com/courses/web-101/unit-9/htmlcss1-img_logo-shiptoit.png" height="20px;"></li>
    <li class="active">Action List</li>
    <li>Profiles</li>
    <li>Settings</li>
  </ul>

  <div class="search">Search the table</div>

  <table>
    <thead>
    <tr>
      <th scope='col'>Company Name</th>
      <th scope='col'>Number of Items to Ship</th>
      <th scope='col'>Next Action</th>
    </tr>
    </thead>
    <tbody>
    <tr>
      <td>Adam's Greenworks</td>
      <td>14</td>
      <td>Package Items</td>
    </tr>
    <tr>
  <td>Davie's Burgers</td>
  <td>2</td>
  <td>Send Invoice</td>
</tr>
<tr>
  <td colspan="2">Baker's Bike Shop</td>
  <td>3</td>
  <td>Send Invoice</td>
</tr>
<tr>
  <td rowspan="2">Miss Sally's Southern</td>
  <td>4</td>
  <td>Ship</td>
</tr>
<tr>
  <td>Summit Resort Rentals</td>
  <td>4</td>
  <td>Ship</td>
</tr>
<tr>
  <td>Strike Fitness</td>
  <td>1</td>
  <td>Enter Order</td>
</tr>
</tbody>
<tfoot>
    <tr>
      <th>Total</th>
      <td>28</td>
    </tr>
  </tfoot>
  </table>
</body>
</html>
```

```html
<!--style.css-->
body {
  background: #EEE;
  margin: 0;
  padding: 0;
}

/* Navigation */

.navigation {
  box-sizing: border-box;
  background-color: #3587A4;
  overflow: auto;
  padding: 18px 50px;
  position: relative;
  top: 0;
  width: 100%;
  z-index: 999;
}

ul {
  padding: 0;
  margin: 0;
}

li {
  color: #FFF;
  display: inline-block;
  font-family: 'Oxygen', sans-serif;
  font-size: 16px;
  font-weight: 300;
  letter-spacing: 2px;
  margin: 0;
  padding: 20px 18px 10px 18px;
  text-transform: uppercase;
}

.active {
  color: #88CCF1;
}

/* Table */

table {
  height: 40%;
  left: 10%;
  margin: 20px auto;
  overflow-y: scroll;
  position: static;
  width: 80%;
}

thead th {
  background: #88CCF1;
  color: #FFF;
  font-family: 'Lato', sans-serif;
  font-weight: 100;
  letter-spacing: 2px;
  text-transform: uppercase;
}

tr {
  background: #f4f7f8;
  border-bottom: 1px solid #FFF;
  margin-bottom: 5px;
}

th, td {
  font-family: 'Lato', sans-serif;
  font-weight: 400;
  padding: 18px;
  text-align: left;
  width: 33.3333%;
}

.search {
  background-color: #FFF;
  border: 1px solid #DDD;
  border-radius: 3px;
  color: #AAA;
  padding: 20px;
  margin: 50px auto 0px auto;
  width: 77%;
}
```

`Forms - codecademy.com`

```html
<!--Text Input-->
<form action="/example.html" method="POST">
  <input type="text" name="first-text-field">
</form>

<!--Label-->
<form action="/example.html" method="POST">
  <label for="meal">What do you want to eat?</label>
  <br>
  <input type="text" name="food" id="meal">
</form>

<!--Password-->
<form>
  <label for="user-password">Password: </label>
  <input type="password" id="user-password" name="user-password">
</form>

<!--Number-->
<form>
  <label for="years"> Years of experience: </label>
  <input id="years" name="years" type="number" step="1">
</form>

<!--Range-->
<form>
  <label for="volume"> Volume Control</label>
  <input id="volume" name="volume" type="range" min="0" max="100" step="1">
</form>

<!--Checkbox-->
<form>
  <p>Choose your pizza toppings:</p>
 
  <label for="cheese">Extra cheese</label>
  <input id="cheese" name="topping" type="checkbox" value="cheese">
 
  <br>
 
  <label for="pepperoni">Pepperoni</label>
  <input id="pepperoni" name="topping" type="checkbox" value="pepperoni">
 
  <br>
 
  <label for="anchovy">Anchovy</label>
  <input id="anchovy" name="topping" type="checkbox" value="anchovy">
</form>

<!--Radio Button-->
<form>
  <p>What is sum of 1 + 1?</p>
  
  <input type="radio" id="two" name="answer" value="2">
  <label for="two">2</label>
  
  <br>
  
  <input type="radio" id="eleven" name="answer" value="11">
  <label for="eleven">11</label>
</form>

<!--Dropdown List-->
<form>
  <label for="lunch">What's for lunch?</label>
  <select id="lunch" name="lunch">
    <option value="pizza">Pizza</option>
    <option value="curry">Curry</option>
    <option value="salad">Salad</option>
    <option value="ramen">Ramen</option>
    <option value="tacos">Tacos</option>
  </select>
</form>

<!--Datalist Input-->
<form>
  <label for="city">Ideal city to visit?</label>
  <input type="text" list="cities" id="city" name="city">

  <datalist id="cities">
    <option value="New York City"></option>
    <option value="Tokyo"></option>
    <option value="Barcelona"></option>
    <option value="Mexico City"></option>
    <option value="Melbourne"></option>
    <option value="Other"></option>  
  </datalist>
</form>

<!--Text Area-->
<form>
  <label for="blog">New Blog Post: </label>
  <br>
  <textarea id="blog" name="blog" rows="5" cols="30">
  </textarea>
</form>

<!--Submit Form-->
<form>
  <input type="submit" value="Send">
</form>

<!--Requiring an Input-->
<form action="/example.html" method="POST">
  <label for="allergies">Do you have any dietary restrictions?</label>
  <br>
  <input id="allergies" name="allergies" type="text" required>
  <br>
  <input type="submit" value="Submit">
</form>

<!--Set Min and Max-->
<form action="/example.html" method="POST">
  <label for="guests">Enter # of guests:</label>
  <input id="guests" name="guests" type="number" min="1" max="4">
  <input type="submit" value="Submit">
</form>

<!--Text Length-->
<form action="/example.html" method="POST">
  <label for="summary">Summarize your feelings in less than 250 characters</label>
  <input id="summary" name="summary" type="text" minlength="5" maxlength="250" required>
  <input type="submit" value="Submit">
</form>

<!--Match a Pattern-->
<form action="/example.html" method="POST">
  <label for="payment">Credit Card Number (no spaces):</label>
  <br>
  <input id="payment" name="payment" type="text" required pattern="[0-9]{14,16}">
  <input type="submit" value="Submit">
</form>

<label for="username">Username:</label>
<br>
<input id="username" name="username" type="text" required minlength="3" maxlength="15" pattern="[a-zA-Z0-9]+">
```

`Semantic HTML - codecademy.com`

```html
<!--Header and Nav-->
<header>
  <h1>
     Everything you need to know about pizza!
  </h1>
</header>

<header> 
  <nav>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>   
    </ul>
  </nav>
</header>

<!--Main and Footer-->
<main>
  <header>
    <h1>Types of Sports</h1>
  </header>
  <article>
    <h3>Baseball</h3>
    <p>
      The first game of baseball was played in Cooperstown, New York in the summer of 1839.
    </p>
  </article>
</main>

<footer>
  <p>Email me at Codey@Codecademy.com</p>
</footer>

<!--Article and Section-->
<section>
  <h2>Fun Facts About Cricket</h2> 
</section>

<section>
  <h2>Fun Facts About Cricket</h2>
  <article>
    <p>A single match of cricket can last up to 5 days.</p>
  </article>
</section>

<!--Aside Element-->
<article>
  <p>The first World Series was played between Pittsburgh and Boston in 1903 and was a nine-game series.</p>
</article>
<aside>
  <p>
   Babe Ruth once stated, “Heroes get remembered, but legends never die.” 
  </p>
</aside>

<!--Figure and Figcaption-->
<figure>
  <img src="overwatch.jpg">
</figure>

<figure>
  <img src="overwatch.jpg">
  <figcaption>This picture shows characters from Overwatch.</figcaption>
</figure>

<!--Audio Attributes-->
<audio>
  <source src="iAmAnAudioFile.mp3" type="audio/mp3">
</audio>

<!--Video and Embed-->
<video src="coding.mp4" controls>Video not supported</video>
<video src="coding.mp4" autoplay>Video not supported</video>
<video src="coding.mp4" loop>Video not supported</video>

<embed src="download.gif"/>

<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <header>
      <h1>Navigational Links</h1>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#posts">Posts</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>
    
    <main>
      <section>
        <article>
          <h2>Facts About Dogs</h2>
          <p>
          Dogs have a sense of time. It's been proven that they know the difference between a hour and five. If conditioned to, they can predict future events, such as regular walk times.
          </p>
        </article>
        <aside>
          <p>A study was conducted on dogs being away from their owners for varying hours and the studies show that dogs who were away from their owners the longest showed the greatest amount of affection!
          </p> 
        </aside>
      </section> 
      <figure>
        <img src="https://content.codecademy.com/courses/SemanticHTML/dogimage.jpeg"/>
        <figcaption>A cute dog.</figcaption>
      </figure>  
      <audio controls>
        <source src="https://content.codecademy.com/courses/SemanticHTML/dogBarking.mp3" type="audio/mp3">
      </audio> 
      <video src="https://content.codecademy.com/courses/SemanticHTML/dog-video.mp4" controls>
      </video>
      <embed src="https://content.codecademy.com/courses/SemanticHTML/dog-on-beach.gif"/>
         
    </main>
    
    <footer>
      <p>Contact me at +1 234 567 8910 </p>
    </footer>
              
  </body>
</html>
```

### [HTML Assessment](https://github.com/Deonnaa/HTMLAssessment)

### CSS - Cascading Style Sheets

#### CSS Basics
#### CSS Targeting: Selectors
#### Lab: CSS Hello World

`index.html`

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name = "viewport" content="
	width=device-width, initial-scale=1">
	<title> Hello World </title>
	<link rel="stylesheet" type="text/css" href="myStyles.css">
</head>
<body>
	<p class="font40">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
	<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
	<ul id="list1">
		<li>Elf</li>
		<li>The Polar Express</li>
		<li>Home Alone</li>
	</ul>
	<br>
	<ul id="list2">
		<li>Hous Pocus</li>
		<li>The Nightmare Before Christmas</li>
		<li>E.T. the Extra-Terrestrial</li>
	</ul>
	<h1 class="font40">Header1</h1>
	<h1 id="header2">Header2</h1>
</body>
<hmtl>
```

`myStyles.css`

```html
h1 {
color: red;
}

.font40 {
font-size: 40px;
}

#header2 {
color: #29c2d4;
}

#list1{
font-weight: bold;
}

#list2{
	font-family: cursive;
}
```

#### CSS Targeting: Specificity
#### The Cascade
#### CSS Targeting: More Selectors
#### The Box Model
#### Relative Positioning
#### Absolute Positioning
#### Fixed Positioning
#### Display Options
#### Floating Elements
#### Labs
#### Partial CSS Style Rules List

`Syntax and Selectors - codecademy`

```html
<!--Intro-->
<link href="style.css" rel="stylesheet">

<!--CSS Anatomy-->

<!--Inline Style-->
<p style='color: red;'>I'm learning to code!</p>
<p style='color: red; font-size: 20px;'>I'm learning to code!</p>

<!--Internal Stylesheet-->
<head>
  <style>
    p {
      color: red;
      font-size: 20px;
    }
  </style>
</head>

<!--External Stylesheet-->

<!--Linking CSS File-->
<link href='https://www.codecademy.com/stylesheets/style.css' rel='stylesheet'>
<link href='./style.css' rel='stylesheet'>

<!--Type-->
p {
  color: green;
}

<!--Universal-->
* { 
  font-family: Verdana;
}

<!--Class-->
<p class='brand'>Sole Shoe Company</p>

.brand {

}

<!--Multiple Classes-->
<h1 class='green bold'> ... </h1>

.green {
  color: green;
}

.bold {
  font-weight: bold;
}

<!--ID-->
<h1 id='large-title'> ... </h1>

#large-title {

}

<!--Attribute-->
<img src='/images/seasons/cold/winter.jpg'>
<img src='/images/seasons/warm/summer.jpg'>

img[src*='winter'] {
  height: 50px;
}

img[src*='summer'] {
  height: 100px;
}

[href]{
   color: magenta;
}

<!--Pseudo-class(not yet available)-->
a:hover {
color: darkorange;
}

a:focus {

}

a:visited {

}

a:disabled {

}

a:active {

}

<!--Classes and IDs(not yet available)-->
<h2 class='heading-background'>1. Florence, Italy</h2>
<h6 id="publish-time">Published: 2 Days Ago</h6>

.heading-background{
  background-color: aqua;
}

#publish-time{
  color: gray;
}

<!--Specificity(not yet available)-->
 <h5 class="author-class" id="author-id">By: Stacy Gray</h5>
 
 h5 {
  color: yellow;
}

.author-class {
  color: pink;
}

#author-id {
  color: cornflowerblue;
}

<!--Chaining(not yet available)-->
h1.special {

}

<!--Descendant Combinator(not yet available)-->
.main-list li {

}

.description h5 {
  color: blueviolet;
}

<!--Chaining and Specificity(not yet available)-->
p {
  color: blue;
}

.main p {
  color: red;
}

<!--Multiple Selectors-->
h1, .menu {
  font-family: Georgia;
}
```

`Visual Rules - codecademy`

```html
<!--Introduction To Visual Rules-->


<!--Font Family-->
h1 {
  font-family: 'Courier New';
}

<!--Font Size(not yet available)-->
p {
  font-size: 18px;
}

p {
  font-size: 100%;
}

<div style="font-size: 24px">
  <p>This text will be 24px, as inherited from the parent element</p>
  <p style="font-size: 0.7em">This text will be 70% of the parent size</p>
</div>

<!--Font Weight(not yet available)-->
p {
  font-weight: bold;
}

p {
  font-weight: normal;
}

<!--Text Align(not yet available)-->
h1 {
  text-align: right;
}

h1 {
  text-align: left;
}

h1 {
  text-align: center;
}

h1 {
  text-align: justify;
}

<!--Color and Background Color(not yet available)-->
h1 {
  color: red;
  background-color: blue;
}

<!--Opacity(not yet available)-->
.overlay {
  opacity: 0.5;
}

<!--Background Image(not yet available)-->
.main-banner {
  background-image: url('https://www.example.com/image.jpg');
}

.main-banner {
  background-image: url('images/mountains.jpg');
}

.image {
  background-image: url("https://content.codecademy.com/courses/freelance-1/unit-2/soccer.jpeg");
  background-size: cover;
  background-position: center;
  height: 300px;
}

<!--Important(not yet available)-->
p {
  color: blue !important;
}

.main p {
  color: red;
}
```

`The Box Model - codecademy`

```html
<!--Introduction to the Box Model-->


<!--The Box Model-->


<!--Height and Width-->
p {
  height: 80px;
  width: 240px;
}

<!--Borders(not yet available)-->
p {
  border: 3px solid coral;
}

p {
  border: 3px solid white;
}

p {
  border: 1px dotted red;
}

<!--Border Radius(not yet available)-->
div.container {
  border: 3px solid blue;
  border-radius: 5px;
}

div.container {
  height: 60px;
  width: 60px;
  border: 3px solid blue;
  border-radius: 50%;
}

<!--Padding(not yet available)-->
p.content-header {
  border: 3px solid coral;
  padding: 10px;
}

padding-top: 10px;
padding-right: 10px;
padding-bottom: 10px;
padding-left: 10px;

<!--Padding Shorthand(not yet available)-->
p.content-header {
  padding: 6px 11px 4px 9px;
}

p.content-header {
  padding: 5px 10px 20px;
}

p.content-header {
  padding: 5px 10px;
}

<!--Margin(not yet available)-->
p {
  border: 1px solid aquamarine;
  margin: 20px;
}

margin-top: 20px;
margin-right: 20px;
margin-bottom: 20px;
margin-left: 20px;

<!--Margin Shorthand(not yet available)-->
p {
  margin: 6px 10px 5px 12px;
}

p {
  margin: 5px 12px 4px;
}

p {
  margin: 20px 10px;
}

<!--Auto(not yet available)-->
div.headline {
  width: 400px;
  margin: 0 auto;
}

<!--Margin Collapse(not yet available)-->
<!--20+20-->
#img-one {
  margin-right: 20px;
}

#img-two {
  margin-left: 20px;
}

<!--30-->
#img-one {
  margin-bottom: 30px;
}

#img-two {
  margin-top: 20px;
}

<!--Minimum and Maximum Height and Width(not yet available)-->
p {
  min-width: 300px;
  max-width: 600px;
}

p {
  min-height: 150px;
  max-height: 300px;
}

<!--Overflow(not yet available)-->
p {
  overflow: scroll; 
}

overflow: hidden; 
overflow: scroll; 
overflow: visible; 

<!--Resetting Defaults(not yet available)-->
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

<!--Visibility-->
.future {
  visibility: hidden;
}

<!--hidden — hides an element.-->
<!--visible — displays an element.-->
<!--collapse — collapses an element.-->
```

```html
body {
  background-color: white;
  font-family: 'Raleway', sans-serif;
  margin: 0;
  padding: 0;
}

.navigation ul {
  margin: 0;
  padding: 0;
  text-align: center;
}

.navigation li {
  font-weight: 100;
  letter-spacing: 2px;
  padding: 20px;
}

.navigation  li.logo {
  color: black;
  font-size: 18px;
  font-weight: 700;
  letter-spacing: 4px;
}

.donate{
  visibility: hidden;
}

#banner {
  background-image: url("https://content.codecademy.com/courses/web-101/unit-6/htmlcss1-img_tahoe.jpeg");
  background-size: cover;
  background-position: bottom center;
  height: 700px;
  width: 100%;
}

#banner .content h1 {
  border: 3px solid white;
  position: relative;
  top: 50px;
  width: 400px;
  margin: 0 auto;
}

#main {
  margin: 0 auto;
  padding: 40px;
  text-align: center;
  width: 400px;
  height: 1000px;
  overflow: scroll;
}

h1 {
  color: white;
  font-size: 42px;
  font-weight: 600;
  text-align: center;
}

h2 {
  border: 1px dotted red;
  color: red;
  font-size: 14px;
  line-height: 48px;
  padding: 20px 30px;
  margin: 30px 20px;
  text-align: center;
}

h3 {
  color: red;
  font-size: 26px;
  font-weight: 700;
  padding: 20px 10px;
}

p {
  color: grey;
  font-size: 16px;
  line-height: 48px;
  margin-top: 60px;
  padding: 10px 20px;
}

.pull-quote {
  margin: 0 auto;
  width: 400px;
}

.byline {
  border-bottom: 1px solid LightGrey;
  border-top: 1px solid LightGrey;
  color: DarkGrey;
  font-size: 14px;
  font-weight: 200;
}

.share {
  border: 1px solid LightGrey;
  padding: 40px 0px;
  position: relative;
  text-align: center;
  width: 100%;
}

.share a {
  background: red;
  border: 1px solid red;
  border-radius: 3px;
  color: white;
  display: inline-block;
  margin: 10px;
  padding: 14px;
  text-decoration: none;
}

.share a:hover {
  background: white;
  border: 1px solid red;
  color: red;
}


!DOCTYPE html>
<html>
<head>
  <title>The Terminal - Your Source for Fact-Based News</title>
  <link href="https://fonts.googleapis.com/css?family=Amatic+SC|Raleway:100,200,600,700" rel="stylesheet">
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <nav class="navigation">
    <ul>
      <li>LOCAL</li>
      <li>NATIONAL</li>
      <li class="logo">THE TERMINAL</li>
      <li>GLOBAL</li>
      <li>OPED</li>
      <li class="donate">DONATE</li>
    </ul>
  </nav>

  <div id="banner">
    <div class="content">
      <h1>Conservation Efforts at Lake Tahoe Being Praised by Nation's Leaders</h1>
    </div>
  </div>

  <div id="main" class="content">
    <h3>THE STATE'S LATEST CONSERVATION EFFORTS ARE BEING HERALDED BY NATION'S TOP LEADERS AS GROUNDBREAKING AND FORWARD THINKING.</h3>
    <span class="byline">WRITTEN BY: JAMES JAYCE</span>
    <p>Until recently, construction on the banks of the Lake had been largely under the control of real estate developers. Construction activities have resulted in a clouding of the lake's blue waters. Currently, the Tahoe Regional Planning Agency is regulating construction along the shoreline and has won two Federal Supreme Court battles over recent decisions. These regulations are unpopular with many residents, especially those in the Tahoe Lakefront Homeowners Association.</p>

    <p>The League to Save Lake Tahoe (Keep Tahoe Blue) has been an environmental watchdog in the Lake Tahoe Basin for 50 years. Founded when a proposal to build a four-lane highway around the lake (with a bridge over the entrance to Emerald Bay) was proposed in 1957, the League has thwarted poorly designed development projects and environmentally unsound planning. The League embraces responsible and diversified use of the Lake's resources while protecting and restoring its natural attributes.</p>

    <div class="pull-quote">
      <h2>"THE LEAGUE EMBRACES RESPONSIBLE AND DIVERSIFIED USE OF THE LAKE'S RESOURCES WHILE PROTECTING AND RESTORING ITS NATURAL ATTRIBUTES"</h2>
    </div>

    <p>Since 1980, the Lake Tahoe Interagency Monitoring Program (LTIMP) has been measuring stream discharge and concentrations of nutrients and sediment in up to 10 tributary streams in the Lake Tahoe Basin, California-Nevada. The objectives of the LTIMP are to acquire and disseminate the water quality information necessary to support science-based environmental planning and decision making in the basin. The LTIMP is a cooperative program with support from 12 federal and state agencies with interests in the Tahoe Basin. This data set, together with more recently acquired data on urban runoff water quality, is being used by the Lahontan Regional Water Quality Control Board to develop a program (mandated by the Clean Water Act) to limit the flux of nutrients and fine sediment to the Lake.</p>

    <p>UC Davis remains a primary steward of the lake. The UC Davis Tahoe Environmental Research Center is dedicated to research, education and public outreach, and to providing objective scientific information for restoration and sustainable use of the Lake Tahoe Basin. Each year, it produces a well-publicized "State of the Lake" assessment report.</p>
  </div>

  <div class="share">
    <a href="#">SHARE</a>
    <a href="#">FAVORITE</a>
    <a href="#">READ</a>
  </div>

</body>
</html>
```

`The Box Model - codecademy`

```html
<!--Why Change the Box Model?-->


<!--Box Model: Content-Box-->


<!--Box Model: Border-Box(not yet available)-->
<h1>Hello World</h1>

* {
  box-sizing: border-box;
}

h1 {
  border: 1px dashed #4f768e;
  height: 150px;
  width: 200px;
  padding: 20px;
}

<!--The New Box Model-->

```

`Display and Positioning - codecademy`

```html
<!--Flow of HTML-->


<!--Position-->
.question {
  text-align: center;
  position: static;
}

position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;

<!--Position: Relative(not yet available)-->
.green-box {
  background-color: green;
  position: relative;
}

.green-box {
  background-color: green;
  position: relative;
  top: 50px;
  left: 120px;
}

top: 50px;
bottom: 50px;
left: 50px;
right: 50px;

<!--Position: Absolute(not yet available)-->
header {
  background-color: #466995;
  border-bottom: 1px solid #466995;
  position: absolute;
  width: 100%;
}

<!--Position: Fixed(not yet available)-->
.title {
  position: fixed;
  top: 0px;
  left: 0px;
}

<!--Position: Sticky(not yet available)-->
.box-bottom {
  background-color: darkgreen;
  position: sticky;
  top: 240px;
}

<!--Z-Index(not yet available)-->
.blue-box {
  background-color: blue;
  position: relative;
  z-index: 1;
}

.green-box {
  background-color: green;
  position: relative;
  top: -170px;
  left: 170px;
}

<!--Inline Display(not yet available)-->


h1 {
  display: inline;
}

<!--Display: Block(not yet available)-->
strong {
  display: block;
}

<!--Display: Inline-Block(not yet available)-->
<div class="rectangle">
  <p>I’m a rectangle!</p>
</div>
<div class="rectangle">
  <p>So am I!</p>
</div>
<div class="rectangle">
  <p>Me three!</p>
</div>

.rectangle {
  display: inline-block;
  width: 200px;
  height: 300px;
}

<!--Float(not yet available)-->
.green-section {
  width: 50%;
  height: 150px;
}

.orange-section {
  background-color: orange;
  width: 50%;
  float: right;
}

float: left;
float: right;

<!--Clear-->
div {
  width: 200px;
  float: left;
}

div.special {
  clear: left;
}

clear: left;
clear: right;
clear: both;
clear: none;
```

```html
body {
  background-color: #FFF;
  margin: 0 auto;
}

header {
  background-color: #466995;
  border-bottom: 1px solid #466995;
  position: fixed;
  width: 100%;
  z-index: 10;
}

ul {
  margin: 30px auto;
  padding: 0 20px;
  text-align: center;
}

li {
  color: #FFF;
  font-family: 'Oswald', sans-serif;
  font-size: 16px;
  font-weight: 300;
  text-transform: uppercase;
  display: inline-block;
  width: 80px;  
}

li:hover {
  color: #DBE9EE;
}

h1 {
  color: #466995;
  font-family: 'Oswald', sans-serif;
  font-size: 32px;
  font-weight: 300;
  text-transform: uppercase;
}

h2 {
  color: #333;
  font-family: 'Varela Round', sans-serif;
  font-size: 26px;
  font-weight: 100;
  margin: 0 auto 20px auto;
}

h3 {
  color: #466995;
  font-family: 'Oswald', sans-serif;
  font-size: 18px;
  text-align: center;
  font-weight: 700;
  text-transform: uppercase;
  padding: 30px;
}

h4 {
  color: #466995;
  font-family: 'Oswald', sans-serif;
  font-size: 18px;
  font-weight: 300;
  letter-spacing: 2px;
  text-align: center;
  text-transform: uppercase
}

p {
  color: #333;
  font-family: 'Varela Round', sans-serif;
  font-size: 18px;
}

footer {
  background-color: #DBE9EE;
  text-align: center;
  height: 100px;
}

.welcome {
  background-color: #DBE9EE;
  box-sizing: border-box;
  padding: 40px;
  text-align: center;
  width: 100%;
  position: relative;
  top: 50px;
}

.question {
  text-align: center;
  position: relative;
  top: 40px;
}

.answer {
  border: 1px solid #466995;
  margin: 20px;
  display: inline-block;
}

.answer:hover {
  background: #C0D6DF;
  color: #FFF;
}


<!DOCTYPE html>
<html>
<head>
  <title>Please Participate in Our Survey!</title>
  <link href="https://fonts.googleapis.com/css?family=Oswald:300,700|Varela+Round" rel="stylesheet">
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <header>
    <ul>
      <li>Question 1</li>
      <li>Question 2</li>
      <li>Question 3</li>
      <li>Question 4</li>
      <li>Question 5</li>
      <li>Question 6</li>
    </ul>
  </header>
  
  <div class="welcome">
    <h1><strong>Welcome</strong> to our survey!</h1>
    <p>We're looking forward to getting your answers so we can make sure our products and services are the best they can be!</p>
  </div>

  <div class="question">
    <h4>Question 1</h4>
    <h2>I like participating in physical activity such as running, swimming, or biking.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

  <div class="question">
    <h4>Question 2</h4>
    <h2>I try to keep up to date with the latest fashion in active wear.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

  <div class="question">
    <h4>Question 3</h4>
    <h2>I purchase clothing online regularly.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

  <div class="question">
    <h4>Question 4</h4>
    <h2>I try to buy goods that are designed and/or manufactured in my home country.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>

  <div class="question">
    <h4>Question 5</h4>
    <h2>I look to famous athletes when trying to choose what to wear when training.</h2>

    <div class="answer">
      <h3>Disagree</h3>
    </div>

    <div class="answer">
      <h3>Neutral</h3>
    </div>

    <div class="answer">
      <h3>Agree</h3>
    </div>
  </div>
  <footer>
    <h3>Thanks for taking our survey!</h3>
  </footer>

</body>
</html>
```

`Colors - codecademy`

```html
<!--Introduction to Color-->


<!--Foreground vs Background-->
h1 {
  color: red;
  background-color: blue;
}

<!--Hexadecimal(not yet available)-->
.city {
  background-color: #8B4513;
}

<!--RGB Colors(not yet available)-->
h1 {
  color: rgb(23, 45, 23);
}

.green {
  background-color: rgb(143, 188, 143);
}

.light {
  background-color: rgb(160, 82, 45);
}

.vienna {
  background-color: #A52A2A;
}

<!--Hex and RGB(not yet available)-->

<!--Hue, Saturation, and Lightness(not yet available)-->
color: hsl(120, 60%, 70%);

<!--Opacity and Alpha-->
color: hsla(34, 100%, 50%, 0.1);
color: rgba(234, 45, 98, 0.33);
```

```html
html,
body {
  margin: 0;
  height: 100%;
}

.wrapper {
  position: relative;
  margin: auto;
  padding: 0;
  max-width: 75vw;
}

.midground, .foreground {
  position: absolute;
  top: 0;
  left: 0;
  display: inline-block;
  margin: 15vh 0 0 15vw;
  padding: 0;
  width: 35vw;
  height: 59vh;
}

body {
  background-color: rgba(0, 255, 0, 0.1);
}

.midground {
  background-color: hsla(225, 100%, 25%, 0.4);
}

.foreground {
  background-color: hsla(325, 50%, 50%, 0.6);
}
```

`Typography - codecademy`

```html
<!--Typography-->


<!--Font Family-->
h1 {
  font-family: Arial;
}

h1 {
  font-family: 'Times New Roman';
}

h1 {
  font-family: Caslon, Georgia, 'Times New Roman';
}

h1 {
  font-family: Caslon, Georgia, 'Times New Roman', serif;
}

<!--Font Weight(not yet available)-->
.left-section {
  font-weight: 700;
}

.right-section {
  font-weight: bold; 
}

font-weight: bold; 
font-weight: normal; 
font-weight: lighter; 
font-weight: bolder; 

<!--400 is normal-->
<!--700 is bold-->

<!--Font Style(not yet available)-->
h3 {
  font-style: italic;
}

<!--Text Transformation(not yet available)-->
h1 {
  text-transform: uppercase;
}

<!--Text Layout(not yet available)-->
p {
  letter-spacing: 2px;
}

h1 {
  word-spacing: 0.3em;
}

p {
  line-height: 1.4;
}

<!--Web Fonts(not yet available)-->


<!--Web Fonts Using <link>(not yet available)-->
<head>
  <!-- Add the link element for Google Fonts along with other metadata -->
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100&display=swap" rel="stylesheet">
</head>

p {
  font-family: 'Roboto', sans-serif;
}

<!--Web Fonts Using @font-face-->
@font-face {
  font-family: 'MyParagraphFont';
  src: url('fonts/Roboto.woff2') format('woff2'),
       url('fonts/Roboto.woff') format('woff'),
       url('fonts/Roboto.ttf') format('truetype');
}

p {
  font-family: 'MyParagraphFont', sans-serif;
}

```

### [CSS Assessment](https://github.com/Deonnaa/HTMLAssessment)

### Bootstrap

#### Bootstrap
#### Adding Bootstrap to Your Page
#### Mobile-First Design
#### Bootstrap Responsive Layout
#### Grid System
#### Bootstrap Forms
#### Navbar Component

```java
```

### Provision an AWS EC2 Instance

### Apache HTTPD Web Server

### Portfolio Site Project