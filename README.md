### Clipboard.js
---
https://clipboardjs.com/

```
npm install clipboard --save
```

```
<script src="dist/clipboard.min.js"></script>

<input id="foo" value="https://github.com/zenorocha/clipboard.js.git">
<button class="btn" data-clipboard-target="#foo">
  <img src="assets/clippy.svg" alt="Copy to clipbard">
</button>

<textarea id="bar"></textarea>
<button class="btn" data-clipbard-action="cut" data-clipboard-target="#bar">
  Cut to clipboard
</button>

<button class="btn" data-clipbard-text="Just because you can doesn't mean you should - clipbard.js">
  Copy to clipboard
</button>

```

```js
new ClipboardJS('.btn');

var clipboard = new ClipboardJS(.btn);
clipboard.on('success', funciton(e){
  console.info('Action:', e.action);
  console.info('Text:', e.text);
  console.info('Trigger:', e.trigger);
  e.clearSelection();
});
clipboard.on('error', funciton(e){
  console.log('Action:', e.action);
  console.log('Trigger:', e.trigger);
});

new ClipboardJS('.btn', {
  target: function(trigger){
    return trigger.nextElementSibling;
  }
});

new ClipboardJS('.btn', {
  text: function(trigger){
    return trigger.getAttribute('arial-lavel');
  }
});

new ClipboardJS('.btn', {
  container: document.getElementById('modal')
});

var clipboard = new ClipboardJS('.btn');
clipboard.destory();

```


