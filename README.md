# A:BC (About:Blank Cloak)
A javascript library for creating websites with hidden urls. Original [Demo](https://fognetwork.github.io/ABC)

## Types
### About
This method seems to be quite old and I first found in an old bookmarklet that had many little features using it to "clone" websites by geting the innerHTML of the whole page and making it in an about:blank page. To use it you just make a new var with a window.open like `var page = window.open()` but not adding a url. Then use innerHTML of document write like `page.document.write("test")`. It has been used in SC and Utopia but can be found in older bookmarklets.

### Blob
This method creates a blob url (a temporary url that thats stores data in a file-like object). It's a feature thats used by many websites and is well documented but not used by the community. You can find the official Mdn docs [here](https://developer.mozilla.org/en-US/docs/Web/API/Blob).

### Overwrite
Just sets the innerHTML of the current page.

## Notes
### How it Works
Basically creates a full screen iframe with whatever url you want.

### Hide From History
The about method does hide the website from your history. The blob one does go into your history but is deleted very soon after. The overwrite method just shows the current website you are on. Extensions like securly that have iframe detection might still see it.

### Unblockable
Despite what you have heard, it will still be blockable because your viewing the website just in an iframe.

## Basic Example
Note: You can also locally host ABC on your website. Just download [this file](https://github.com/py660/cloak/blob/main/index.js) and change the src to `/index.js` or your file path

**HTML**
```html
<script src="/index.js"></script>
```
**Javascript**
```js
//Creates new ABC
var page = new ABC({
    "type": "blank", //Blank, blob, or overwrite
    "url": "https://example.com" //Any url
})
//Set the type
page.setType("blank")
//Set the url
page.setUrl("https://example.com")
//Get iframe code
console.log(page.getCode())
//Open page
var win = page.open()

//View window object (or None for overwrite)
console.log(win.document.body.innerHTML);
```

## Credits
Py660 - Functionality extension

Nebelung - For this thing

Veracity - See below

Both the about:blank method and fullscreen iframe have be around for a while but veracity combined them to from [Utopia](https://discord.gg/hFZC5cgsmq)
