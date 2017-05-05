## CSS: pimp your layout

Until now we have worked on the structure of our web page using titles lists and paragraph. But we haven't made it very beautiful yet. Time to change that using CSS!

CSS \(Cascading Style Sheets\) is the language used to defined the layout of HTML pages. We will put our CSS code in a sperate file. This will make our life easier if at some point we want to change the look of our site, but keep the content. A CSS file is a normal text file ending on css \(in the same way that a HTML file is a normal text file ending on .html\). Because of the different endings everybody \(well especially Programmers, and from now on, you as well\) knows which files contains the content, and which one the layout definition.

So first we have to make a new textfile in the same folder containing index.html. I'll call mine main.css, but you can also give yours a different name, as long as it ends with .css. Now open this file with your code editor, and write your first CSS code inside:

```
h1 {
    color: #426493;
}
```

This code will change the color of the most important heading 'h1'. After saving the changes to our CSS file, we now have to write somewhere in our index.html file an indication for the browser where it can finde the layout belonging to this page. To do this we add the following to index.html:

```
<html>
    <head>
        <title> ... </title>
        <link rel="stylesheet" href="main.css">
    </head>
    ...
```

If you gave your CSS file a different name, don't forget to change it in this peace of code as well. \(after `href="`\)

After saving our changes we can now open the index.html in our browser again. The h1-heading should now be blue, because \#426493 is the colorcode of a particular kind of blue. If you want another color instead, try to enter "colorpicker" in google, find a color you like and copy the number starint with a \# into your CSS file instead of '\#426493'.

Success! we've added CSS to our web page. We can do much more with it of course, but first let us save this step in Git and deploy our result to the internet once more.

command-line

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   index.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)

    main.css

no changes added to commit (use "git add" and/or "git commit -a")
$ git add --all
$ git commit -m "a little bit of css"
[master a0850fb] a little bit of css
 2 files changed, 4 insertions(+)
 create mode 100644 main.css
$ git push
```

Enter your Github username and password, and it is done! Woohoow!

If you look closer to the code that we wrote int our CSS file you will see that it looks similar to the image below. Except that we have used another color and another selector.  Can you guess whet the css form the image does? \(If you want to try it out, you can type the code from the image into your CSS file right under what we have written earlier. Then save it and have a look at index.html in your browser. As \#333333 is a very dark grey that might be hard to distinguish from bleck, it might be a good idea to replace it with another colorcode to see what is going on.\)![](/assets/cssrule.png)Image from [https://www.girldevelopit.com/materials](https://www.girldevelopit.com/materials)

So the thing we have written is called a CSS rule. To define the complete layout of your website you need a whole lot of those CSS rules. You can just write them one after the other in your CSS file. Each rule can have multiple declarations. Declarations are always of the form `Eigenschaft: Wert;` .

We could for example change the CSS rule of the 'h1' selector we wrote earlier to: :

```
h1 {
    background-color: #426493;
    color: #ffffff;
}
```

Or we can change the fonts: :

```
body{
    font-family: "Courier New", Courier, monospace;
}    
h1 {
    font-family: Arial, Helvetica, sans-serif;
    background-color: #426493;
    color: #ffffff;
}
```

You can find other examples of fonts for the web on [http://www.w3schools.com/cssref/css\\_websafe\\_fonts.asp](http://www.w3schools.com/cssref/css_websafe_fonts.asp) Those fonts are used very often and most browsers provide them by default. If you want to use more exotic fonts, you will have to provide the font with your website, as the browser doesn't automatically know all fonts. You can finde more info about this in the chapter[ extras for your static website](/introduction.md).

Until now we have alsways used names of HTML tags as selectors for our CSS rules. This is useful when the CSS rule has to be aplied to all headings, paragraphs or links. But it doesn't work when you only want to apply a particular layout to only a group of elements. For this case we need another type of selectors: IDs and classes. To each HTML tag we can add one or multiple classes and one id. We have to take care that ids have to be unique per page \(one ide cannot appear multiple times in one page\). Classes however can be added to multiple elements on the same page.

| Name | Benutzung im HTML-File | Benutzung im CSS-File |
| :--- | :--- | :--- |
| ID | `<p id="one_green_thing"> some green text </p>` | `#one_green_thing{ color: #00ff00;}` |
| Class | `<h1 class="all_red_things">Red title</h1><p class="all_red_things"> some red text </p>` | `.all_red_things{ color: #ff0000;}` |

In our index.html we can use `<span>` and `<div>` HTML tags as generic containers. Their main difference is that span is an inline element which doesnt interupt the text flow, whereas div is a block element. Both elements are often used in combination with classes and ids to give certain parts of a web page a certain layout. An example:

index.html

```
<html>
    <head>
        <title>Django Girls Bern</title>
        <link rel="stylesheet" href="main.css">
    </head>
    <body>
        <div id="header">
            <h1>Was ist Django Girls Bern</h1>
        </div>
        <div id="content">
            <p>Django Girls Bern ist ein Workshop wo man Programmieren lernt. </p>
            <p>Während zwei Tagen machen wir eine eigene <span class="color">Webseite</span>, 
            mit einem <span class="color">Blog</span>. 
            Dazu verwenden wir verschiedene Tools, Frameworks und Programmiersprachen. Ein paar Beispiele sind:</p>
            <ul>
                <li><a href="https://de.wikipedia.org/wiki/Hypertext_Markup_Language">HTML</a></li>
                <li><a href="https://de.wikipedia.org/wiki/Cascading_Style_Sheets">CSS</a></li>
                <li><a href="https://de.wikipedia.org/wiki/Git">GIT</a></li>
                <li><a href="https://de.wikipedia.org/wiki/Python_(Programmiersprache)">Python</a></li>
                <li><a href="https://de.wikipedia.org/wiki/Django_(Framework)"><span id="big_django">Django</span></a></li>
                <li><a href="https://de.wikipedia.org/wiki/Kommandozeile">Command line</a></li>
            </ul>
            <p>Alle sind super motiviert und die Coaches haben viel geduld. Zudem gibt es feines Essen.</p>
        </div>
    </body>
</html>
```

main.css

```
body{
    margin: 0;
    padding: 0;
    font-family: "Courier New", Courier, monospace;
}

h1 {
    font-family: Arial, Helvetica, sans-serif;
    color: #ffffff;
}

#header {
    text-align: center;
    padding-top: 25px;
    padding-bottom: 25px;
    background-color: #426493;
}

#content {
    width: 75%;
    margin-top: 25px;
    margin-left: auto;
    margin-right: auto;
}

a {
    color: #426493;
}

.color{
    font-weight: bold;
    color: #426493;
}

#big_django{
    font-size: 200%;
    font-weight: bold;
}
```

And the result:  
![](/assets/statische-seite.jpg)This example shows a couple of things you can do using CSS. You can find more examples on  [w3schools](http://www.w3schools.com/css/default.asp). Now it is time for you to try it out. Don't try to make the perfect web page from the start, but do short cycles of making some changes, saving, looking in your browser, so that you get to understand what happens.

When you are finished all we have to do before we are ready is deploying our website one more time:

command-line

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   index.html
    modified:   main.css

no changes added to commit (use "git add" and/or "git commit -a")
$ git add --all
$ git commit -m "a complete web page including css"
[master 80c1d78] a complete web page including css
 2 files changed, 63 insertions(+), 22 deletions(-)
 rewrite index.html (87%)
$ git push
```



