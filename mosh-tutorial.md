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

dev tool
network tab: inspect network traffic from and to url

if you reload, you can see all the requests sent from brower to google.com
at the bottom you can see 59 requests, and the amount of data transferred over the network

the first request is the first http request that chrome sent to google.com

if you click the request you can see more details 

on headers tab, you can see all the headers of the request and response

remote address: neumeric representation of google.com

below you have response headers

has content type, date, 

if you click preview tab, you can see a preview of the html document that is returned from the server

all the other subsequent requests are sent to download resources

you can filter requests using filter icon



