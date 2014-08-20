# Quick recap of JavaScript, Ajax and jQuery

###Prerequisites

Codecademy courses on:
* [JavaScript](http://www.codecademy.com/en/tracks/javascript)
* [jQuery](http://www.codecademy.com/en/tracks/jquery)

###JavaScript

JavaScript was developed for the release of Netscape Navigator 2.0 in 1995 and was added to Microsoft Internet Explorer 3.0 the following year. Notoriously, Brendan Eich [created it in 10 days](https://www.w3.org/community/webed/wiki/A_Short_History_of_JavaScript). Despite being full of bad design decisions and having a syntax that superficially looks like Java, it is has some very powerful programming features--not shared by many mainstream languages--borrowed from languages like Lisp and Smalltalk.
 
It was originally pitched as a nice way to do form validation and was quickly adopted for implementing dynamic page elements, like dropdown menus. It was several years before JavaScript was widely recognised, not as a toy scripting language for pepping up web pages, but as a serious programming language.

###Ajax

By the early 2000s, JavaScript began to be used for populating an already-loaded web page with new content in what became known as Ajax (asynchronous JavaScript and XML) applications. Google launched gmail in 2004 and Google Maps the following year. The widely-used jQuery library was released in 2006. The Google V8 JavaScript engine, which greatly speeded up the execution of JavaScript, was released in 2008 with the first version of Google Chrome.

It is possible to write web server applications without using JavaScript, but no other language will actually run in a web browser.

JavaScript is also used as a server language. Node.js was released in 2009 and has started to become widely adopted for building applications that manage data in real time, such as for gaming, online chat and remote monitoring.

###jQuery

jQuery is a library for manipulating the DOM (Document Object Model). The DOM is a convention for describing and manipulating the elements of an HTML document, which treats the document as a heirarchical tree with HTML tags as nodes in that tree.

There is a good summary of [how jQuery works](http://learn.jquery.com/about-jquery/how-jquery-works/) on the jQuery website.

There is also a good [introduction to the DOM](http://www.w3.org/TR/DOM-Level-2-Core/introduction.html) at W3C.

####How to use jQuery

you can download jQuery, but for now we recommend linking to jQuery via a [CDN](https://code.jquery.com/) and creating a separate link to a local _application_ file. In order to reduce load times, link to both files at the bottom of your document:

        <script src="//code.jquery.com/jquery-2.1.1.min.js"></script>
        <script src="/js/application.js"></script>
      </body>
    </html>

(For an explanation of that '//' prefix, see Paul Irish on [The Protocol-relative URL](http://www.paulirish.com/2010/the-protocol-relative-url/))
    
The application.js file should look something like this:

    $( document ).ready(function() {

        // add your code here

    });

