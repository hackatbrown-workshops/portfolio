# Launching Your Own Online Portfolio

Hi everyone! We'll be using HTML and CSS to make a portfolio for ourselves! You can see all the different versions of our code on GitHub.

But first of all, we need some background on what HTML and CSS actually are. These are the standard languages used to make all web pages, so you've already seen their result on every website you've been to. HTML stands for HyperText Markup Language. HyperText is just a fancy word for text that links to other stuff, like images and other web pages. HTML is a markup language because it describes ("marks up") the structure of the content. Instead of just being a pile of words, it has structure - paragraphs and lists and headings and containers and so on. CSS defines the appearance of the page - how all those parts should actually look. It's why websites aren't all black Times New Roman text on a white background.

As an analogy, think of a web page as a building. HTML is the walls, the doors, the foundation - all the parts you need for the building to work. CSS is like the paint, doorknobs, furniture, and lava lamps - you don't have to have them, but they make the building a lot prettier and nicer to use.

## Checkpoint 0: Setup
First, create a folder on your desktop called "Portfolio". This is where we're going to put all the files we're going to be creating in this workshop! Open up your favorite text editor and create a new file in this folder called index.html, this is your HTML file. If you're using the computers in the List MML, you can open up Text Wrangler.

We'll play around with the HTML file first before conquering the CSS part.

##Checkpoint 1: Structuring
Now, try copying the following code into your file:

```html
<!doctype html>
<html>
<head>
  <title>Website Title Here!</title>
  <link rel="stylesheet" href="styles.css">
</head>

<body>

</body>
</html>
```

This is the template we're going to start out with because it contains a lot of the tags we're going to need to start out with. Tags are essentially little labels telling the browser what the different parts are of your website are. For example, we might want to tell the browser which parts of our website is going to be a block of paragraph text, and which parts are going to be larger heading titles. HTML tags typically come in pairs of opening tags, like `<html>`, and closing tags, like `</html>`. 

Let's take a deeper look at each of these tags:

<!doctype html> tells the browser that everything from that point on in the file is going to be written in HTML.

`<html>` - after `<!doctype html>`, we always include an `<html>` tag.

The `<head>` tags include all the content that we want the browser to know about our website. This might include information that doesn't actually show up to users, but the browser needs to know about our website.

Inside the `<head>` tag (notice that tags can be *nested*, or placed inside one another!), we have a `<title>` tag, which sets the page title which shows up on the tab bar of your browser.

Ignore the `<link rel...>` tag for now -- we're going to be needing this part when we start working on our CSS.

The `<body>` tags contain all the information that should actually show up on your website itself. This is the tag we're going to be putting most of our HTML code in.

For now, try typing Hello World! inside your body tags. Save, and try opening index.html in your browser. Your screen should say "Hello World!" Congratulations! You made your first web page!

## Checkpoint 2: Titles and Headings
You should also be able to see Website Title Here on the tab bar of your browser. Let's change this to something else. I'm going to change it to my name.

We want an actual title to appear on the website itself, not just the tab bar, so let's try adding a `<h1>` tag in the body. You can have several different levels of headings, from `<h1>` to `<h6>`. The numbers represent importance, from most important (1) to least important (6)

```html
<body>
	<h1>Hi I'm Lucy.</h1>
	<h2> I'm a Computer Science student at Brown University.</h2>
</body>
```

Let's add some more `<h2>` tags for each subheading in our website.

```html
<body>
	<h1>Hi I'm Lucy.</h1>
	<h2> I'm a Computer Science student at Brown University.</h2>

	<h2>About Me</h2>

	<h2>Projects</h2>
</body>
```
Save and refresh to see the new headings!

## Checkpoint 3: Textual Content
The next tag we're going to be learning is the `<p>` tag, which stands for paragraph. Whenever we create a block of text on our site, we're going to want to wrap it with the `<p> ... </p>` tag.

Let's add some more textual content to our site now!
```html
<body>
	<h1>Hi I'm Lucy.</h1>
	<h2> I'm a Computer Science student at Brown University.</h2>

	<h2>About Me</h2>
	<p> Hi! I'm currently a sophomore studying Computer Science at Brown University. I love CS! And pumpkin pie </p>

	<h2>Projects</h2>
	<h3>My Hack @ Brown Project</h3>
	<p>Worked with a team of 4 undergraduate students during 2 day hackathon. Designed a fantastic front end for a super cool app with no prior web programming experience. Used HTML, CSS, and Javascript.</p>
	<h3>Doodle Jump</h3>
	<p>Created a fully functional Java implementation of Doodle Jump game in CS15 course. Used Java Swing to build GUI.</p>
</body>
```

##Checkpoint 4: Links
In your website, you might want to add some links to other sites, or a link to quickly email you. I'm going to place some link tags inside my `<h3>` tags for the titles of different projects I've worked on.

```html
<h3><a href="http://github.com">My Hack @ Brown Project</a></h3>

<h3><a href="http://github.com">Doodle Jump</a></h3>
```
You might notice that our link tags look a little different. The href attribute tells our browser which website we want to link to. Try changing the URL to something else.

Next, let's add a link to your email. When clicked, this link will start an email that will be sent to your email address, which is convenient when people want to reach you. I'm going to link a Contact Me! button.

