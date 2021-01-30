# How to Enable Responsive Styles
## March 11, 2018

To be able to use responsive styles across browsers and devices, make sure this meta tag is in the `head` block of your page:
```html
<meta name="viewport" content="width=device-width,initial-scale=1.0">
```

The `width=device-width` part sets the width ofo the page to follow the screen width of the device, which will vary depending on the device).

The `initial-scale=1.0` part sets the initial zoom level whe the page is first loaded by the browser.

Helpful link: https://www.w3schools.com/tags/tag_meta.asp
