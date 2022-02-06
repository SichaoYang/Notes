# HTML Essential Training
From https://www.linkedin.com/learning/html-essential-training-4

By [Jen Simmons](https://www.linkedin.com/learning/instructors/jen-simmons)

## Introduction
### What is HTML
_\[HTML\] is the way to mark up our content and to bridge the divide between the human language and the computer language._

## HTML
### The role of HTML
_That was the entire point of the Web, the reason it was invented, to provide a way for humanity to share content,
even when our computers are different from each other. It's pretty remarkable.
This is made possible by having three different kinds of programming languages, each doing part of the job._

- Web programming languages
  - **HyperText Markup Language (HTML)**: meaning/structure.
  - **Cascading Style Sheets (CSS)**: appearance/presentation.
  - **JavaScript (JS)**: functionality/behavior. 

- [**The Rule of Least Power**](https://www.w3.org/2001/tag/doc/leastPower.html):
Use the least powerful language suitable for expressing information, constraints or programs on the World Wide Web.
  - HTML is the simplest but also the most fault-tolerant.
  - CSS is more powerful but also more fragile.
  - JavaScript is the most powerful but also the most fragile.

## Formatting Text
### The syntax of HTML elements
_The syntax itself is fairly simple. The trickier part is knowing which tags to use when._

- Anatomy of an HTML **Element**

  | Opening Tag | Content                | Closing Tag | 
  |-------------|------------------------|-------------|
  | `<p>`       | `This is a paragraph.` | `</p>`      |

- Nesting elements

  ```html
  <article>
    <h1>This is a headline.</h1>
    <p>This is the first paragraph.</p>
    <p>This is the second paragraph.</p>
    <p>This third paragraph has <em>text that's emphasized</em> for effect.</p>
  </article>
  ```
  
- **Document Object Model (DOM)**: 
  a document model representing an HTML or XML document as a tree structure in the memory, 
  where each node represents an element of the document, 
  allowing programmatic access to the tree, with which one can change the structure, style, or content of a document.
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
  
### Paragraphs
_The browser knows that these are paragraphs of text because we told it so._

- [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p): a paragraph.
  - ```html
    <p>If you just put all the content in an HTML file with no markup, it just ends up as one big blob on the website. The browser assumes it's all one long string of text.</p>

    <p>We can try to create separate paragraphs by leaving a bunch of space in our HTML file, but that space doesn't count. The browser ignores it. All these words simply add up to a bunch of words in a row.</p>
    
    <p>The browser doesn't know what this is, because we haven't used any HTML yet to tell it what this is.</p>
    ```
### Headlines
_We're not going to pick a headline level based on how it looks, we're going to make a choice based on what it means._

- [`<h1> to <h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements): a headline. 
  - `<h1>` defines the most important _semantic_ hierarchy. 
  - `<h6>` defines the least important _semantic_ hierarchy.
  - ```html
    <h1>Title of this Article</h1>
    <h2>Subtitle that’s usually smaller and maybe longer</h2>
  
    <p>Then the text of the article begins. And you already have a sense of what this is going to be about, because the title and subtitle have set some kind of expectation</p>
    ```

### Bold and Italics
_We aren't just typesetting when we're choosing elements like these. We're conveying semantic meaning, human meaning._

- Italics
  - [`<i>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/i): visual-only italics.
  - [`<em>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em): emphasis italics.
    - ```html
      <p>My <em>favorite</em> character from <i>Sesame Street</i> is Grover.</p>
      ```
- Bold
  - [`<b>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b): visual-only bold.
    - ```html
      <p>This is a paragraph of text. Let's pretend it's part of a long article, where we expect many people to quickly scan through it, and <b>we want to mark certain phrases with some boldness</b>, some visual attention, so that those sentences jump out and people don't miss them. Almost like having a pull-quote.</p>
      ```
  - [`<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong): importance, seriousness, urgency.
    - ```html
      <p><strong>WARNING!</strong> Do not be late.</p>
      ```

### Lists
_We pick \<ul\> because it's the right choice to convey meaning, and then we use CSS to totally alter how it looks._

- [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li): a list item.
- [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul): an unordered list.
  - ```html
    <ul>
      <li>flour</li>
      <li>sugar</li>
      <li>baking powder</li>
      <li>salt</li>
      <li>non-diary milk</li>
      <li>apple cider vinegar</li>
      <li>vanilla</li>
    </ul>
    ```
- [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol): an ordered list.
  - ```html
    <ol>
      <li>In a bowl, mix all the dry ingredients.</li>
      <li>In another bowl, mix together the rest.</li>
      <li>Wisk together.</li>
      <li>Wait 5 minutes.</li>
      <li>Cook the pancakes.</li>
    </ol>
    ```
- [`<dl>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl): a definition list.
  - ```html
    <dl>
      <dt>term</dt>
        <dd>definition</dd>
        <dd>additional definition</dd>
      <dt>second term</dt>
        <dd>definition of second term</dd>
      <dt>third term</dt>
        <dd>definition of third term</dd>
    </dl>
    ```

### Quotes
_Although that is my topographic eye that says that these should be curly quotes,
 for many of you around the world, there are all kinds of other ways that these quote marks should be displayed.
 It depends on the language, the script, or the types of conventions of a particular region._

- [`<cite>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/cite): the title of a creative work.
- [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote): a block quote.
  - ```html
    <blockquote cite="https://www.huxley.net/bnw/four.html">
      <p>Words can be like X-rays, if you use them properly—they’ll go through anything. You read and you’re pierced.</p>
      <p>—Aldous Huxley, <cite>Brave New World</cite></p>
    </blockquote>
    ```
- [`<q>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q): an inline quote.
  - ```html
    <p>Jeremy Keith said, <q>You could open an HTML from back then in a browser today.</q></p>
    ```

### Dates and times
_We use the \<time\> element to format a date or time, anything that's related to a specific moment or range in time,
 into something other computers can understand._

- [`<time>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time): date/time/duration.
  - `datetime`: [machine-readable](https://html.spec.whatwg.org/multipage/common-microsyntaxes.html#times) date and time.
  - ```html
    <time datetime="2025-05-08">May 8, 2025</time>
    <time datetime="2021-10-05">2 days ago</time>
    ```
  - ```html
    <time datetime="12:30">half past noon</time>
    <time datetime="15:45-05:00">3:45 pm in New York</time>
    ```
  - ```html
    <time datetime="2020-11-04T19:00-0500">Wednesday, Nov 4th at 7 pm</time>
    <time datetime="2020-11-04 19:00-05:00">Wednesday, Nov 4th at 7 pm</time>
    ```
  - ```html
    <p>The concert starts at <time datetime="20:00">20:00</time> and you'll be able to enjoy the band for at least <time datetime="PT2H30M">2h 30m</time>.</p>
    ```
    
### Code, pre, and br
_We want to get the spacing into the content itself because it's inherent to the content, 
 it's part of the meaning of this content._

- [`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code): inline code.
  - HTML **entity**: a string starting with `&` and ending with `;`, used to display
    [reserved](https://developer.mozilla.org/en-US/docs/Glossary/Entity#reserved_characters), 
    invisible, and [special](https://html.spec.whatwg.org/multipage/named-characters.html#named-character-references) characters. 
  - ```html
    We can write <code>h4{color:green;}</code> in our CSS, 
    and it will apply to anything marked up as an <code>&lt;H4&gt;</code> element.
    ```
- [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br): line break.
  - ```html
    <p>
    They<br>
    say you took my manhood,<br>
    Momma.<br>
    Come sit on my lap<br>
    and tell me,<br>
    what do you want me to say<br>
    to them, just<br>
    before I annihilate<br>
    their ignorance?<br>
    </p>
    
    <p>—Maya Angelou, <cite>Son to Mother</cite></p>
    ```
- [`<pre>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre): preformatted text.
  - ```html
    <h1>[in Just-]</h1>
    <p>by e.e. cummings</p>
    <pre>
    it's
    spring
    and
    
             the
    
                      goat-footed
    
    balloonMan          whistles
    far
    and
    wee
    </pre>
    ```
  - ```html
    <pre>
    <code>
    &lt;ul&gt;
      &lt;l1&gt;flour&lt;/li&gt;
      &lt;l1&gt;sugar&lt;/li&gt;
      &lt;l1&gt;salt&lt;/li&gt;
    &lt;/ul&gt;
    
    ul {
      color: teal;
    }
    li {
      list-style-type: square;  
    }
    </code>
    </pre>
    ```
    
### Superscripts, subscripts, and small text
_We don't use \<small\> because we just want to make a certain passage of text smaller.
 We use CSS to adjust the size of text to be any size that we want, large or small.
 It is correct, however, to mark text that has a small meaning._

- [`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub): subscript.
  - ```html
    <p>H<sub>2</sub>O</p>
    ```
- [`<sup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub): superscript.
  - ```html
    <p>5<sup>2</sup>=25</p>
    ```
- **Mathematical Markup Language (MathML)**: use [Presentation MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) to display complex mathematical notations inside HTML5 documents.
- [`<small>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/small): 
  side-comments and small prints, like copyright and legal text, with _small prominence_.
  - ```html
    <small>&copy; 2019 Fancy Company</small>
    ```
    
## Understanding the Power of HTML
### Debugging HTML
_We can use developer tools to inspect any website on the internet 
 and peek under the hood to see how other developers use HTML._

- Use **developer tools** to **inspect** HTML.
  - [Chrome DevTools](https://developer.chrome.com/docs/devtools/)
  - [Firefox Developer Tools](https://developer.mozilla.org/en-US/docs/Tools)
  - [Safari Web Developer Tools](https://developer.apple.com/safari/tools/)

### HTML attributes
_But HTML does have a bit more complexity than this, 
 more power that can be added to any element through what's called an attribute._

- HTML attributes

  |         | Attribute               |                       |
  |---------|-------------------------|-----------------------|
  | `<time` | `datetime="2025-05-08"` | `>May 8. 2025</time>` |

- [**Global attributes**](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes): 
  attributes that can be applied to any HTML element.
  - [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/class):
    a space-separated list of the classes of the element, allowing targeting all elements with these classes in CSS and JavaScript.
    - ```html
      <p class="intro">This is the introduction.</p>
      ```
  - [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id):
    an identifier unique in the whole document, allowing targeting the element with this id in links, CSS, and JavaScript.
    - ```html
      <p class="intro" id="article-intro">This is the introduction.</p>
      ```
  - [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable):
    `true`/`false` indicating whether the element should be editable by the user.
    - ```html
      <blockquote contenteditable="true">
        <p>Edit this content to add your own quote</p>
      </blockquote>
      <cite contenteditable="true">-- Write your own name here</cite>
      ```
  - [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang): 
  the language non-editable elements are written in, or the language editable elements should be written in by the user.
    - ```html
      <p lang="en-GB">This paragraph is defined as British English.</p>
      <p lang="fr">Ce paragraphe est défini en français.</p>
      ```
  - [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir):
    `ltr`/`rtl`/`auto` indicating the direction the element's text flows.
    - ```html
      <p dir="ltr">This paragraph is in English and correctly goes left to right.</p>
      <p dir="auto">هذه الفقرة باللغة العربية ، لذا يجب الانتقال من اليمين إلى اليسار.</p>
      ```
      
### ARIA roles
_In fact, in many places it's illegal to make a website inaccessible to people with disabilities.
Yeah, HTML can be a human rights issue._

- [**Accessibility tree**](https://developer.mozilla.org/en-US/docs/Glossary/Accessibility_tree): 
  accessibility-related information based on the DOM tree, used by platform-specific Accessibility APIs to provide a representation that can be understood by assistive technologies, such as screen readers.
- [**ARIA roles**](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA): 
  HTML attributes that provide accessible information about the specific element.
  - ```html
    <h1 aria-label="Hello World">
      <div class="grid" aria-hidden="true">
        <span>H</span>
        <span>e</span>
        <span>l</span>
        <span>l</span>
        <span>o</span>
    
        <span>w</span>
        <span>o</span>
        <span>r</span>
        <span>l</span>
        <span>d</span>
      </div>
    </h1>
    ```

### Formatting HTML
_Browsers will support a range of different options of how you format your code.
 It's really up to you and your team to decide how you want to do it._

- Spacing: browsers ignore spacing beyond one single space unless `<pre>`, `<code>`, `<textarea>`, or specific CSS is used.
- **Comment**: browsers ignore comments between <code>&lt;!--</code> and <code>--></code>.
- Letter case: HTML5 tags are not case-sensitive, but conventionally written in all lowercase.
- Closing tag
  - HTML5 forbids adding a closing tag for [**void elements**](https://html.spec.whatwg.org/multipage/syntax.html#void-elements).
  - The `/` in the opening tag is optional for void elements and self-closing for [foreign elements](https://html.spec.whatwg.org/multipage/syntax.html#foreign-elements).

### Weird Characters
_HTML character entities give you a way to ensure that the browser will put the character that you want on the page,
 including non-breaking spaces._

- HTML entities for reserved characters.
  - `&lt;`: `<`
  - `&gt;`: `>`
  - `&amp;`: `&`
- HTML entities for special characters not on the keyboard.
  - `&copy;`: <code>&copy;</code>
  - `&trade;`: <code>&trade;</code>
  - `&star;`: <code>&star;</code>
- HTML entities for invisible characters
  - `&nbsp;`: a non-breaking space.
    - For avoiding line break between specific words.
    - For adding more than one consecutive space.

## Linking and Navigation
### Links
_The code for creating a link is fairly simple;
the way that  the link transformed computing information and everything about our modern world is profound._

- [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a): a hyperlink to a URL.
  - [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-href): the URL that the hyperlink points to.
  - ```html
    <p>This is a sentence <a href="https://example.com">with a link</a> in the midst of the text.</p>
    ```
  - ```html
    <p><a href="https://example.com">Website<img src="https://tinyurl.com/y3ycfl3e"></a></p>
    ```
- [**Hypertext Transport Protocol (HTTP)**](https://developer.mozilla.org/en-US/docs/Web/HTTP): 
  a protocol for transmitting hypermedia documents between web browsers and web servers.
- [**HyperText Transfer Protocol Secure (HTTPS)**](https://developer.mozilla.org/en-US/docs/Glossary/https):
  HTTP protocol encrypted through [SSL](https://developer.mozilla.org/en-US/docs/Glossary/SSL) or [TLS](https://developer.mozilla.org/en-US/docs/Glossary/TLS).

### URL paths
_Making a well-structured, elegant URL to our webpages is an art.
 It's worth thinking about how your URLs effect user experience and search engine results, 
 and craft them the way that you create any content. 
 Using relative URLs can be super helpful on a project that moves from server to server while it's being worked on._
 
- [**Uniform Resource Locator (URL)**](https://developer.mozilla.org/en-US/docs/Glossary/URL):
  a text string that specifies where a resource can be found on the Internet.
  - `https://example.com/`.
- **Absolute URL**: all information necessary to locate a resource, in the format of `scheme://server/path/resource`.
  - [`scheme`](https://en.wikipedia.org/wiki/List_of_URI_schemes): 
    how the `resource` is to be accessed, like `ftp`, `http`, `https`, `nfs`, etc.
  - `server`: name of the computer where the `resource` is located.
  - `path`: sequence of directories leading to the `resource`.
  - `resource`: optional, default to `index.html` when the web browser requests a URL pointing to a directory.
  - ```html
    <li><a href="https://awesomedogs.com/about">About</a></li>
    <li><a href="https://awesomedogs.com/about/">About</a></li>
    <li><a href="https://awesomedogs.com/about/index.html">About</a></li>
    ```
- **Relative URL**: location of a resource relative to an absolute URL, in the format of `path/resource`.
  - ```html
    <li><a href="/about">About</a></li>
    <li><a href="/about/">About</a></li>
    <li><a href="/about/index.html">About</a></li>
    <li><a href="../about/index.html">About</a></li>
    ```
### Navigation
_We have a lot of options when we start combining HTML elements together.
 By thinking about the many actions and how they combine to layer semantic meaning into our content,
 we can start to get it to the right choices for our projects. 
 There's not one right way. The only for sure is that it depends._  

- [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav): a navigation section.
  - ```html
    <nav role="navigation" aria-label="main menu">
      <ul class="navbar">
        <li><a href="/">Home</a></li>
        <li><a href="/people">People</a></li>
        <li><a href="/prices">Prices</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>
    </nav>
    ```
  - ```html
    <nav aria-label="Breadcrumb">
      <ol class="breadcrumbs">
        <li><a href="/">Home</a></li>
        <li><a href="/blog">Blog</a></li>
        <li><a href="/blog/march">March</a></li>
        <li>March 9th Update</li>
      </ol>
    </nav>
    ```
  - ```html
    <footer>
      <a href="/about/privacy">Privacy Policy</a>
      <a href="/about/legal">Terms of Service</a>
    </footer>
    ```

## Images and Graphics
### Images
_The Web is a web of texts and images._
- [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img): an image.
  - `src`: URL to the image.
  - `alt`: a substitute for the image whenever the image cannot be seen.
  - `width`: the width of the image, enabling layout calculation before the image is downloaded.
  - `height`: the height of the image, enabling layout calculation before the image is downloaded.
  - ```html
    <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/maggie.jpg" alt="shiny black dog looking pensive" width="400" height="300">
    ```
    
## Image formats
_The goal is to have the highest quality possible with the smallest file size possible.
 Each file format takes a different approach to solving this._

- [Image formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types):
  - **Graphics Interchange Format (GIF)**
    - Good for small movies and animations.
    - Does well compressing large areas of a single color.
    - Limited color space of 256 colors.
    - Can do transparency, with jagged edges.
    - Can have multiple frames.
  - **Scalable Vector Graphic (SVG)**
    - Good for logos, icons, illustrations, etc.
    - Vector file: losslessly scalable.
    - _If you can use an SVG, you definitely should._
  - **Joint Photographic Experts Group (JPEG/JPG)**
    - Good for photos.
    - Can be lossily compressed.
    - Tradeoff between image quality and file size.
  - **Portable Network Graphics (PNG)**
    - Good for images that need transparency.
    - Does better compressing photos and images that GIF and JPG depending on the use case.

### Responsive images
_We can use the power of HTML to deliver different image files to different size screens.
 We can make several different files and list them as a set of options in our HTML,
 and let the browser decide which image to download. It can do so in coordination with the operating system, 
 while taking the device hardware capabilities and the network speed into account as well._

- [`srcset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/srcset):
  comma-separated image candidate strings specifying multiple files to be used based on either viewport width or image pixel width.
- ```html
  <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-480.jpg" 
       alt="shiny black dog looking pensive" width="480" height="360"
       srcset="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-960.jpg  2x,
               https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-1440.jpg 3x,
               https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-1920.jpg 4x">
  ```

### Responsive width
_Well, this system is designed to be fast and 
 for the browser to make a decision about which image to download as early as possible in the page loading process. 
 It chooses the image file before the CSS has been parsed and before the layout has happened,
 so the browser has no idea what you're going to do with that image.
 It doesn't know what the size of the box is going to be, where the image is going. 
 If we know the image is going to be a lot smaller than the width of the whole page, 
 we probably want to add more information here for the browser to use when it's making its choice about which file to grab._

- [`sizes`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/sizes):
  comma-separated strings specifying which size image to use at which [media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries).
- ```html
  <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-480.jpg" 
       alt="shiny black dog looking pensive" width="480" height="360"
       srcset="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-480.jpg  480w.
               https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-960.jpg  960w,
               https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-1440.jpg 1440w,
               https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog-1920.jpg 1920w"
       sizes="(max-width: 480px)  240px,
              (max-width: 960px)  480px,
              (max-width: 1440px) 960px,
                                  1920px">
  ```

### Responsive pictures
_HTML gives us a powerful set of options for optimizing images on the web. So we can send the smallest file possible 
 while still publishing gorgeous images that are sometimes displayed quite large...
 On most sites though, the work needed to publish each image in this way is automated._

- [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture):
  a picture containing multiple `<source>` elements and one `<img>` element 
  to offer alternative versions of an image for different display/device scenarios.
- [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source): 
  media sources for the `<picture>`, `<audio>`, or `<video>` element.
  - `media`: [media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries) of the intended media source.
  - ```html
    <picture>
      <source media="(min-width: 600px)"
              srcset="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-320.jpg  320w,
                      https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-480.jpg  480w,
                      https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-720.jpg  720w,
                      https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-960.jpg  960w,
                      https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-1440.jpg 1440w,
                      https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-1920.jpg 1920w">
      <source srcset="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-cropped-320.jpg  320w,
                      https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-cropped-480.jpg  480w,
                      https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-cropped-720.jpg  720w,
                      https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-cropped-960.jpg  960w">
      <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/dog2-480.jpg" 
           alt="black dog lying in the sun" width="480" height="360"
           style="width: 100%; height: auto;">
    </picture>
    ```
  
### Figure and figcaption
_The \<figure\> amd \<figcaption\> elements are handy for anything that appears as 
 a figure illustrating something, or anything that's a demonstration of a concept which needs a caption._

- [`<figure>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure): a figure with optional caption.
- [`<figcaption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption): 
  a caption demonstrating the of content its parent `<figure>` element.
  - ```html
    <figure>
      <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/maggie2.png" width="960" height="720" alt="shiny black dog in the sun">
      <figcaption>Maggie the dog enjoys resting in a field, after a long day of chasing squirrels.</figcaption>
    </figure>
    ```
    
## Media
### Audio
_The \<audio\> element is a good example of the power of HTML to provide a bunch of functionality that 
 maybe we just don't want to bother to build ourselves. We can use what the browser provides._

- [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio): an audio.
  - `controls`: if set, the browser will offer controls including volume, seeking, and pause/resume playback.
  - `loop`: if set, the audio will start from the beginning again when it gets to the end.
  - `autoplay`: if set, the audio will play as soon as the page loads.
    - _Be careful with autoplay. 
       Most people actually hate it when the audio starts playing automatically when they land on a webpage, 
       so maybe don't use that one._
  - ```html
    <audio controls loop autoplay src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/birds.mp3"></audio>
  
    <audio controls>
      <source src="http://example.com/birds.ogg" type="audio/ogg; codec=opus">
      <source src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/birds.mp3" type="audio/mpeg">
      Sorry, your browser doesn't support this audio. 
    </audio>
    ```

- [Audio formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Containers):

  | If you need...	                              | Consider using this container format                                              |
  |-----------------------------------------------|-----------------------------------------------------------------------------------|
  | Compressed files for general-purpose playback | **MPEG-1 Audio Layer III (MP3)**                                                  |
  | Losslessly compressed files	                  | **Free Lossless Audio Codec (FLAC)** <br> with **Apple Lossless (ALAC)** fallback |
  | Uncompressed files	                          | **The Waveform Audio File Format (WAV)**                                          |

### Video
_The power of the Web has revolutionized the way that we connect and share experiences.
Film, television, and, well, teaching have all been transformed by the ability of the Web to transmit video._

- [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video): a video.
  - ```html
    <video controls>
      <source src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/moonwalk.480p.vp9.webm" type="video/webm">
      <source src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/moonwalk.480p.h264.mp4" type="video/mp4">
    </video>
    ```
- [Video formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Containers):
  
  | If you need...	                                    | Consider using this container format                                        |
  |-----------------------------------------------------|-----------------------------------------------------------------------------|
  | General purpose video, preferably in an open format	| **Web Media (WebM)** <br> ideally with **MPEG-4 (MP4)** fallback            |
  | General purpose video	                            | **MPEG-4 (MP4)** <br> ideally with **Web Media (WebM)** or **Ogg** fallback |
  | High compression optimized for slow connections	    | **3GP/3GPP** <br> ideally with **MPEG-4 (MP4)** fallback                    |
  | Compatibility with older devices/browsers	        | **QuickTime** <br> ideally with **AVI** and/or **MPEG-2** fallback          |

- **Adaptive Bitrate Streaming**:
  a method of video streaming over HTTP where the video is encoded at multiple bit rates,
  allowing real-time adjustment of the quality of the stream according to the bandwidth and CPU capacity of the user.
  - Requires a server farm of transcoding robots.
  - Embed code from a video hosting service.

### Captions and subtitles
_It's pretty amazing that we can put audio and video on a website, 
 but not everyone can always hear or understand the audio. ...
 So let's add captions and make our video more accessible to everyone._

- [**Web Video Text Tracks Format (WebVTT)**](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API):
  a format for displaying timed text tracks, such as subtitles or captions, using the `<track>` element.
- [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track): 
  timed text tracks for the parent `<audio>` or `<video>` element.
  - `src`: URL to the `.vtt` track.
  - `kind`
    - `subtitles`: translation and additional background information for users who cannot understand the content.
    - `captions`: transcription and non-verbal information for users who cannot hear the content.
    - `descriptions`: textual description for users who cannot see the content.
    - `chapters`: chapter titles for users who are navigating the media resource.
  - `label`: a user-readable title of the text track to be listed in the player among available text tracks.
  - `srclang`: language of the track text.
  - `default`: if set, use this track unless another track is more appropriate based on the user's preference.
  - ```html
    <video controls>
      <source src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/moonwalk.480p.vp9.webm" type="video/webm">
      <source src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/moonwalk.480p.h264.mp4" type="video/mp4">
  
      <track src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/moonwalk.vtt"
             kind="captions"
             label="English"
             srclang="en"
             default>
  
      <track src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/moonwalk.es-la.es.vtt"
             kind="subtitles"
             label="Español"
             srclang="es">
  
      <p>This would be a video of a moonwalk, if your device supported playing this video.</p>
    </video>
    ```
### Embedding other media through iframes
_It's likely that you'll use a video hosting service and embed the video player that they provide onto your webpage._

- **Embedding**: placing content from one site into the body of a page on another site.
- [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video): 
  a nested browsing context embedding another HTML page into the current one.
  - ```html
    <iframe width="560" 
            height="315" 
            src="https://www.youtube-nocookie.com/embed/0Gr1XSyxZy0" 
            allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>      
    </iframe>
    ```
  - Security
    - Someone else displays your content in an `<iframe>`: 
      avoid [click-jacking](https://developer.mozilla.org/en-US/docs/Web/Security/Types_of_attacks#click-jacking) with
      [X-Frame-Options](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options).
    - You display someone else's content in an `<iframe>`: apply restrictions to the content in the frame with 
      [`sandbox`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-sandbox).
    - You display your own content in an `<iframe>`: safe.
      
## More Ways to Identify Content
### Supporting languages
_The Web, by its very nature, is global. We humans speak hundreds of different languages.
 There are several tools in HTML we want to use to make sure it's clear which language our content is in._
- Benefits identifying languages:
  - Proper search engine results.
  - Proper dictionaries for spell checkers.
  - Proper pronunciation by screen readers.
- `lang`
- `dir`
- [`charset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#attr-charset): 
  the set of characters for the script language.
  - [**ASCII**](https://en.wikipedia.org/wiki/ASCII): 
    an encoding standard limited to 128 characters, focused on the needs of certain European languages.
  - [**Unicode**](https://en.wikipedia.org/wiki/Unicode): 
    a universal encoding standard for characters, encompassing many languages.
    - [**Unicode Transformation Format – 8-bit (UTF-8)**](https://en.wikipedia.org/wiki/UTF-8): 
      one-to-four-byte Unicode backward-compatible with ASCII. 
  - ```html
    <head>
      <meta charset="UTF-8">
    </head>
    ```
    
### Generic elements: div and span
_I hope by now this course has shown you the value of semantic HTML.
You can get away with using divs and spans for everything. ... But it's bad. It hurts a lot of users.
So please, please, please, I beg you, don't use divs and spans for everything. Don't do it.
Use the proper HTML element for the task at hand. ...
They can be handy, div and span, use them when there's not another appropriate element, as a last resort._

- [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div):
  a generic block-level container for flow content.
- [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span): 
  a generic inline container for phrasing content.
  - ```html
    <article lang="en">
      <h1>This is the headline</h1>
      <div class="box">
        <p>The first paragraph.</p>
        <p>Some text in a second paragraph.</p>
        <p>Third paragraph. 
           <span lang="es" class="bilingual">Esta oración está en español.</span> 
           Some of this text is in another language.
        </p>
        <p>Fourth paragraph.</p>
      </div>
    </article>
    ```

## Putting It All Together
### The HTML page
_So the HTML file, that first file that's returned in response to a request for a webpage, \[...\] is pretty important. 
 It functions as the headquarters for everything else that happens after the first moment of the site loading._

- Viewing a webpage
  1. URL: the user inputs a URL or follows a hyperlink.
  2. Request: the browser sends a request for an HTML file.
  3. HTML file: a server returns a single HTML file in response to the request.
  4. Render: the browser reads the HTML file from top to bottom and does what it says.
- Anatomy of an HTML document
  - [`DOCTYPE`](https://developer.mozilla.org/en-US/docs/Glossary/Doctype):
    the required preamble at the top of all documents declaring the era this HTML is from.
    - `<!DOCTYPE html>`: the simplest DOCTYPE recommended by HTML5 in order to activate the 
      [**full standards mode**](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode).
  - [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html): the root.
  - [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head):
    machine-readable information about the document, not to be displayed on the page.
  - [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body):
    the content to be displayed on the page.
  - ```html
    <!DOCTYPE html>
    <html lang="en-US" dir="ltr">
      <head>
        ...
      </head>
      <body>
        <h1>This is a Headline</h1>
        <p>Text in a paragraph.</p>
        <p>Usually there's a lot in here.</p>
      </body>
    </html>
    ```
    
### Document head
_The HTML head is a place to get everything connected and set up to make sure other assets are loaded and 
 to provide data about the page to other sites and platforms. It's the headquarters for starting out the page right._

- [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title):
  the document's title to be shown as a browser tab title or a bookmark title.
- [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta):
  metadata that cannot be represented by other HTML elements.
  - [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name) and `content`: 
    document metadata in name-value paris.
    - [`viewport`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name#standard_metadata_names_defined_in_other_specifications):
      hints about the initial size of the viewport, indicating the responsiveness of the layout.
    - `description`: a short and accurate summary of the content of the page,
      to be shown in search engine results and bookmark descriptions.
    - `keywords`:  comma-separated words relevant to the page's content.
    - `application-name`: the name of the application running in the webpage, to be shown when saved to home screen.
    - `msapplication-TileImage`: tile image of the application running in the webpage.
    - `theme-color`: background color of the application running in the webpage.
    - `author`: the name of the document's author.
- [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link): a link to an external asset.
  - `href`: URL to the asset.
  - `rel`: the relationship [type](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) of the asset to the document.
    - stylesheet
      - ```html
        <link rel="stylesheet" href="main.css">
        ```
    - favicon
      - ```html
        <link rel="icon" href="favicon.ico">
        ```
    - font
      - ```html
        <link rel="preload" href="myFont.woff2" as="font"  type="font/woff2" crossorigin="anonymous">
        ```
    - _The browser will load the files in the order they are listed._
- [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script): 
  executable code or data, typically Javascript.
  - ```html
    <script src="my-javascript-file.js"></script>
    ```

### Structuring content
_Again, it's the semantic meaning that matters here, not the position on the page. 
 Although frequently layout does convey meaning, and these HTML elements are a way to 
 transfer that meaning from graphic design to the marked up content._

- [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main): 
  main content of the `<body>` element, used only once per webpage.
- [Sectioning content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#sectioning_content):
  a section of content, defining the scope of `<header>`, `<footer>`, and 
  [heading content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#heading_content).
  - [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header):
    a header for the nearest sectioning content, containing introductory content about the section, 
    maybe with a logo, a site name, a navigation, a search form, an author name, etc.
  - [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer):
    a footer for the nearest sectioning content, containing information about the author of the section, 
    maybe with links, copyright information, extra information about the company, etc.
  - [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article):
    a self-contained unit of content, independently distributable or reusable.
  - [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section):
    a generic section of content, usually with a heading.
  - [`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside):
    content off to the side, frequently presented as inset panels, sidebars, or call-out boxes.

### Examples of putting it all together
_There's a bit of an art to structuring HTML. We have a lot of creative freedom here.
We are, after all, trying to represent human communication in code.
And while code maybe wants to be correct and prefect, human connection is not._
  
## Forms and Interactive Contents
### HTML form basics
_By using HTML form elements we tap into the power that's built into the browser. We'll save ourselves
a lot of wasted effort trying to recreate in custom JavaScript what's already been built into the browser.
We ensure that our forms will work on every device for every possible combination of input and output hardware,
including devices we've never heard of._

- [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form): 
  a document section containing interactive controls for submitting information.
- [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label): 
  a caption for an item in a user interface.
  - `for`: a single `id` for a [labelable](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form-associated_content) 
    form-related element the `<label>` element is associated to. 
- [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input):
  interactive controls for web-based forms in order to accept data from the user; 
  a wide variety of types of input data and control widgets are available, depending on the device and user agent.
- [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button):
  a clickable button, used to submit forms or anywhere in a document for accessible, standard button functionality.
- Associating a `<label>` with an `<input>`:
  - Help assistive technology understand the semantic meaning of the expected input.
  - Focus and activate the input when the user clicks or touches the label.
  - ```html
    <form action="success.html" method="get">
      <label for="name">Name</label>
      <input name="name" id="name">
      <label for="email">Email</label>
      <input name="email" id="email">
      <button>Sign up</button>
    </form>
    ```
  - ```html
    <form action="success.html" method="get">
      <label>Name <input name="name"></label>
      <label>Email <input name="email"></label>
      <button>Sign up</button>
    </form>
    ```
    
### More on forms
_Forms can get complicated, but by learning about and using the power of HTML, 
 you can make sure that your form works for all users in a way that's clear and frictionless._

- `<input>` attributes:
  - [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#input_types)
    - `text`: default, a single-line text field, with line-breaks automatically removed from the input value.
    - `email`: a field for editing an email address, with validation parameters and relevant keyboard when supported.
  - [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-required):
    if set, a value must be specified or checked for the input for the form to be submittable.
  - [`placeholder`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-placeholder):
    a string as a suggestion or an example for the expected input.
  - [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value):
    initial value of the input control.
- `<button>` [`types`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button#attr-type):
  - `submit`: submit the form data to the server.
  - `reset`: reset all controls to their initial values.
  - `button`: no default behavior.
- ```html
  <form action="success.html" method="get">
    <label for="name">Name</label>
    <input name="name" id="name" type="text" value="Jen">
    <label for="email">Email</label>
    <input name="email" id="email" type="email" required placeholder="me@wxample.com">
    <button type="submit">Sign up</button>
  </form>
  ```
  
### Additional form element types
_There's much more to it all. I just wanted to give you a quick tour of some of the many different HTML form elements
 and how they tap into the power of the browser software and operating system on a wide range of different devices._

- [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea):
  a multi-line plain-text editing control.
  - `rows`: height of the text area specified for consistency across browsers.
  - `cols`: width of the text area specified for consistency across browsers.
- `<input>` [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#input_types)
  - `password`: a single-line text field whose value is obscured, alerted when the site is insecure.
  - `search`: a single-line text field, with line-breaks automatically removed from the input value, 
  displaying a delete icon and/or a search icon when supported.
  - `tel`: a control for entering a telephone number, displaying a telephone keypad when supported.
  - `date`: a control for entering a date, with a date picker or numeric wheels for year, month, day when supported.
  - `color`: a control for specifying a color, with a color picker when supported.
  - `file`: a control for selecting files.
    - `accept`: a comma-separated string list of [unique file type specifiers](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file#unique_file_type_specifiers),
      defining the file types the file input should accept.
    - `multiple`: if set, allow selecting more than on file.
    - `checkbox`: a checkbox allowing single values to be selected/deselected.
      - `checked`: if set, the checkbox is checked by default.
- [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select):
  a control that provides a dropdown list of options.
- [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option):
  an item contained in a `<select>`, an `<optgroup>`, or a `<datalist>` element.
- [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset):
  a group of multiple controls and labels within a web form.
- [`<legend>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/legend):
  a caption for the content of the parent `<fieldset>`.
- ```html
  <!doctype html>
  <html dir="ltr" lang="en-us">
    <head>
      <title>Form Basics</title>
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width, initial-scale=1">
      <link rel="stylesheet" href="styles.css">
    </head>
    <body>
      <main>
        <section class="">
          <h1>Our Form</h1>
          <form action="received.html" method="get">
            <label for="name">Name</label>
            <input id="name" name="name" type="text">

            <label for="email">Email</label>
            <input id="email" name="email" type="email" placeholder="you@example.com">

            <label for="password">Password</label>
            <input id="password" name="password" type="password">

            <label for="search">Search</label>
            <input id="search" name="search" type="search" placeholder="&#128269;">

            <label for="phone">Phone Number</label>
            <input id="phone" name="phone" type="tel">

            <label for="textarea">Text Area</label>
            <textarea  id="textarea" name="textarea" cols="30" rows="15"></textarea>

            <label for="date">Date</label>
            <input id="date" name="date" type="date">

            <label for="color">Color</label>
            <input id="color" name="color" type="color">

            <label for="file">File</label>
            <input id="file" name="file" type="file" accept="image/*" multiple>

            <label for="checkbox">Checkbox</label>
            <input id="checkbox" name="simplecheckbox" type="checkbox" value="The checkbox is checked" checked >

            <label for="selectlist">Choose one</label>
            <select id="selectlist" name="selectlist">
              <option>First Option</option>
              <option>Second Choice</option>
              <option>Third Thing</option>
            </select>

            <fieldset>
              <legend>Checkbox fields inside a fieldset</legend>
              <input id="thischeck" name="checkboxlist" type="checkbox" value="This" checked >
              <label for="thischeck">This</label>
              <input id="orcheck" name="checkboxlist" type="checkbox" value="And Or">
              <label for="orcheck">And/Or</label>
              <input id="thatcheck" name="checkboxlist" type="checkbox" value="That">
              <label for="thatcheck">That</label>
            </fieldset>

            <fieldset>
              <legend>Radio button list inside a fieldset</legend>
              <input id="thisradio" name="radiobutton" type="radio" value="This" checked>
              <label for="thisradio">This</label>
              <input id="orradio" name="radiobutton" type="radio" value="Or">
              <label for="orradio">Or</label>
              <input id="thatradio" name="radiobutton" type="radio" value="That">
              <label for="thatradio">That</label>
            </fieldset>

            <button type="submit">Submit</button>
          </form>
        </section>
      </main>
    </body>
  </html>
  ```
  
## Structuring Tabular Data
### When to use tables
_Does using a table make it more clear what the content means?.
If that's the nature of the information at hand, then use the table in HTML to semantically mark it up as what it is._

### Building table rows
_To create an HTML table, you use several different HTML elements in just the right combination._

- [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table): 
  a table, wrapping around elements belonging to the whole table.
- [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr): 
  a table row, wrapping around elements belonging to the same row.
- [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th): 
  a header for a table column.
- [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td):
  data in a table cell.
  - ```html
    <table class="styled">
      <tr>
        <th>Bird</th>
        <th>Color</th>
        <th>Diet</th>
        <th>Photo</th>
      </tr>
      <tr>
        <td>American Goldfinch</td>
        <td>yellow</td>
        <td>Mostly seeds.</td>
        <td><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/american-goldfinch.jpg" alt="american-goldfinch" width="360" height="261" ></td>
      </tr>
      <tr>
        <td>Bluejay</td>
        <td>blue</td>
        <td>Omnivorous.</td>
        <td><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/blue-jay.jpg" alt="" width="360" height="529" ></td>
      </tr>
      <tr>
        <td>Indigo Bunting</td>
        <td>blue</td>
        <td>Mostly seeds and insects.</td>
        <td><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/indigo-bunting.jpg" alt="" width="360" height="255" ></td>
      </tr>
      <tr>
        <td>Northern Cardinal</td>
        <td>red</td>
        <td>Seeds, insects, berries.</td>
        <td><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/northern-cardinal.jpg" alt="" width="360" height="240" ></td>
      </tr>
      <tr>
        <td>Tufted Titmouse</td>
        <td>grey</td>
        <td>Mostly insects.</td>
        <td><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/10558/tufted-titmouse.jpg" alt="" width="360" height="531" ></td>
      </tr>
    </table>
    ```
    
## Conclusion
### How to keep learning and HTML specifications
_There's more to know about HTML, especially as the language slowly continues to evolve._

- [**MDN Web Docs**](https://developer.mozilla.org/)
- [**HTML: The Living Standard**](https://html.spec.whatwg.org/dev/)
- [**Web Content Accessibility Guidelines (WCAG)**](https://www.w3.org/TR/WCAG/)
