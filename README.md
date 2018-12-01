# Gmail Mobile Enhancer
An UserJS to add a few enhancement on the [Gmail Mobile site](https://mail.google.com/mail/mu/) to use it as desktop.

## What is it ?
It's an UserJS that enhance a bit the mobile Gmail site, to avoid using the desktop one. It contains several modifications :  
* Dark theme
* A bit more compact UI
* A menu to go to all your folders and labels (you have to configure it first)
* Possibility to write a new mail in a tab
* Buttons to go back and forth
* Open current thread in the classic Gmail Desktop interface
* Change the favicon and site title to show number of unread
* Fix a bug with PgUp and PgDown (and space and shift+space)

Moreover, the whole thing is pretty modular, so you can modify it to suits you. Everything is commented, and even translatable easily.

## How to install it ?
It's an UserJS, so you can drag and drop it in your extension page, or use an extension like Tampermonkey.
Be aware though, that you need to configure the script to have the menu enabled. For that, go to your [Gmail Mobile page](https://mail.google.com/mail/mu/), go to the menu page (the hamburger icon, and the menu should be loaded.

If you want to avoid having to open the menu each time to have the menu, just open your console (after opening the menu once) and replace the lines in the userJS
```js
	var textsUsual = [];

	var textsLabels = [];
	var commandsLabels = [];
	var colors = [];
```
by those provided in the console. And you should be done.

## What is the licence ?
The licence is easy : do whatever you want with it, except making money.

## Shoutouts
I stole some part of this project from others :  
* The injection of style comes from [Gmail Colour and Spacing Changes](https://greasyfork.org/fr/scripts/373498-gmail-colour-and-spacing-changes)
* The favicon change is a simplified version of [Gmail Unread Message Count in Favicon](http://userscripts-mirror.org/scripts/review/39432)
* Almost all the icons come from Gmail except the "My Circles" which is mine, and "External Link" which comes from [Font Awesome](https://fontawesome.com/icons/external-link-alt?style=solid)

## FAQ
*Why is this script so heavy ?*
Because I included the icons in it in base64. The code in itself represent a quarter of the size.
