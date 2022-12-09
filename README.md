# snippets
Helpful (I hope so) js code snippets

## 📈 Google Analytics browser debuger
My little analytics tasks helper.  
Snippet sent new events in the browser console. 
No install needed, just `dataLayer` global object on your page.

Just copy-n-paste this code to your browser console on the page with events you wants to catch. Preserve log is an option.
```js
((a, time) => {
  if (!a) return;
    let len = a.length;
    setInterval(() => {
      if (a.length > len) {
        a.slice(len, a.length).forEach(i => (
          console.log("\n🚀 " + new Date().toLocalString() + " Event fired"),
          console.table(i)
        );
        len = a.length;
      }}, time)})(dataLayer, 500);
```

Every 500ms the script compare saved dataLayer array, if found some, sent the new one to console
