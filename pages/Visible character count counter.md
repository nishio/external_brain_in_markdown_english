---
title: "Visible character count counter"
---

from [/scrasobox/visible-character-counter](https://scrapbox.io/scrasobox/visible-character-counter).
---
style.css

```
/* counter style */
#__charCounter__ span {
  cursor: pointer; font: 88%/1 monospace; 
  opacity: .35; /* ← density when mouse is not over it 35% */
  transition: opacity .2s ease-out }
#__charCounter__ span:hover { opacity: 1 } /* ← density on mouse over 100% */
#__charCounter__ { z-index: 30; position: sticky; bottom: 0; text-align: right }

/* popup style */
#__charCounterPopup__ {
  z-index: 30; position: absolute; bottom: 2em; right: -1em;
  border-radius: .25em; border: 1px solid #ddd; box-shadow: 0 0 8px 1px rgba(8,8,8,.1);
  padding: .8em; background-color: azure; color: #5F9EA0; font: 13.5px/1.4 monospace;
  transition: opacity .3s ease-out }

/* hide when in presentation mode */
.presentation #__charCounter__,
.presentation #__charCounterPopup__ { display: none }
```


script.js

```javascript
const __appliedProject__ = scrapbox.Project.name
const __charCounterSetup__ = setInterval(function() {
  
  // We want to wait for the page to be ready, so we start processing about 3 seconds after the script loads ↓↓↓.
  if (document.getElementById('editor') && scrapbox.Page.lines)
    clearInterval(__charCounterSetup__)
  else
    return // wait another 3 seconds if the page is not ready
  
  // Preparation
  const $id = id => document.getElementById(id)
  const $query = q => document.querySelector(q)
  const fmt = n => new Intl.NumberFormat('en-US').format(n).padStart(6)
  
  // Create elements for character count counter display
  const linesText = $query('.lines').innerText.trim()
  const chars = linesText.split(/\s+/).join('').length
  var counterWrapper = document.createElement('div')
  counterWrapper.id = '__charCounter__'
  counterWrapper.innerHTML = `<span>${fmt(chars)} chars</span>` +
      '<pre id="__charCounterPopup__" style="opacity:0"></pre>'
  $id('editor').appendChild(counterWrapper)
  
  const counter = $query('#__charCounter__ span')
  const popup = $id('__charCounterPopup__')

  // Pop up details when hovering mouse over character counter
  counter.addEventListener('mouseover',
      function() {
        const linesText = $query('.lines').innerText.trim()
        const chars = linesText.split(/\s+/).join('').length
        const words = linesText.split(/\s+/).length
  
        popup.innerHTML = `${fmt(chars)} chars\n` +
            `${fmt(words)} words\n` +
            `${fmt(scrapbox.Page.lines.length)} lines`
        popup.style.opacity = 1
      })
  
  // Make the detail popup invisible when the mouse cursor leaves the character counter
  counter.addEventListener('mouseout', function() { popup.style.opacity = 0 })

  // function to recount characters only
  const updateCounter = function() {
    if ($query('.presentation')
        || scrapbox.Project.name !== __appliedProject__) {
      
      // Hide the character counter if you are in presentation mode or displaying another project.
      counterWrapper.style.display = 'none'
    } else if (scrapbox.Page.lines) {
      
      // I'm recounting here.
      const linesText = $query('.lines').innerText.trim()
      const chars = linesText.split(/\s+/).join('').length
      counter.innerText = `${fmt(chars)} chars`
      counterWrapper.style.display = 'block'
    }
  }
  
  // Recount when entering text and when pasting
  $id('text-input').addEventListener('input', updateCounter)
  $id('text-input').addEventListener('paste', updateCounter)
  
  // Recount every 3 seconds without doing anything.
  setInterval(updateCounter, 3000)
}, 3000)
```


---
This page is auto-translated from [/nishio/見える文字数カウンター](https://scrapbox.io/nishio/見える文字数カウンター) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.