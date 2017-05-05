## Structure with HTML

We already mentioned HTML in the introduction \(How the internet works\). It means Hyper Text Markup Language. HTML exists of so called tags:

* &lt; elementname &gt; : start tag
* &lt;/ elementname &gt; : end tag
* &lt; elementname /&gt; : empty tag

Start and end tags are always used together. The text in between a start and an end tag is the element. The tags themselves indicate how the text in between them should be displayed. Some tags don't need a text in between, in those cases an empty tag is used. An empty tag is a contraction of a start and end tag without any text in between them. The following table shows some examples.

| Explanation | HTML |
| :--- | :--- |
| ordinary paragraph text | `<p>text</p>` |
| your most important heading | `<h1>A heading</h1>` |
| a heading at the next level | `<h2>A sub-heading</h2>` |
| a heading at the next level | `<h3>A sub-sub-heading</h3>`... and so on, up to`<h6>` |
| emphasize your text | `<em>text</em>` |
| strongly emphasize your text | `<strong>text</strong>` |
| go to another line | `<br/>`\(you can't put anything inside br, it's an empty tag\) |
| create a link | `<a href="http://djangogirls.org/">link text</a>` |
| make a list | `<ul><li>first item</li><li>second item</li></ul>` |
| define a section of the page | `<div></div>` |

A HTML text uses different HTML-tags for structure and correct display. Those tags can also be nested. For example if a Titel contains a link, it will look like this: :

```
<h1>Title with <a href="http://something.com">Link</a></h1>
```

In addition, each HTML-page has a base structure that is always the same. The outermost tag bair is always &lt;html&gt;...&lt;/html&gt;. Inside of this there are two parts: head and body. The body contains information that is displayed on the actual page. The Head on the other hand contains meta information, for example the title of the page, which CSS files should be used for the layout, the keywords for search engines ect.

The complete base structure looks like this:

```
<html>
    <head>
        ...
    </head>
    <body>
        ...
    </body>
</html>
```

In order to make the HTML-text more readable for humans nested tags are indented compared to their parent tags.

Using this you are now able to improve you web page in the index.html. You could for example make a text with a title and a list of links to the pages of the other people in your group at the bottom.  The exact content of your page is not so important right now. The most important thing is that you get the chance to play around with HTML tags a bit.

If you want to have a look at how your website would look like while you are putting in more and more HTML tags, you can always save your file and open it in your browser.

![](/assets/tutorial_screenshot.png)

When you are happy with the content and structure of your page, it is time to publish a new version online. To do this we go back to the Terminal window \(ideally you still have it open somewhere\).

command-line

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")
$ git add --all
$ git commit -m "adding html"
[master 9bfcf50] adding html
 1 file changed, 20 insertions(+), 2 deletions(-)
 rewrite index.html (100%)
$ git push
```

Now just enter your Github username and password when asked for it and that was it! The newest version of your website is online now! Woohoow :D!

