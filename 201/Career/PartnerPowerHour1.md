# Partner Power Hour 1
#### 5/1/20

Presenter - Dale Sande who works for Alaska Airlines.
- Topic was about: Lit-element library.
- Was a previous instructor
- frameworks are opinions
    - opinions leads to standards
    - there can be many different standards
- design systems
    - Don't just fork.
- Components
    - which framework?

- Design / Code
    - low resources, high expectations
- Design systems
    - Drive design consistence
- Sketch (design) / HTML/SASS (code) or react?    
- Copy/Paste HTML <ins>will</ins> mutate
    - Contracts will be broken.
- CSS naming conventions are <ins>doomed</ins> to fail.
- No more monolithic framework

- Web components
    - Encapsulated CSS.
    - Encapsulated JS.
    - Encapsulated UX.

- What happens in the shadow DOM stays in the Shadow DOM.

```JavaScript
import {LitElement, html} from 'https://unpkg.com/lit-element/lit-element.js?module';

class MyElement extends LitElement{
  render() {
    return html`
    <slot></slot>
    `;
  }
}

customElements.define('my-element', MyElement);
```

How did it affect my approach

Other takeaways: 

Look up web components. Look up SASS. Shadow DOM

- Specialize in .net web component implementation? 

- Culture 

@anotheruiguy