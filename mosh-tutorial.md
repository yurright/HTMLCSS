# Mosh HTML Tutorial

visual studio

## Install Extension

Prettier Extension

Live Server Extension


## HTML

Hypertext Markup Language (구조)

## CSS

Cascading StyleSheet (마감재)

## Javascript

Adding functionality(interaction) to web pages (엘리베이터로 수직 이동)


## Frameworks

repetitive task done faster

react/angular/vue 대응

## Version Control: Git

## How the Web Works

what happens when you type an address and hit enter?

address is called **URL**: Uniform Resource Location

Resources:
-Web pages (HTML documents)
-images
-video files
-fonts
-...

Client (Browser)

(Web) Server (Computer that hosts the website)

Client Server Model
: client requests a service, and the server provides the service

client says "give me the hompage of this website" to server

this message is formatted based on a protocol called HTTP (Hypertext Transfer Protocol)

HTTP
: language that clients and servers use to talk to each other

not a programming langauge

just textual language

HTTPS
: HTTP + Encryption

the messages exchanged between the client and server are encrypted

http message:
```
GEt /index.html HTTP/1.1
Host: www.codewithmosh.com
Accept-Language: en-us
```
the messages are called HTTP Request, HTTP Response

every data exchange between the client and server involves two messages: request and response

```
HTTP/1.1 200 OK
Date: 1 Jan 2021 09:00
Content-Type: text/html

<!DOCTYPE html>
<html>
...
</html>
```

as the browser reads this html document, it constructs a DOM,

DOM

: Document Object Model
a model that represents the object or elements in the html document

as browser reads HTML document, it discovers references to other resources(images, fonts...)

each of these resources has an address or url

for each resource the browser sends a separate HTTP request to the server to fetch that resource

many of these HTTP requests are sent in parallel 



once the browser has all the necessary resources, it will render the html document


rendering an HTML document means displaying it. 


## Inspecting HTTP Requests and Responses

**dev tool**
**network tab**: inspect network traffic from and to url

if you **reload**, you can see all the requests sent from brower to google.com
at the **bottom** you can see 59 requests, and the amount of data transferred over the network

the first request is the** first http request** that chrome sent to google.com

if you **click** the request you can see more details 

on** headers tab**, you can see all the headers of the request and response

**remote address**: neumeric representation of google.com

below you have **response headers**

has content type, date, 

if you click **preview tab**, you can see a preview of the html document that is returned from the server

all the other subsequent requests are sent to download resources

you can **filter** requests using filter icon

## HTML Basics

index.html : often represents the homepage of webiste

first thing to do: tell the browser that this is an html5 document

doctype declaration:
```
<!DOCTYPE html> // tells browser that this is a html5 document
```
html not case sensitive, but conventionally you type everthing lowercase execpt DOCTYPE

now, we need to use HTML elements to defiine the structure of this web page

the first element is the html element


```
<html></html> // left is opening tag, right is closing tag
```

now, add two elements, head and body
```
<html>
  <head> // use head element to give browser info about this page
  <title>My first web page</title> // title appears on tab 
  </head> 
  <body></body> /
</html> 
```

ip address 127.0.0.1 : references current computer
:5000 : port number on which our web server is listening

so our web server is waiting for http requests on 5000 port

/index.html: name of file

127.0.0.1:5000/index.html

inside body element, add elements that would appear on the page

img element is different from other elements:

1 don't have a closing tag (reason: because img element cannot have any child elements)
```
<img src="" alt=""> // in html5, you don't need />
```
img tag has two **attributes**: src and alt

with attributes, we can supply additional info about an element

src attribute: specify the path of the image
alt : give the browser some text to display in case the image cannot be displayed

text element
```
<p></p> // short for paragraph
```

 use html to define structure, or building block of web pages

 ## CSS Basics
