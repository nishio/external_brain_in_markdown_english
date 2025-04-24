---
title: "JS to summarize all pages that can be reached by following links"
---

[https://github.com/nishio/concatPages](https://github.com/nishio/concatPages)
[[concatPages]]

script.js

```javascript
function fetchAllPageData(projectName, title) {
  const url = `https://scrapbox.io/api/pages/${projectName}/${encodeURIComponent(
    title
  )}`;
  return fetch(url).then((res) => res.json());
}

async function fetchPage({ projectName, title }) {
  const url = `https://scrapbox.io/api/pages/${projectName}/${encodeURIComponent(
    title
  )}/text`;
  const pageRes = await fetch(url);
  if (pageRes.ok) {
    const text = await pageRes.text();
    return "## " + title + "\n" + text;
  } else {
    return "";
  }
}

function ensureDialogExists() {
  let dialog = document.getElementById("resultDialog");
  if (!dialog) {
    dialog = document.createElement("dialog");
    dialog.id = "resultDialog";

    // Checkbox
    // Create label and checkbox for current page
    const labelCurrent = document.createElement("label");
    const cbCurrent = document.createElement("input");
    cbCurrent.type = "checkbox";
    cbCurrent.id = "cbCurrent";
    cbCurrent.checked = true;
    labelCurrent.appendChild(cbCurrent);
    labelCurrent.appendChild(document.createTextNode("current"));
    dialog.appendChild(labelCurrent);
    dialog.appendChild(document.createTextNode(" "));

    const label1hop = document.createElement("label");
    const cb1hop = document.createElement("input");
    cb1hop.type = "checkbox";
    cb1hop.id = "cb1hop";
    cb1hop.checked = true;
    label1hop.appendChild(cb1hop);
    label1hop.appendChild(document.createTextNode("1hop"));
    dialog.appendChild(label1hop);
    dialog.appendChild(document.createTextNode(" "));

    const label2hop = document.createElement("label");
    const cb2hop = document.createElement("input");
    cb2hop.type = "checkbox";
    cb2hop.id = "cb2hop";
    cb2hop.checked = true;
    label2hop.appendChild(cb2hop);
    label2hop.appendChild(document.createTextNode("2hop"));
    dialog.appendChild(label2hop);
    dialog.appendChild(document.createTextNode(" "));

    const labelProj = document.createElement("label");
    const cbProj = document.createElement("input");
    cbProj.type = "checkbox";
    cbProj.id = "cbProj";
    cbProj.checked = true;
    labelProj.appendChild(cbProj);
    labelProj.appendChild(document.createTextNode("proj"));
    dialog.appendChild(labelProj);
    dialog.appendChild(document.createTextNode(" "));

    dialog.appendChild(document.createElement("br"));

    const textarea = document.createElement("textarea");
    textarea.id = "resultTextarea";
    textarea.style.width = "600px";
    textarea.style.height = "400px";
    dialog.appendChild(textarea);

    dialog.appendChild(document.createElement("br"));

    const closeBtn = document.createElement("button");
    closeBtn.id = "closeBtn";
    closeBtn.textContent = "close";
    closeBtn.addEventListener("click", () => dialog.close());
    dialog.appendChild(closeBtn);

    document.body.appendChild(dialog);
  }
  return dialog;
}

// Cache and link sets as global variables
let links1hop = [];
let links2hop = [];
let projLinks = [];
let cache = null; // after first fetch, {links1hop: {...} , links2hop: {...} , projLinks: {...}} Store
let initDone = false; // initialized flag

async function initAndShowDialog() {
  if (!initDone) {
    const projectName = scrapbox.Project.name;
    const data = await fetchAllPageData(projectName, scrapbox.Page.title);
    const relatedPages = data.relatedPages;

    links1hop = relatedPages.links1hop.map(({ title }) => ({
      projectName,
      title,
    }));
    links2hop = relatedPages.links2hop.map(({ title }) => ({
      projectName,
      title,
    }));
    projLinks = data.relatedPages.projectLinks1hop.map(
      ({ projectName, title }) => ({
        projectName,
        title,
      })
    );

    // fetch and cache all linked pages
    cache = {
      links1hop: {},
      links2hop: {},
      projLinks: {},
    };

    await Promise.all([
      ...links1hop.map(async (link) => {
        cache.links1hop[link.title] = await fetchPage(link);
      }),
      ...links2hop.map(async (link) => {
        cache.links2hop[link.title] = await fetchPage(link);
      }),
      ...projLinks.map(async (link) => {
        cache.projLinks[link.title] = await fetchPage(link);
      }),
    ]);

    // Fetch the current page content
    const currentPageContent = await fetchPage({ projectName, title: scrapbox.Page.title });
    
    // Store in cache with a separate key
    cache.currentPage = currentPageContent;

    ensureDialogExists();
    // Event Listener Registration
    document
      .getElementById("cb1hop")
      .addEventListener("change", updateTextareaContent);
    document
      .getElementById("cb2hop")
      .addEventListener("change", updateTextareaContent);
    document
      .getElementById("cbProj")
      .addEventListener("change", updateTextareaContent);
    document
      .getElementById("cbCurrent")
      .addEventListener("change", updateTextareaContent);

    initDone = true;
  }

  // Refresh on first time or redisplay
  updateTextareaContent();
  ensureDialogExists().showModal();
}

function updateTextareaContent() {
  const cb1hop = document.getElementById("cb1hop").checked;
  const cb2hop = document.getElementById("cb2hop").checked;
  const cbProj = document.getElementById("cbProj").checked;
  const cbCurrent = document.getElementById("cbCurrent").checked;

  const resultPages = [];
  if (cb1hop) {
    resultPages.push(...Object.values(cache.links1hop));
  }
  if (cb2hop) {
    resultPages.push(...Object.values(cache.links2hop));
  }
  if (cbProj) {
    resultPages.push(...Object.values(cache.projLinks));
  }
  // Add current page content if checked
  if (cbCurrent && cache.currentPage) {
    resultPages.push(cache.currentPage);
  }

  const content = resultPages.join("\n\n");
  document.getElementById("resultTextarea").value = content;

  // Copy to clipboard after updating
  navigator.clipboard.writeText(content)
    .catch((err) => console.error("Clipboard error: ", err));
}

// Add an item called concatPages to Scrapbox's custom menu
scrapbox.PageMenu.addItem({
  title: "concatPages",
  onClick: () => initAndShowDialog(),
});
```


---
This page is auto-translated from [/nishio/リンクをたどって到達できるページを全部まとめるJS](https://scrapbox.io/nishio/リンクをたどって到達できるページを全部まとめるJS) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.