# Roy's note

## Stack
**TinyApp**
- Web Server: Node.js
- Middleware: Express
- Template Engine: EJS

**MERN**
Node.js Express MongoDB React

## DOM
At the most basic level, a website consists of an HTML document. The browser that you use to view the website is a program that interprets HTML and CSS and renders the style, content, and structure into the page that you see.  

The browser creates a representation of the document known as the Document Object Model. This model allows JavaScript to access the text content and elements of the website document as objects.

## Event Propagation
**Bubbling**  
When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.

**Capturing**
![EventPropagation](https://github.com/roylyh/lighthouse-web-notes/blob/52f70c7d0173c7a558456a8df58313272848e649/docs/EventPropagation.PNG)

The standard DOM Events describes 3 phases of event propagation:  
- Capturing phase – the event goes down to the element.
- Target phase – the event reached the target element.
- Bubbling phase – the event bubbles up from the element.

[Bubbling and Capturing](https://javascript.info/bubbling-and-capturing)

## Chrome DevTools
[Overview](https://developer.chrome.com/docs/devtools/overview/)