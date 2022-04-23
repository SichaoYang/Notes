# Web Programming Foundations
From https://www.linkedin.com/learning/web-programming-foundations

By [Morten Rand-Hendriksen](https://www.linkedin.com/learning/instructors/morten-rand-hendriksen)

## Introduction
### Welcome
_Knowing how the internet works and how to work with it, all the way the from the code editor to the mobile browser and beyond, is essential to anyone wanting to publish their ideas on the web._

```
user -> URL -> browser -> request -> server -> HTML document -> resource referenced by the HTML document: content + media (images, audio, video) + style (style sheets) + interactivity (JavaScript) -> browser -> user
```

## Deconstructing the Web
### From URL to website
_Front-end web development is focused on how to make the stuff that ends up in the browser. Knowing how it gets there helps explain some of the things we do when we build the creations that live on the web._

```
URL -> browser -> DNS request -> DNS cache/server -> IP address -> browser -> HTTP request -> server
```
- [**IP Address**](https://developer.mozilla.org/en-US/docs/Glossary/IP_Address): a number assigned to every device connected to a network that uses the Internet protocol, typically a 32-bit IPv4 address.
- [**Uniform Resource Locator (URL)**](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL): the address of a unique resource on the Web, written as `<Scheme>://<Domain>:<Port number><Path to resource><Parameters><Anchor>`.
  - E.g. `http://www.example.com:80/path/to/index.html?key1=value1&key2=value2#SomewhereInTheDocument`
  - [Scheme](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#scheme): the protocol that the browser must use to request the resource, e.g. HTTP or HTTPS for websites.
  - [Domain](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#authority): a human-readable domain name or numeric IP address.
    - [Domain name](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_domain_name): a human-readable address for a web server, read from right to left.
      - E.g. `developer.mozilla.org`
      - [Top-Level Domain (TLD)](https://developer.mozilla.org/en-US/docs/Glossary/TLD): general purpose of the service behind the domain name maintained by [ICANN](https://data.iana.org/TLD/tlds-alpha-by-domain.txt).
        - Generic TLDs: `.com`, `.org`, `.net`, ...
        - Local TLDs: `.us`, `.cn`, ...
        - Government department TLD: `.gov`.
        - Educational and academic institution TLD: `.edu`.
      - Label: 1-63 letters, numbers, and `-` between the letters and numbers.
        - Secondary Level Domain (SLD): the label right before the TLD.
        - A domain, e.g., `mozilla.org`, can have arbitrary sub-domains, e.g., `developer.mozilla.org`, `iot.mozilla.org`, and `bugzilla.mozilla.org`.  
  - [Port number](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#authority): a 16-bit unsigned number identifying one of the ports, which provide a multiplexing service for multiple services or multiple communication sessions at one network address, usually omitted when using the standard ports of the HTTP protocol (80 for HTTP and 443 for HTTPS).
    - [Well-known port numbers](https://en.wikipedia.org/wiki/Well-known_port_numbers): port numbers lower than 1024, reserved for system processes.
    - [Ephemeral ports](https://en.wikipedia.org/wiki/Ephemeral_port): higher-numbered ports, available for general use by applications.
  - [Path to resource](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#path_to_resource): physical or abstracted location of the resource on the server.
  - [Parameters](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#parameters): extra parameters provided to the server.
  - [Anchor](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#anchor): an anchor to an internal part of the resource, parsed by the browser and never sent to the server. 
- [**Domain Name System (DNS)**](https://developer.mozilla.org/en-US/docs/Glossary/DNS): a hierarchical and decentralized naming system for Internet connected resources, maintaining a list of domain names along with associated resources, such as IP addresses.
  - **DNS lookup**: the process of mapping a domain name to the appropriate IP address.
  - **Reverse DNS lookup (rDNS)**: the process of finding the domain name associated with an IP address.

### The web, in a browser
_Remember, every webpage and every website is a document, and a properly structured document is readable and accessible, even without all the fancy colors and fonts and layouts, which kind of is the whole point of the web. Serve up the content in a uniform format, and let people decide how to access that content. [...] The web browser is an advanced viewer for web documents, nothing more, nothing less._

### The structure of a web document visualized
_Remember, what you see in your browser is a carefully structured document displayed as a collection of boxes with different properties. [... E]verything is a box within a box within a box._

- Hierarchical structure of elements:
  - Clear, content-independent structure.
  - Style inheritance.

### The node tree: How the browser sees a web document
_Remembering that every element is a box, and that every box is a node on the tree connected to its parents, siblings, and descendants via branches is key to understanding how the browser sees the Web and how you can give the browser sufficient information to do what you want._

- **Document Object Model (DOM)**: a document model representing an HTML or XML document as a tree structure in the memory, where each node represents an element of the document, allowing programmatic access to the tree, with which one can change the structure, style, or content of a document.
  - E.g. 
    ```
    └── ARTICLE
        ├── #text:
        ├── H1
        │   └── #text: This is a headline.
        ├── #text:
        ├── P
        │   └── #text: This is the first paragraph.
        ├── #text:
        ├── P
        │   └── #text: This is the second paragraph.
        ├── #text:
        ├── P
        │   ├── #text: This third paragraph has 
        │   ├── EM
        │   │   └── #text: text that's emphasized
        │   └── #text: for effect.
        └── #text:
    ```

### HTML: The source code of the web
_Talking to web designers and developers will often find they make these drawings either in their heads or on paper in a design application to visualize these relationships before the code reaches the browser. And eventually, it becomes second nature to break down everything you see in a browser as a logical grouping of boxes, which represent nodes on a DOM tree, which represent tags in an HTML document, which means we've come full circle from what we see in the browser to how that content was written and all the way back again._

- [HTML Essential Training](https://github.com/SichaoYang/Notes/blob/main/HTML%20Essential%20Training.md)

### The web document is a document with superpowers
_The web was built to make information accessible, shareable, and linkable. With HTML, any web document can link to contents within itself, to other contents on the same domain, or to any content anywhere on the web. That is why it's called the World Wide Web. It's quite literally a web of links tying information from all over the world together, and making it all accessible through a web browser to date, and to other means we have yet to come up with in the future. And the best thing, the superpower of HTML belongs to everyone._


## The Duality of Web Programming
### The dual purpose of web code
_To reiterate, you have two goals, communicate with a human consumer and communicate with a machine. To do this, you must effectively write the content, identify the nature, property, purpose, and relationships of each element of that content and mark everything up accordingly._

- Web programming for **people**: accessible, understandable, and usable **content**.
- Web programming for **machines**: clearly marked up and declaratively codified **structure**.

### Content and structure
_Semantic HTML is the key to bridging the gap between content and structure, and, used correctly, it makes the content more accessible for everyone, both humans and computers._

- [HTML Essential Training](https://github.com/SichaoYang/Notes/blob/main/HTML%20Essential%20Training.md)

### Metadata and purpose
_All of these tools are designed to do the same thing. To assist humans in finding and accessing the content they are looking for, and to assist clients, search engines and other tools in cleaning meaningful data about the document and it's content, again, to assist human users._

- [**Metadata**](https://www.w3.org/TR/2008/PR-SVGTiny12-20081117/diff/metadata.html): nonvisual data added to a web document to provide further information about purpose and function.
  - [HTML `<head>`](https://github.com/SichaoYang/Notes/blob/main/HTML%20Essential%20Training.md#document-head)
  - Element-level meta
    - [**Microdata**](https://developer.mozilla.org/en-US/docs/Web/HTML/Microdata): HTML global attributes that use a supporting vocabulary to describe an item and name-value pairs to assign values to its properties, which can be extracted by search engines and web crawlers to provide a richer browsing experience for users.
      - [Schema.org](https://schema.org/): a provider of vocabulary for structured data.
      - [Global attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Microdata#global_attributes)
        - [`itemscope`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemscope): a boolean that creates an item with properties defined within the element.
        - [`itemtype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemtype): a URL of a vocabulary that describes an item and its properties context.
        - [`itemprop`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemprop): a name defined by the vocabulary, which forms a name-value pair, a property of an item, with the content of the element. 
      - E.g.
        ```html
        <div itemscope itemtype="https://schema.org/SoftwareApplication">
          <span itemprop="name">Angry Birds</span> -

          REQUIRES <span itemprop="operatingSystem">ANDROID</span><br>
          <link itemprop="applicationCategory" href="https://schema.org/GameApplication"/>

          <div itemprop="aggregateRating" itemscope itemtype="https://schema.org/AggregateRating">
            RATING:
            <span itemprop="ratingValue">4.6</span> (
            <span itemprop="ratingCount">8864</span> ratings )
          </div>

          <div itemprop="offers" itemscope itemtype="https://schema.org/Offer">
            Price: $<span itemprop="price">1.00</span>
            <meta itemprop="priceCurrency" content="USD" />
          </div>
        </div>
        ```
    - [**Microformats**](https://developer.mozilla.org/en-US/docs/Web/HTML/microformats): standards used to embed semantics and structured data in HTML, and provide an API for social web applications, search engines, aggregators, and other tools.
      - [Microformats class name prefixes](https://developer.mozilla.org/en-US/docs/Web/HTML/microformats#microformats_prefixes)
        - `h-*`: a root class name that indicates a type and the corresponding vocabulary of properties.
        - `p-*`: plain text properties. e.g. `p-name`, `p-summary`.
        - `u-*`: URL properties, e.g. `u-url`, `u-photo`, `u-logo`.
        - `dt-*`: datetime properties, e.g. `dt-start`, `dt-end`, `dt-bday`.
        - `e-*`: element tree properties where the entire contained element hierarchy is the value, e.g. `e-content`.
      - [Microformats rel property](https://microformats.org/wiki/existing-rel-values)
      - E.g.
        ```html
        <p class="h-card">
          <img class="u-photo" src="https://example.org/photo.png" alt="" />
          <a class="p-name u-url" href="https://example.org">Joe Bloggs</a>
          <a class="u-email" href="mailto:joebloggs@example.com">joebloggs@example.com</a>,
          <span class="p-street-address">17 Austerstræti</span>
          <span class="p-locality">Reykjavík</span>
          <span class="p-country-name">Iceland</span>
        </p>
        ```
    - [**Accessible Rich Internet Applications (ARIA)** attributes](https://github.com/SichaoYang/Notes/blob/main/HTML%20Essential%20Training.md#aria-roles)


### Accessibility
_Content should be accessible regardless of what tool the visitor uses to access it._
- Game plan:
  1. Make it accessible.
  2. Make it fancy.
  3. Don't break accessibility.
- Day-to-day processes:
  1. Start with semantic, standards-compliant HTML.
  2. Run accessibility checks.
  3. Fix issues before moving forward.
  4. Bring in accessibility consultants and testers.
  5. Make a maintenance and iteration plan.

## Which Came First: the Browser or the Editor?
### The web browser of today and of tomorrow
_Even though the content we publish on the web today should work in old browsers, it should not be built for those browsers. Instead, the content should be separated from its presentation and browser-specific solutions like CSS and JavaScript should be added on as one option for accessing that content. That's the way to build solutions for today and for the future._

- Cross browser testing
  - Multiple browsers and browser versions.
  - Various physical devices and device labs.
  - [BrowserStack](https://www.browserstack.com/): an online tool for automated cross browser testing.
- Cross browser accessibility
  - Follow accessibility and web standards for everyone.
  - Employ progressive enhancements for modern browsers.
  - [**Representational state transfer (REST)**](https://restfulapi.net/)

### What is a code editor?
_For the most part, code editor preference is exactly that, a preference._

- Code editors
  - Editing code
    - Syntax highlighting
    - Code hinting
    - Project management
  - Previewing code 
    - What You See Is What You Get (WYSIWYG) editor: code and preview in the same editor, suboptimal in practice due to emulation inaccuracy.
    - Real browsers

### Developer tools
_Browser tools are an essential part of web development._

- Browser developer tools: tools built into every modern browser, allowing inspection of the code, network conditions, and other properties of the current document running in the browser.
  - [Chrome DevTools](https://developer.chrome.com/docs/devtools/)
  - [Firefox Developer Tools](https://developer.mozilla.org/en-US/docs/Tools)
  - [Safari Web Developer Tools](https://developer.apple.com/safari/tools/)

## The Parts That Make up the Web

### HTML
_The web is still HTML, but how that HTML is created is changing and will continue to change._

- [**HTML** Essential Training](https://github.com/SichaoYang/Notes/blob/main/HTML%20Essential%20Training.md)

- Who writes the HTML?
  - Human + code editor
  - Human + server-side app
  - Human + JavaScript framework

### CSS
_This is how CSS adds a presentational layer to web documents: starting from the default browser styles and targeting first the most general element and then moving in to the most specific ones, we create rules to describe their appearance. The trick is to figure out how to make as few rules and property declarations as possible to create the most impact. In CSS, as in everything else that has to do with code, smaller and simpler is always better._

- [**CSS** Essential Training](https://github.com/SichaoYang/Notes/blob/main/CSS%20Essential%20Training.md)

### JavaScript
_What sets JavaScript apart from other web programming languages like PHP and Ruby is it executes in the browser rather than on the server. In other words, the interactivity happens locally on whatever device is accessing the document, and in many cases it can run even if the internet and the connection to the web server is cut._

- [**JavaScript** Essential Training](https://github.com/SichaoYang/Notes/blob/main/JavaScript%20Essential%20Training.md)
- JavaScript in a nutshell: small programs running in the browser that interact with the DOM by targeting DOM nodes and reacting to browser events.
- The evolution of JavaScript
  - Traditional JavaScript: manipulating HTML and CSS in the browser viewport to add interactivity.
  - Modern JavaScript: Running in the browser or on a server to generate new documents and views.
- Browser rendering of HTML, CSS, and JavaScript
  1. Downloading the HTML document and indexes all its contents.
  2. Downloading the CSS and JavaScript the document references.
  3. Running the JavaScript to see if the HTML changes.
  4. Applying the CSS.
  5. Keeping the JavaScript running in case an interaction or event triggers further scripts. 

### The Document Object Model (DOM)
_The browser creates the DOM based on the semantic markup in the HTML document. We can then use CSS rules and JavaScript to apply presentational elements and behaviors to elements and content in the document by targeting these nodes in the DOM._

### Events
_Whenever you interact with the browser in any way, you fire an event and the browser reacts to that event with pre-configured responses. Using JavaScript, we can write our own scripts to respond to these events as well._

- ```
  HTML -> DOM -> JavaScript -> CSS
  |^     |^         |^        |^
  v|     v|         v|        v|
            Events
  ```
- [**Events**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events): actions or occurrences that happen in the system you are programming, which the system tells you about so your code can react to them.
- [**Event Handling**](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers): detecting and responding to an event using JavaScript.
  1. Identifying a DOM node to monitor.
  2. Identifying the event you want to respond to.
  3. Creating a function to run when the event is triggered.

### Putting it all together
_To accurate replicate the web environment on your computer, you need to run a local web server._

- Setting up a local web server
  - Large, complex applications for large, complex sites
    - Virtual machines, e.g. [Vagrant](https://www.vagrantup.com/).
    - Full web servers, e.g. [WampServer](https://www.wampserver.com/), [MAMP](https://www.mamp.info/).
  - Code editor extensions for live servers: functionality added to the code editor to spin up a small, local server environment that syncs to the code editor and the browser, e.g. [Live Server for Visual Studio](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).
  - [Browsersync](https://browsersync.io/): a module for Node.js for synchronized browser testing accessible from any browser on any device through the local network.

## Conclusion
### Next steps
_My goal for this course was to give you an in-depths look at how the web works and how to work with it. By watching this course, you now have an understanding of web programming fundamentals and you know how all the main pieces fit together. This knowledge becomes the foundation on which you build your web programming practice and we have all the courses to get you going._