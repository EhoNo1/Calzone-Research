# 3D Worlds and The Web
I've had the privalege of learning a lot about how the web works from an Instructor who, for a period of time, also developed the front and backend for many of my college's actual web apps and infrastructure. *In fact*, if you want a good reference on how to make client-side web applications: [here's the textbook we're using](https://info340.github.io/). It's Creative Commons licensed.
## The Shape of Web Content
The web as we know it today is governed by a near universal design principle that will be familiar to anyone who writes code regularly; [Separation of Concerns](https://en.wikipedia.org/wiki/Separation_of_concerns). To put it simply, when following the design principle of Separation of Concerns; you should separate different parts of your program that handle different fundamentally different tasks in your program. 

This design principle simplifies project design and encourages modularity. For the web this design principle has been widely accepted and adopted into our modern web browsing experience.

Currently; the whole of a 2D web page is broken into 3 distinct domains of concerns; **Content,** **Style,** and **Interactivity**. Much of the modern web uses [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) for the Content, [CSS](https://www.w3schools.com/Css/) to define formatting, and [Javascript](https://developer.mozilla.org/en-US/docs/Web/javascript) to define special interactivity and functions beyond body and style.

Actually, if you only care about content; you don't even need write any CSS or Javascript. From a technical standpoint, they are 100% optional. (Aesthetically however, you'll at least want *some* style.) I won't go into detail about how to use them, take a look at the [textbook I mentioned earlier](https://info340.github.io/) if you are really interested.

Now, this is really interesting, because it means that when you browse to a web page you're actually only asking for the *content* of the page. Once that content arrives; it itself then contains references to stylesheets and dynamic code that it needs, that your web browser then goes and requests separately. 

This *sounds* inefficient on the surface; but its quite the opposite. This structure means that the content, *the thing that actually matters* is always delivered first. On top of that, since the web browser is the one making the decision to load content; you could selectively *just not* load optional content that you don't want or your device/connection can't handle. Not to mention the improved resource efficiency! Many website use the same style across multiple pages; but this design pattern means that each page on the site can just to *the exact same stylesheet file.* And don't even get me started on the potential network efficiencies of *caching* commonly used files.

Cool! This seems to flow in stark contrast to how VRChat seems to work. (Full disclosure, this is an educated guess as VRChat is a proprietary, closed-source project. The best I can do that doesn't break TOS.) When you create content for VRChat, the uploader compiles your assets into a package file then sends that off to their Content Delivery Network (CDN). In-game, when someone loads your content; be it an avatar or world, the game appears to download the **entire** file before loading.

VRChat's CDN operates at starkly different scales than a common web browser. *And yes it would be uncanny to have people's avatars load in peicemeal.* But for worlds especially, it feels strange to do it this way. We've already hit a bit of a problematic trend with *larger* and **larger** and ***larger*** world sizes to the point where a not insignificant number of users *struggle* to run them.

Now, obviously there would be some new challenges to tackle, but as a designer; I can't stop myself but wonder if VR worlds could be improved by adopting an internal structural pattern similar to web pages?
## The Next Step

https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction

https://www.web3d.org/x3d4
