# Browser and how they work

## What happends when typing URL in the browser

1. The browser gets the `IP address` from cache or Domain Name System(DNS)

   - Check 4 caches
     1. Browser cache
     1. OS cache
     1. Router cache
     1. ISP cache
   - The requested URL is not in the cache, ISP's DNS server initiates a DNS query to find the IP address

1. The browser receives the correct IP address -> Initiate a `TCP connection` with the server

   - With `TCP/IP three-way handshake`. This is a three-step process where the client and the server exchange SYN(synchronize) and ACK(acknowledge) messages to establish a connection.
     1. The client machine sends a SYN packet to the server over the internet, asking if it is open for new connections
     1. If the server has open ports that can accept and initiate new connections, it’ll respond with an ACKnowledgment of the SYN packet using a SYN/ACK packet.
     1. The client will receive the SYN/ACK packet from the server and will acknowledge it by sending an ACK packet.

1. The TCP connection is established -> The browser sends an `HTTP request` to the webserver

   - The request's additional information
     - `User-Agent` header: browser identification
     - `Accept` header: types of requests that the client will accept
     - `Connection` header: control whether the network connection stays open after the current transaction finishes
     - `Cookie` header: contains stored HTTP cookie associated with the server

1. The server handles the request and sends back a response
1. The server sends out an HTTP response

   - About the response code
     - 1XX: an informational message only
     - 2XX: success of some kind
     - 3XX: redirects the client to another URL
     - 4XX: an error on the client’s part
     - 5XX: an error on the server’s part
   - About the response header
     - `Content-Type` header

1. The browser renders the content
   1. The first GET request returns HTML
      - with `Content-Type` header set to `text/html`
      - The browser startparsing the HTML as soon as a few lines of the entire document are available
      - The browser can build the DOM tree incrementally
      - The browser parses HTML from top to bottom
      - `external resource` -> download of that file in the background
        - `script` file
        - `stylesheet` file
        - image file
      - `main thread`: DOM parsing
        - if the main JavaScript execution thread is busy, DOM parsing will not progress until the thread is free
        - IMPORTANT!, only `script` elements are `parser-locking`
        - image, stylesheet, pdf, video, etc. do not block DOM construction(parsing)
   1. The browser makes the subsequent request to the server to get the CSS resource to style the page
   1. construction: `DOM tree` - Document Object Model
      - DOM is a high-level Web API, which provided by the browser
        ![DOM tree](/public/frontend/internet/DOM-tree.png)
   1. construction: CSSOM tree - CSS Object Model
      - CSS stands for `Cascading Style Sheets`
        ![CSSOM tree](/public/frontend/internet/CSSOM-tree.png)
   1. construction: `Render-Tree`
      - Combining DOM and CSSOM trees together
        ![Render tree](/public/frontend/internet/Render-tree.png)
   1. operation: `Layout`
      - Size of each node (in pixels)
      - position, where it will be printed on the screen
      - This process is also called `reflow` or `browser reflow`
      - This process also occur when we `scroll`, `resize` the window or `manipulate DOM` elements
   1. operation: `Paint`
      - Based on element's position, or geometry, etc. Creating `layers`
      - The browser doesn't draw all the layers in a single go. Each layer is drawn separately first
   1. operation: `Compositing`
      - All layers are sent to GPU to finally draw it on the screen

## References

- [what happens when you type an url in the browser](https://medium.com/@maneesa/what-happens-when-you-type-an-url-in-the-browser-and-press-enter-bb0aa2449c1a)
- [How the browser renders a web page](https://medium.com/jspoint/how-the-browser-renders-a-web-page-dom-cssom-and-rendering-df10531c9969#:~:text=When%20a%20web%20page%20is,the%20Render%2DTree%20from%20it.)
