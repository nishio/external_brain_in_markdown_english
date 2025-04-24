---
title: "nishio"
---

This is a better [[My page]] to have due to Scrapbox specifications.

![image](https://gyazo.com/03051565f03a70a83b182fda5965e187/thumb/1000)
- If you make a personal page like this, you can use Ctrl+i to get an icon.
- By first pinning the page with the image on it, it becomes a Favicon and is easily recognizable in browser tabs, etc.
    - [[self-introduction]]
- [NISHIO Hirokazu,](http://www.nhiro.org/)

![image](https://gyazo.com/c078c5aa55ddbddd85530c5136b163e8/thumb/1000)



----- including user scripts for personal customization under -----

[[MyUserScript]]
style.css

```
 @import "https://scrapbox.io/api/code/nishio/MyUserScript/style.css";
```

script.js

```javascript
 import '/api/code/nishio/MyUserScript/script.js'
```

---

[[pin-diary-X]]
script.js

```javascript
import "/api/code/nishio/pin-diary-X/min.js"
```



- [[Recently unopened pages]]
disabled_script.js.disabled

```
import "/api/code/nishio/recently unopened pages/script.js"
```


[[add watchlist]]
script.js.disabled

```
import '/api/code/nishio/add_watchlist/script.js'
```


[[open with mem]]
script.js

```javascript
import '/api/code/nishio/open_with_mem/script.js'
```


[[open with quartz]]
script.js

```javascript
import '/api/code/nishio/open_with_quartz/script.js'
```


[[open with porter]] Moved To MyUserScript
script.js.disabled

```
import '/api/code/nishio/open_with_porter/script.js'
```



[[ScrapBubble]] [/takker/takker99/ScrapBubble](https://scrapbox.io/takker/takker99/ScrapBubble)
script.js.disabled

```
import { mount } from "../ScrapBubble-min/app.js";

mount({
  whiteList: ["nishio"]
});
```



- [[Ctrl+Enter in Scrapbox to have Keicho ask a question.]]
script.js.disabled

```
import('/api/code/nishio/Ctrl+Enter in Scrapbox to ask Keicho a question/script.js');
```


## "format" menu for full-width half-width conversion, etc.
 (from [/shiology](https://scrapbox.io/shiology))
1. replace all bullets with Tab at the beginning
2. remove full-width and half-width spaces in a sentence
- Fix garbled characters (in this case, change `de' to `de')
- Replace full-width alphanumeric characters with half-width alphanumeric characters.
- Replace full-width parentheses with half-width parentheses
6. put a space before or after the parentheses
7. space before and after the code block notation
script.js.disabled

```
scrapbox.PopupMenu.addButton({
    title: 'format',
    onClick: text => text.split('\n').map(function(line) {
        return line.replace(/^\s*/g, s => s.replace(/\s/g, '\t'))
//            .replace(/[ 　]/g, '')
            .replace(/[a-n|a-v]゙/g, s => String.fromCharCode(s.charCodeAt(0) + 1))
            .replace(/[Ａ-Ｚａ-ｚ０-９]/g, s => String.fromCharCode(s.charCodeAt(0) - 0xFEE0))
            .replace('（', '(')
            .replace('）', ')')
            .replace(/\S\(/g, s => s.charAt(0) + ` (`)
            .replace(/\)\S/g, s => ') ' + s.charAt(1))
            .replace(/\S`.*`/g, s => s.charAt(0) + ' ' + s.slice(1))
            .replace(/`.*`\S/g, s => s.slice(0, -1) + ' ' + s.slice(-1))
    }).join('\n')
})
```


- [[Scrapbox Cross Search]]
script.js.disabled

```
var pagename = document.location.pathname.split("/").pop();
if(pagename == "cross_search"){
	console.log(pagename);
	var query = document.location.search.substr(1);
	var page = document.getElementsByClassName("page")[0];
	page.innerHTML = "<iframe width='50%' height='2000px' src='https://scrapbox.io/rashitamemo/search/page?q=" + query + 
"'></iframe><iframe width='50%' height='2000px' src='https://scrapbox.io/nishio/search/page?q=" + query + "'></iframe>" + page.innerHTML;
}

```



Create a new one if not found in [/masui/search](https://scrapbox.io/masui/search).
- [[Create a new page by pressing the new line key]]
disabled_script.js.disabled

```
$('body').on('keydown',function(e){ // Enter key to create new page
   if(e.target.tagName != "TEXTAREA" && e.target.tagName != "INPUT"){
      if(e.key == 'Enter'){
         var project = location.href.split('/')[3];
         location.href = `/${project}/new`;
      }
   }
});
$('.btn.btn-default').on('click',function(){
   var s = $('.form-control').val();
   if(s == ''){
      var project = location.href.split('/')[3];
      location.href = `/${project}/new`;
   }
});
```


## time tagging
.
Create a tag for year, a tag for day of month, and a tag for year and month. You can use "What did you do around what year?" or narrow it down to "Around what month of the year. The day-of-month tag is used for "[[This day in the past]]".
script.js.disabled

```
 scrapbox.PopupMenu.addButton({
   title: "TimeTag",
   onClick: (text) => {
   	 var m = text.match(/((\d\d)?(\d\d))-?(\d\d)-?(\d\d)/);
     var year = "20" + m[3];
     var month = m[4];
     var day = m[5];
     return `${year}-${month}-${day} #${year} #${month}-${day} #${year}-${month}`;
   }
 })
```


2018-09-19 Date and time format to ←.
Moved To MyUserScript
script.js.disabled

```
scrapbox.TimeStamp.removeAllFormats()
scrapbox.TimeStamp.addFormat("YYYY-MM-DD")
```


2018-06-22
script.js.disabled

```
import '/api/code/nishio/excerpt-UserScript/script.js'
```

see  [[Extracted UserScript]]

2018-06-12
reduce
script.js.disabled

```
 var elm=document.createElement('span');
 elm.append("ZoomOut")
 elm.onclick = ()=>{
   		document.getElementsByClassName("page-list")[0].setAttribute('style', 'zoom: 0.5')
     	document.getElementsByTagName('body')[0].webkitRequestFullscreen()
 }
 document.getElementsByClassName("search-form")[0].parentElement.append(elm) 
```




2018-05-25
- [/customize/"this day in the past" function](https://scrapbox.io/customize/"this day in the past" function)
    - [[Scrapbox look-back function]]
script.js.disabled

```
import '/api/code/nishio/Scrapbox lookback function/script.js'
```


## voice input
.
2018-04-15
[/shokai/Voice Input Menu](https://scrapbox.io/shokai/Voice Input Menu).
script.js.disabled

```
import '/api/code/shokai/Voice Input Menu/script.js'
```


From Dr. Shiozawa's project

## tweet menu
.
script.js.disabled

```
scrapbox.PageMenu.addItem({
  title: 'Tweet',
  image: 'https://twitter.com/favicon.ico',
  onClick: () => window.open(`https://twitter.com/intent/tweet?url=${encodeURIComponent(location.href)}&text=${encodeURIComponent(document.title)}`)
})
```


## Character Count Menu
.
script.js.disabled

```
 scrapbox.PageMenu.addItem({
   title: () => {
     if (!scrapbox.Page.lines) return
     const chars = scrapbox.Page.lines.map(line => line.text.length).reduce((a,b) => a + b)
     const words = scrapbox.Page.lines.map(line => line.text.split(/\s+/).length).reduce((a,b) => a + b)
     return `${chars}characters ${words}words ${scrapbox.Page.lines.length}lines
   },
   onClick: () => null
 })
```


## character counter
.
- [[Visible character count counter]]
style.css_disabled

```
@import "/api/code/nishio/visible-characters-counter/style.css";
```

script.js_disabled

```
import "/api/code/nishio/visible-character-count-counter/script.js";
```



## Search popup for selected string in project
.
script.js.disabled

```
// Search for the selected string in the Scrapbox project
// Open the same results page as when using the Scapbox search box
scrapbox.PopupMenu.addButton({
    title: 'Search in SB',.
    onClick: function (text) {
    	var projectName = 'shio';
     	window.open('https://scrapbox.io/'+ projectName +'/search/page?q=' + text);
    }
});
```



---
Cutting out a section of a page into a new page
disabled_script.js.diabled

```
scrapbox.PopupMenu.addButton({
  title: 'NewPage',
  onClick: text => {
    const lines = text.split(/[\r\n]/g)
    const title = lines[0]
      .trim()
      .replace(/\[[^\]]+.icon\]/gm, '')
      .replace(/[\[\]]/g, '')
    const projectRoot = (() => {
      const tmp = location.href.split('/')
      tmp.pop()
      return tmp.join('/')
    })()
    const currentPageTitle = decodeURIComponent(location.href.split(/\//g).pop())
    lines.unshift(`from [${currentPageTitle}]`)
    const body = encodeURIComponent(lines.join('\n'))
    window.open(`${projectRoot}/${title}?body=${body}`)
    return `[${title}]`
  }
})
```


2021-05-06
[[to🔒]]
script.js.disabled

```
const privateProject = "znishio"
scrapbox.PageMenu.addItem({
  title: 'to🔒',
  onClick: () => {
	const title = document.location.pathname.split("/")[2];
	window.open(`https://scrapbox.io/${privateProject}/🔒${title}`, "_blank")
  }
})
scrapbox.PageMenu.addItem({
  title: 'make🔒',
  onClick: () => {
	const title = document.location.pathname.split("/")[2];
	const body = `[https://scrapbox.io/nishio/${title} 🌏] [${title}]`
	window.open(`https://scrapbox.io/${privateProject}/🔒${title}?body=${body}`, "_blank")
  }
})
```


- [[add padding]]
style.css.disabled

```
a.mobile-search-toggle {
    padding: 1em;
}
.toggle-button.closed {
    padding-right: 1em;
}
.toggle-button.open {
    padding-right: 1em;
}
```


---
This page is auto-translated from [/nishio/nishio](https://scrapbox.io/nishio/nishio) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.