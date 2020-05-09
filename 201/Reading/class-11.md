# Read: 11 - Assorted Topics
- Images pg 406-427
- Practical Information pg 476-492
- [MDN on audio and video](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)
- Flash pg 201-206 (skim)

## Images 406-427
### Controlling the Size of images in CSS
- `width: px;`
- `height: px;`
    - choose 1 or the other. Don't change both.
### Aligning Images
- Use float
    - `float: left;`
### Centering Images with CSS
- by default images are inline elements
1. make the image a block-level element
1. On the containing element you can use `text-align:center`
1. Or on the image itself, you can use the margin property and set the values of the left and right to auto.
```CSS
img.align-center{
  display:block;
  margin: 0px auto;
  }
```
### Background Images
`background-image: url("path/image.gif")`
### Repeating Images
- `background-repeat`
    - `repeat` - background image is repeated vertically and horizontally
    - `repeat-x` - repeats horizontally
    - `repeat-y` - repeats vertically
    - `no-repeat` - image is only shown once
    - `fixed` - image stays in the same position
    - `scroll` - image moves up and down as the user scrolls
### Positioning
- `background-position:`
    - `left top`
    - `left center`
    - `left bottom`
    - `center top` 
    - `center center`
    - `center bottom`
    - `right top`
    - `right center`
    - `right bottom`
### Shorthand
1. color
1. image (url)
1. repeat
1. attachment
1. position
### Image Rollover & Sprite
Set up 3 settings for the same image
1. for no mouse over
1. for hover
1. for active
### CSS Gradient
1. use webkit gradient add a gradient to a background image
### Contrast of Background Images
## Practical Information pg 476-492
### Search Engine Optimization (SEO)
- SEO is the practice of trying to help your site appear nearer the top of search engine resultes. 
- Need to figure out what terms users are likely to search for. 
#### On Page Techniques
- Good Keywords.
- Search engines rely on your text. 
- Make use images have an `alt`
1. Page Title
1. URL/Web Address
1. headings
1. Text
1. link text
1. image alt text
1. page description
    - Live inside the `<head>` tag.
#### Off-Page Technique
- Getting other pages to link to yours. 
- Search engines looks for the words between the `<a>` tags
### Analytics: Learn about your users
- `google.com/analytics`
#### Visiting numbers
- Visits
- Unique Visits
- Page Views
- Pages Per Visit
- Average Time on Site
- Date Selector 
- Export
#### What are they looking at
- Pages
- Landing Pages
- Top exit pages
- Bounce Rate
#### Where are you visitors coming from?
- Referrers
- Direct
- Search Terms
- Advanced features
#### Where are they coming from?
#### DNS
### FTP & Third Party Tools
## [Video and Audio APIs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)
- `<video>` and `<audio>` allows for embedding video and audio into a  page.
- `controls` attribute - allows user to have controls show up.
- HTMLMediaElement` api - provide features to allow you to control video and audio players programmatically
    - `HTMLMediaElement.play()`
    - `HTMLMediaElement.pause()`
    
```HTML 
<div class="player">
  <video controls>
    <source src="video/sintel-short.mp4" type="video/mp4">
    <source src="video/sintel-short.webm" type="video/webm">
    <!-- fallback content here -->
  </video>
  <div class="controls">
    <button class="play" data-icon="P" aria-label="play pause toggle"></button>
    <button class="stop" data-icon="S" aria-label="stop"></button>
    <div class="timer">
      <div></div>
      <span aria-label="timer">00:00</span>
    </div>
    <button class="rwd" data-icon="B" aria-label="rewind"></button>
    <button class="fwd" data-icon="F" aria-label="fast forward"></button>
  </div>
</div>
```
- Styling
```CSS
.controls {
  visibility: hidden;
  opacity: 0.5;
  width: 400px;
  border-radius: 10px;
  position: absolute;
  bottom: 20px;
  left: 50%;
  margin-left: -200px;
  background-color: black;
  box-shadow: 3px 3px 5px black;
  transition: 1s all;
  display: flex;
}

.player:hover .controls, player:focus .controls {
  opacity: 1;
}
```
- controlling the video
```JavaScript
stop.addEventListener('click', stopMedia);
media.addEventListener('ended', stopMedia);

function stopMedia() {
  media.pause();
  media.currentTime = 0;
  play.setAttribute('data-icon','P');
}
```

## Flash 201-206
- Sadly not supported in many browsers anymore (rip homestarrunner)
- Needs a plug-in to work