```html
<a href="mailto: hwei@cs.brown.edu">Contact Me!</a>
```

Try saving + refreshing, and testing out your links!

##Checkpoint 5: Images
Let's try adding an image of ourselves. Image tags are a little different from all the tags we've encountered so far. I'm going to add one right before my about me paragraph text.

```html
<img src="image.png">
```

The src attribute in image tags describe the location of your image. If your image is in the same folder as your HTML file, you can just type the name of the image. Otherwise, you must specify its relative or absolute file path, or include an online URL.

Note that image tags also do not have a closing tag. They are one of the few HTML tags that only have an opening tag.

##Checkpoint 6: Prep for CSS
Whew! That was a lot of HTML. Before we move on to CSS, which will make our site a lot prettier, we're going to add some `<div>` tags. `<div>` tags alone will not change how your website will look, but they can help us section out our HTML. This is helpful for CSS because we might only want to apply a style to a specific section of our page. 

Here's how my body tag looks now:

```html
<body>
	<div id="header">
		<h1>Hi, I'm Lucy.</h1>
		<h2>I'm a Computer Science student at Brown University.</h2>
	</div>
	<div id="about">
		<h2>About Me</h2>
		<div id="about_content">
			<img src="image.png">
			<div id="about_text">
				<p>Hi! I'm currently a sophomore studying Computer Science at Brown University. I love CS! And Hack@Brown!</p>
			</div>
		</div>
		
	</div>
	<div id="projects">
		<h2>Projects</h2>
		<h3><a href="http://github.com">My Hack @ Brown Project</a></h3>
		<p>Worked with a team of 4 undergraduate students during 2 day hackathon. Designed a fantastic front end for a super cool app with no prior web programming experience. Used HTML, CSS, and Javascript.</p>
		<h3><a href="http://github.com">Doodle Jump</a></h3>
		<p>Created a fully functional Java implementation of Doodle Jump game in CS15 course. Used Java Swing to build GUI.</p>
	</div>
	<div id="contact">
		<a href="mailto:hwei@cs.brown.edu">Contact Me!</a>
	</div>
</body>
```

The id attribute simply allows us to give a name for the div (which will again be super helpful when we start CSSing!)

Next, let's pick out a font that we're going to use for our file. We can use Google Web Fonts for this. Once you choose a font, click on the plus button. Click the "1 Family Selected" Bar and copy the link that looks like `<link href="https://fonts.googleapis.com/css?family=...." rel="stylesheet">`. Paste this in your `<head>` tag *above* the line already there that says `<link href=...>`. The font won't actually show up on our website yet - we're going to need CSS to help us out with that!

##Checkpoint 7: CSS!
Take a look inside your head tag again. Remember the `<link ref="stylesheet" href="styles.css">` tag? That's a bit of HTML that helps us link up our HTML file and the CSS file that is going to style it.

Create a new file in your text editor and save it as styles.css (make sure that it is a .css file, not a .css.txt!) In your file, type out:

```css
body {
	font-family: 'font name';
	text-align: center;
}
```

Replace font name with the name of the font you selected earlier. We've selected a tag (the <body> tag) in our HTML file that we want to apply our CSS styling to. In our curly braces, we've denoted the styles we want to be applied, each separated by a semicolon.

Here are a couple more styles you can try out. Try experimenting around.

```css
h1 {
	font-size: 42px;
}

h2 {
	font-size: 32px;
}
```

Colors in HTML/CSS are described using Hex codes. For example, #FFFFFF represents white. Use http://www.colorpicker.com to help you select some colors!

```css
#header {
	background-color: #CAB1F0;
	padding:80px;
	margin-bottom:50px;
}

#header h1, #header h2 { 
	color: #ffffff;
	text-shadow: 3px 3px 0 #7B4CC2;
}

#about {
	margin-bottom: 50px;
}
```

You can think of most HTML tags as being represented as a box on your screen. When we add padding and margin, we add whitespace inside or around the edge of our box. Padding creates space between the edge of our box and the content inside our box; margin creates space between the edge of our box and the content *around* our box.

At this point, you know enough of the basics to start playing around with styles on your own. Feel free to check out my example styles.css file in the repository, or use http://www.w3schools.com/, which contains a wealth of information of HTML tags and CSS.

##Checkpoint 8: Setting Up Github Pages
Github Pages is a tool that will helps you upload your website to the world wide web using Github. We will assume that you already have a Github account and Git set up. If you need help getting Git set up, call over a mentor, or check out our Git guide.

First, log into your Github account and create a new repository called *username*.github.io, where *username* is your username on Github. The username must match or this well not work.

Using your terminal, open up the folder where want to store your website (preferably not your desktop or the same place as the folder we created today). In terminal, type in `git clone https://github.com/username/username.github.io`. If you open up your GitHub folder (where all your repositories are located), you should see that a new folder has been created.

Next, open up the folder containing all the files we've created today. Copy over all the files we've created into your username.github.io folder. This includes your index.html file, style.css, and any images you've added.

Add, commit, and push your changes.

```
git add --all
git commit -m "Initial commit"
git push -u origin master
```

Open up your browser and go to http://username.github.io!

Whenever you want to make edits to your website, simply edit the contents of the cloned repository, add, commit, and push your changes.
