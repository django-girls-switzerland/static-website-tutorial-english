Your first message to the world

Now, we create anew file called `index.html`  in the `username.github.io` folder. This is your web page. As an empty file is not so interesting to look at, we now open this file using the code editor you installed earlier, and write something in it. What exactly you write is not so important. Just write whatever comes to your mind. After saving the file we go back to the Terminal in order to put this file on the internet. 

command-line

```
$ git status
On branch master
Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

    index.html

nothing added to commit but untracked files present (use "git add" to track)
```

From this we learn that  Git has seen the `index.html` file but didn't save it yet. In addition to saving file in the code editor, we need to save it in git as well, in order for git to be able to keep track of the changes. To save something in Git is called 'commit'. This creates a new version of your project \(which contains all the files in the`username.github.io` folder in this case\) for you so you can comeback to it later. Each commit has a commit message. This is a short description in which you write what you changed since the last version/commit. To commit something in git we do: 

command-line

```
$ git add --all
$ git commit -m "first commit: just saying something"
[master (root-commit) 4eca6ab] first commit: just saying something
 1 file changed, 2 insertions(+)
 create mode 100644 index.html
```

Now there is just one step missing to bring our first version of a website online. We have to upload the changes we made to Github. This can be done with the push command: 

command-line

```
$ git push -u origin master
```

You will be asked to enter your Github username and password, and after that your commit will be transfered to github. You know have published a very minimal website! If you go to  [http://username.github.io](http://username.github.io) in your browser, you should see the text that you have written in the index.html file. 

Dit you write a text over multiple lines in index.html? How does it look like in your browser? If your text was only one line long, you can now try to add some more lines, and repeat the whole commit process after that. You will see that the browser doesn't recognise the linebreaks from your file. Because of this we will need to use HTML to structure the text on our web page. We will do exactly this in the next section. But before that you have earned a break. 



