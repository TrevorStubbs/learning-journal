# Read: 13 - [Local Storage](http://diveinto.html5doctor.com/storage.html)

- Native client applications used to be the only way to save things into local storage
- Cookies were invented to provide storage of small amounts of data but they have a few downsides
    1. Cookies are included with every HTTP request, thereby slowing your web application by needlessly transmitting the same data over and over.
    1. Also the data is un-encrypted. (Unless the entire web app is served over SSL)    
    1. Cookies are limited to about 4 KB of data.

## Local storage before HTML5
    - userData was introduce by Internet Explorer
        - allowed for 64KB of data per domain. 
    - Flash Cookies - 100KB
    - Google Gears
    - All these were limited to a single browser or required 3rd party tools. 

## HTML5 Storage, Intro
- HTML5 Storage is called `Web Storage` (aka `Local Storage` or `DOM Storage`)
- store key/value pairs locally within the web browser
- Data is never transmitted to remote web server.

```JavaScript
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}
``` 
or 
```JavaScript
if (Modernizr.localstorage) {
  // window.localStorage is available!
} else {
  // no native support for HTML5 storage :(
  // maybe try dojox.storage or a third-party solution
}
```

- named key is a string
- data is stored as a string
- can use getItem() or use the item like an associative array ([])
```JavaScript
var foo = localStorage.getItem("bar");
// ...
localStorage.setItem("bar", foo);
// or
var foo = localStorage["bar"];
// ...
localStorage["bar"] = foo;
```

- removeing items
```JavaScript
interface Storage {
  deleter void removeItem(in DOMString key);
  void clear();
};
```

- to keep track of changes to the HTML5 Storage area need to trap the storage event.
```JavaScript
if (window.addEventListener) {
  window.addEventListener("storage", handle_storage, false);
} else {
  window.attachEvent("onstorage", handle_storage);
};

function handle_storage(e) {
  if (!e) { e = window.event; }
}
```

