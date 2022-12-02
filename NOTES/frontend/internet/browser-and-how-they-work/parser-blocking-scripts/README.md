# Parser-blocking scripts

## Definition

A script(JavaScript) file/code that stops the parsing of the HTML

When the browser encounters a script element

- `embedded script`, the browser will execute the script first and then continue parsing the HTML
- `external script file`
  1. The browser will start the download of the file off the main thread
  1. The browser will halt the execution of the main thread until that file is downloaded
  1. Once the script file is downloaded, the browser will first execute the downloaded script file on the main thread and then continue with the DOM parsing

## Why so important?

Because `script` elements are `parser-blocking`. Every external file requests such as `image`, `stylesheet`, `pdf`, `video`, ect. do not block DOM construction (parsing) except script file requests

## script attribute: async v.s. defer

![async-vs-defer](/public/frontend/internet/whats-the-difference-between-async-vs-defer-attributes.jpeg)

## References

- [#Parser-Blocking Scripts](https://medium.com/jspoint/how-the-browser-renders-a-web-page-dom-cssom-and-rendering-df10531c9969#:~:text=When%20a%20web%20page%20is,the%20Render-Tree%20from%20it.)
- [race conditions](https://stackoverflow.com/questions/34510/what-is-a-race-condition)
