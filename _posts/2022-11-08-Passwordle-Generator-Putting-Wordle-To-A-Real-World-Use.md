---
title: "Passwordle... Generator! Putting Wordle to real-world use."
date: "2022-11-8"
---
<img src="https://nytco-assets.nytimes.com/2022/01/Screen-Shot-2022-01-30-at-10.05.09-PM.png" alt="drawing" width="570"/>
(*Credit:: [New York Times](https://www.nytimes.com/)*)
[*Wordle*](https://www.nytimes.com/games/wordle/index.html) is an online game where you guess a word and it will tell you what letters are in the word. All of the words that you can guess have to be 5 letters (in the main version). Instead of making my own version of *Wordle*, I made a project with a use... To generate passwords.

## Retrieving the words
To retrieve all of the possible words you can enter into Wordle, you have to find a list. A list is available [here](https://github.com/tabatkins/wordle-list/blob/main/words). I didn't use that repo although it contains all of the words I did use.

## Security... And convenience.
You may think a password like `JgQ%67BR0ryJ` (Generated from [*LastPass*](https://www.lastpass.com/features/password-generator)) is more secure than a password generated with *Wordle* words but surprisingly, That isn't the case! This [*xkcd*](https://xkcd.com/936/) explains why. Not only is 4 words secure but it's easy to remember. The four words: `correct horse battery staple` (used in the *xkcd* linked above) are extremely easy to remember. For fun, I took this idea and put it into my project.

## Generating the password
To generate the password, you take the list of words, find 4 random ones and add a special character and a number (I just did the special character and a number part for fun. The choice of you keeping it is yours). Here is the code taken from the project:
```
// words contains the words and sc is short for special character:
$("#password").text( words[Math.floor(Math.random() * words.length)] + words[Math.floor(Math.random() * words.length)] + words[Math.floor(Math.random() * words.length)] + words[Math.floor(Math.random() * words.length)] + words[Math.floor(Math.random() * words.length)] + sc[Math.floor(Math.random() * sc.length)] + Math.floor(Math.random() * 99));
```
## Copying to the clipboard
I thought a great feature to add to this was being able to copy stuff to the clipboard. There are better ways, but the way I used was this:
```
navigator.clipboard.writeText($("#password").text()).then(function() {

alert("Password copied to clipboard");

}, function(err) {

console.error(err);

});
```
To copy it takes one line:
```
navigator.clipboard.writeText($("#password").text())
```
The `.then` was used just to notify the user that it was added to the clipboard.

## Contribution
If you would like to contribute to this project, the *GitHub* repo is [here](https://github.com/nikhilhex/passwordle-generator)

## Conclusion
This was a simple, but fun project. I will gladly take any suggestions on how to add more to this project (Post an issue on *GitHub*).
