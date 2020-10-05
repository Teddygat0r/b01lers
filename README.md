# b01lers

Ctf At: https://play.ctf.b01lers.com/home

## Find That Data!

**Solution**
When we first visit the website, we see a simple login screen.  It doesn't seem to be related to sql, and when we open up the source code, we can see the username and password in the source code.

After logging in, we see a game screen.  We need to get from one end of a maze that changed every second to the other end.  When we open the source code, we can see the game's source javascript code.  It appears that the game is run locally, so we are able to use to console to interact with the game.  We can just copy paste the code from the game's 'win' function into the console, and boom! An alert with the flag appears!

## First Day Inspection

**Solution**
This is a simple inspect element problem.  The 5 pieces of the flag are littered in different sections of inspect element.  

## Reindeer Flotilla

**Solution**
This is a basic xss problem.  The goal is to get an alert to appear on the screen.  Unfortunately, it doesn't seem to let you use a <script> tag.  We can bypass this by using another html tag to run the javascript, for example, an <img> tag.
  
```<img src="bald" onerror="alert(1)">```

The way this works is that it tries to get an image located at "bald".  However, as bald doesn't exist, it instead runs the javascript within onerror.
