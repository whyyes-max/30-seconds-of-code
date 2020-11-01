---
title: textDance
tags: text,html-interfacing
---

Makes text dance.

- You specify a HTML ID to dance, and it will dance
- It works by inserting spaces and removing them after

```js
function dance(elementid, dancetime){
    setInterval(dancetimer, 200, elementid, "add");
    window.setTimeout(removedancetimer, dancetime, elementid, dancetime);
}

function dancetimer(elementid, mode){
    if(mode == "add"){
        document.getElementById(elementid).innerHTML = "&nbsp;"+document.getElementById(elementid).innerHTML;
    }else{
        document.getElementById(elementid).innerHTML = document.getElementById(elementid).innerHTML.substr(6);
    }
}

function removedancetimer(elementid, dancetime){
    clearInterval(dancetimer);
    setInterval(dancetimer, 50, elementid, "remove");
    window.setTimeout(clearInterval, dancetime, dancetimer);
}
```

```js
<div id="todance" onClick='dance("todance", 20000);'>text to dance</div>
```