```
<html>
  <head> // use head element to give browser info about this page
  <title>My first web page</title> // title appears on tab
  <style> // this is where we write css code
    img { // img to reference img tag
      width: 100px;  // each declaration contains a property and value
      border-radius: 10px;
    }
    p {
    }  
    p.username { // p tag elements with class username
    }
    .username { // all type of elements with class username
    }
  </style> 
  </head> 
  <body>
<p class="username">1</p>
<p>2</p> 
</body> 
</html> 
```

 to separate the two paragraph tags, you give the <p> tag an attribute called **class**

 class is short for classification, use class attribute to put elements in a diff class(categories)

 ## Inspecting Pages using DevTools
 dev tool elements tab, on the left side you can see the document object model
 
when clicking element,

on the right side you can see styles applied to the elemet

click checkbox to enable/disable, use up/down arrow to change value

on right side upper right conrner you can see where these styles have been applied

## Validating Web Pages
typo, grammar, use validator to identify potential errors in code

validator.w3.org

: standard markup validation service

three methods to validate HTML markup: by address, file, direct input

## CSS Validator

jigsaw.w3.org/css-validator/

## Essential HMTL elements

- text
- links
- images
- lists & tables
- container elements
- structural elements (semantic elements)

## The Head Section 
give browser info about the web page
```
! tab 
```
: get "HTML Boilerplate", the basic HTML template

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"> // defining the character set used in this html document
  <meta name="viewport" content="width=device-width, initial-scale=1.0"> // meta element for configuring viewport
  <title>Document</title> 
</head> 
<body>
</body>
</html> 
```
in head section, there are a couple of **meta elements** that give info about this webpage

the first meta element is for defining the character set

**character set**: map a character to numeric value
- ASCII
- UTF-8

```
<meta name="viewport" content="width=device-width, initial-scale=1.0"> 
```
 **viewport**: visible area of web page

 this element defines the initial width and zoom factor

 we need this element so that the web page looks good on all devices (mobil, tab, desktop)

 every web page should have at leas these 2 meta elements

 other meta

 ```
<meta name="keywords" content="HTML, CSS"> // define keywords that represent this page. for seo
```
but these days, search engines don't put too much weight on these keywords

```
<meta name="description" content=""> // define the description of this page
```
this **description** appears on google!!

## Elements for working with text

```
<body>
<p>I love to teach you <em>HTML!</em> </p>
</body>
```

wrap with **emphasis element ** 

by default browsers display emphasize content in italic : help search engines extract important content in documents!!! seo


```
<body>
<p>I love to teach you <strong>HTML!</strong> </p>
</body>
```

**strong element** similar to emphasis, 

**heading elements**

h1, h2, ... h6

don't choose headings based on size! that is css can always be changed

should be used to create hierarchy!

**every web page should only have 1 h1 element** !! what the page is all about! seo

after h1, should use h2, do not jump to h4

## Entities

how to display special characters like < or > in HTML?
```
$lt;
$gt;
$copy;
$nbsp; //nonbreaking space 잘려서는 안 되는 띄어쓰기
```

dev.w3.org : can see complete list of entities

generate dummy text lorem50(number of words)

## Hyperlinks
to create link, use **anchor element**

```
<body>
  <a href=""></a>
</body>
```
every anchor element should have href attribute

href: short for hypertext reference. = url or link 

relative url: start from current level 
absolute url: start with / : means the root  of the website

href can link to HTML docs, imgs, pdfs etc

```
<a href="images/mosh.jpg" download></a> // since download attribute doesn't have value you can eliminate =""
```
downloads when clicked!

can anchor parts of the html doc too!

give a unique identifier by id attribute
```
  <a href="#section-css">css</a>
<h2 id="section-css"></h2> // define fragement(place) of page
```
can jump to sections!!!

can create jump to top as well 
```
  <a href="#">jump to top</a>
```
link to external website
```
  <a href="https://google.com" target="_blank">Google</a>
```

**target attribute**: link to new tab

link to email

```
  <a href="mailto:dlkasdlfj@gmail.com">email me</a>
```

### what is the difference between a link and a hyperlink?

a link is just an address, the location of the target page
a hyperlink is the element that the user can click on to navigate to that target page

## Images
embedding images

unsplash.com : free images

inspect image squash: dev toll checkbox


### SEO related
<meta title>
<meta desc>
<meta keywords>
<em></em>
h1 h2
image file names! should be descriptive
image alternative text
