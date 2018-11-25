# Gmail Mobile Enhancer
An UserJS to add a few enhancement on the Gmail mobile site to use it as desktop.

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
Be aware though, that you need to configure the script. For that, go to your [Gmail Mobile page](https://mail.google.com/mail/mu/), go to the menu page (the hamburger icon at the top left) and execute this line in your console : 

```js
for(var a=document.getElementsByClassName("Tk"),b=[],c=0;c<a.length;c++)b[c]=1<a[c].innerText.split("\n").length?a[c].innerText.split("\n")[1]:a[c].innerText;for(var d=document.getElementsByClassName("Uk"),e=[],f=[],g=[],c=0;c<d.length;c++){e[c]=1<d[c].innerText.trim().split("\n").length?d[c].innerText.trim().split("\n")[1]:d[c].innerText.trim();var h=d[c].getElementsByClassName("bl");f[c]=h[0].style.background;var j=d[c].getElementsByClassName("Og");g[c]=j[0].getAttribute("onclick").split("'")[3]}for(var k="var textsUsual = [",c=0;c<b.length;c++)k+="\""+b[c]+"\", ";k=k.substring(0,k.length-2)+"];",console.log(k);for(var l="var textsLabels = [",c=0;c<e.length;c++)l+="\""+e[c]+"\", ";l=l.substring(0,l.length-2)+"];",console.log(l);for(var m="var colors = [",c=0;c<f.length;c++)m+="\""+f[c]+"\", ";m=m.substring(0,m.length-2)+"];",console.log(m);for(var n="var commandsLabels = [",c=0;c<g.length;c++)n+="\""+g[c]+"\", ";n=n.substring(0,n.length-2)+"];",console.log(n)
```

It will output some lines.
Copy those lines in the script to replace the lines with the empty values : 

```js
	var textsUsual = [];

	var textsLabels = [];
	var commandsLabels = [];
	var colors = [];
```

And you are done.

## What is the licence ?
The licence is easy : do whatever you want with it, except making money.

## Shoutouts
I stole some part of this project from others :  
* The injection of style comes from (Gmail Colour and Spacing Changes)[https://greasyfork.org/fr/scripts/373498-gmail-colour-and-spacing-changes]
* The favicon change is a simplified version of (Gmail Unread Message Count in Favicon)[http://userscripts-mirror.org/scripts/review/39432]
* Almost all the icons come from Gmail except the "My Circles" which is mine, and "External Link" which comes from [Font Awesome](https://fontawesome.com/icons/external-link-alt?style=solid)

## FAQ
*Why is this script so heavy ?*
Because I included the icons in it in base64. The code in itself represent a quarter of the size.
