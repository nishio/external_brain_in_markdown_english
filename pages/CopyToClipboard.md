---
title: "CopyToClipboard"
---

A story about creating a bookmarklet that facilitates the process of "copying something to the clipboard.

how things have been going so far
- [/yujif/bookmarklet that allows you to copy the page you are currently viewing in Scrapbox link format](https://scrapbox.io/yujif/bookmarklet that allows you to copy the page you are currently viewing in Scrapbox link format).
- [/shiology/05107-180420 Now you can copy the Scrapbox link on the page you are looking at with one click](https://scrapbox.io/shiology/05107-180420 Now you can copy the Scrapbox link on the page you are looking at with one click).
- [/shiology/05148-180531 I wrote a bookmarklet to get the Scrapbox link for flickr](https://scrapbox.io/shiology/05148-180531 I wrote a bookmarklet to get the Scrapbox link for flickr).

Summary at this time
- When execCommand is invoked from a bookmarklet in the latest Chrome, the return value is false and not copied
- The same code is copied with a return value of true when executed from devtool
- This seems like an `outside a user-generated event handler` type of problem, is there any way around it?

-----
Mounting 1
javascript

```javascript
function copy_impl1(target){
	// Copy function implementation 1: Create an input element containing the desired string, select it, and execute the copy command.
 	// Chrome on Mac works with Safari, but not Safari on iOS, apparently.
	const e=document.createElement('input');
 	e.value=target;
  	document.querySelector('body').append(e);
    e.select();
    document.execCommand('copy');
    e.remove();
}) 
```


Mounting 2
js

```javascript
function copy_impl2(target){
	// Copy function implementation 2: Create a textarea element containing the desired string,
 	// Select characters 0 to 99999999 and execute copy command
 	// Confirmed to work with Safari on both iOS and Mac
	var a = document.createElement("textarea");
	a.textContent = target;
    var b = document.getElementsByTagName("body")[0];
    b.appendChild(a);
    a.contentEditable = true;
    a.readOnly = false;
    a.setSelectionRange(0, 999999);
    document.execCommand("copy");
    b.removeChild(a)
}
```


- Comparing the two, the main difference is the use of textarea and setting contentEditable to true
- querySelector is also supported in Safari on iOS [https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)

But, well, let's not go too deep and simply call them both this time.
- It didn't work.
- Draft 3
- [http://yuw27b.hatenablog.com/entry/2017/02/19/230000](http://yuw27b.hatenablog.com/entry/2017/02/19/230000)
- There's a difference in the way you make choices.

js

```javascript
function copy_impl3(target){
	// Copy function implementation 3: Create a p element containing the desired string, select it, and execute the copy command,
	var a = document.createElement("p");
    var b = document.querySelector("body")
    b.append(a);
	var range = document.createRange();
 	range.selectNode(a);
 	window.getSelection().removeAllRanges();
 	window.getSelection().addRange(range);
 	document.execCommand('copy');
}
```

This way it was confirmed up to the point where the p-element was added and it was selected, but it was not copied.

Chrome
- impl1 confirmed that input is selected by e.select
- But not copied.
- Then I run document.execCommand('copy') from devtool and it copies it.
- The return value in this case is true
- false when executed from a bookmarklet

Yet another solution
js

```javascript
function copy_impl4(target){
	let copyListener = event => {
 		document.removeEventListener("copy", copyListener, true);
  	event.preventDefault();
  	let clipboardData = event.clipboardData;
 		clipboardData.clearData();
 		clipboardData.setData("text/plain", target);
	};
	document.addEventListener("copy", copyListener, true);
	document.execCommand("copy");
	document.removeEventListener("copy", copyListener);
}
```

In this case also, launching from the bookmarklet does not work, execCommand is false, and running with devtool copies it properly.

So the code for the whole thing is below
main.js

```javascript
function copy_impl1(target){
	// Copy function implementation 1: Create an input element containing the desired string, select it, and execute the copy command.
 	// Chrome on Mac works with Safari, but not Safari on iOS, apparently.
	const e=document.createElement('input');
 	e.value=target;
  	document.querySelector('body').append(e);
  	console.log(e)
    e.select();
    console.log(document.execCommand('copy'));
    //e.remove();
}
function copy_impl2(target){
	// Copy function implementation 2: Create a textarea element containing the desired string,
 	// Select characters 0 to 99999999 and execute copy command
 	// Confirmed to work with Safari on both iOS and Mac
	var a = document.createElement("textarea");
	a.textContent = target;
    var b = document.getElementsByTagName("body")[0];
    b.appendChild(a);
    a.contentEditable = true;
    a.readOnly = false;
    a.setSelectionRange(0, 999999);
    console.log(window.getSelection())
    document.execCommand("copy");
    //b.removeChild(a)
}
function copy_impl3(target){
	// Copy function implementation 3: Create a p element containing the desired string, select it, and execute the copy command,
	var a = document.createElement("p");
 	a.textContent = target;
    var b = document.querySelector("body")
    b.append(a);
    console.log(a)
	var range = document.createRange();
 	range.selectNode(a);
    console.log(range)
 	window.getSelection().removeAllRanges();
 	window.getSelection().addRange(range);
 	document.execCommand('copy');
    console.log(window.getSelection())
}
function copy_impl4(target){
	let copyListener = event => {
 		document.removeEventListener("copy", copyListener, true);
  	event.preventDefault();
  	let clipboardData = event.clipboardData;
 		clipboardData.clearData();
 		clipboardData.setData("text/plain", target);
	};
	document.addEventListener("copy", copyListener, true);
	console.log(document.execCommand("copy"));
	document.removeEventListener("copy", copyListener);
}
function main(){
	var target = `[${document.title.replace(/\s*[\[\]]\s*/g,' ')} ${location.href}]`;
 	//copy_impl1(target);
  	//copy_impl2(target);
    //copy_impl3(target);
    copy_impl4(target)
    console.log("ok")
}
main();
```


This can be accessed at `https://scrapbox.io/api/code/nishio/CopyToClipboard/main.js` so

javascript: var url="[https://scrapbox.io/api/code/nishio/CopyToClipboard/main.js";var](https://scrapbox.io/api/code/nishio/CopyToClipboard/main.js";var) elm=document.createElement('script');elm.setAttribute('src', url);document.body.appendChild(elm);

a
a

---
This page is auto-translated from [/nishio/CopyToClipboard](https://scrapbox.io/nishio/CopyToClipboard) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.