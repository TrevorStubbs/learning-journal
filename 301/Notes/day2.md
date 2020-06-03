# Day 2
#### 6/2/20

## Pass by Value vs Pass by Reference
### Value
- Its own memeory block
- numbers, bools, strings
### Reference
- Memory block is shared
- arrays
- objects

## jQuery
- `$('a[href="http://google.com"]")` seleects only anchor tas with an href attribute that links to google.com
- Data-attribute `data-[anything]=[whatever]`
### Setters vs Getters
- Setters = sets or assign a value
- Getters = gets a value
```JavaScript
$('li').text() // => getter
$('li').text('new text') // => setter
```
### Event listener
``` JavaScript
$('#form').submit(function(){})

// submit = event

selector.event(callback)

// or

selector.on(event, callback);
```
## Waiting until the page has loaded
``` JavaScript
$().ready(callback);
// for example
$(document).ready(callback)

 
```

## jQuery `this` vs JavaScript `this`
- jQuery `this` the thing that got clicked on. aka `event.target`

## Event Delegation
- `$('ul li').on('click', callback)` - cant be used on dynamically created tags
- `$('parent').on('event', 'child', callback)` - can be used on dynamically created tags

## Ajax Calls with jQuery
- (Keys to the internet)
- jQuery's build in method for making asynchronous JS requests.
    - We can now go to an endpoint and get data
    - The endpoint can be a URL or a filepath

```JavaScript
//Get the data
$.ajax('/filepath')

// What format is the data
$.ajax('filepath', {method: "GET", dataType: "JSON"})

//tell what do do with the data
$.ajax('filepath', {method: "GET", dataType: "JSON"})
  .then(data => /*do something*/{
    //data only exists within this function
    // ajax takes care of parsing
  })
  //.then is a promise
```


