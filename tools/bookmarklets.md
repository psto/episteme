# Bookmarklets

Create a new bookmark and paste the JavaScript code in the URL box. Set an easy to remember keyword.

* [Kill sticky headers](https://alisdair.mcdiarmid.org/kill-sticky-headers/) to remove annoying sticky headers.
* [sci-hub.tw shortcut](research-papers.md#TIP)
* to [see a dead page](https://en.wikipedia.org/wiki/Help:Using_the_Wayback_Machine#JavaScript_bookmarklet) with the [Wayback Machine](https://web.archive.org/): 
```javascript
javascript:(function(){window.location.href = "https://web.archive.org/web/*/"+window.location.href;})();
```
* save a web page: 
```javascript
javascript:void(window.open('https://web.archive.org/save/'+location.href));
```
* remove distractions from an article:
```javascript
javascript:(function(){window.location.href = "https://outline.com/"+window.location.href;})();
```
* google site search the entire page:
```javascript
javascript:q=%22%22+(window.getSelection?window.getSelection():document.getSelection?document.getSelection():document.selection.createRange().text);if(!q)q=prompt(%22Search%20terms%20%5Bleave%20selection%20and%20box%20blank%20to%20list%20all%20pages%5D%20...%22).replace(/%5Cs%5C+/g,%22%252B%22);if(q!=null)location=%22http://www.google.com/search?q=%22+q.replace(/%5Cs+/g,%22+%22)+%22+site:%22+location.hostname;void(0);
```
* translate the current page:
```javascript
javascript:{var d,b,o,v,p;b=(d=document).body;o=d.createElement('script');o.setAttribute('src','https://translate.google.com/translate_a/element.js?cb=googleTranslateElementInit');o.setAttribute('type','text/javascript');b.appendChild(o);v=b.insertBefore(d.createElement('div'),b.firstChild);v.id='google_translate_element';v.style.display='none';p=d.createElement('script');p.text='function googleTranslateElementInit(){new google.translate.TranslateElement({pageLanguage:""},"google_translate_element");}';p.setAttribute('type','text/javascript');b.appendChild(p);};void(0);
```
* define words with google
```javascript
javascript:d=%22%22+(window.getSelection?window.getSelection():document.getSelection?document.getSelection():document.selection.createRange().text);d=d.replace(/%5Cr%5Cn%7C%5Cr%7C%5Cn/g,%22%20,%22);if(!d)d=prompt(%22Enter%20the%20words:%22,%20%22%22);if(d!=null)location=%22http://www.google.com/search?q=define:%22+escape(d).replace(/%20/g,%22+%22);void(0);
```
