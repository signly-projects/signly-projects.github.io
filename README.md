# Signly Installation Documentation

Signly JavaScript module allows website users to play and request sign language translations. It can simply be included in a web page. An example of this can be seen here [Signly Test Page](https://signly-projects.github.io)

## Include Signly in Website 

### Signly Styles
Append Signly CSS source to head element:
```
<head>
....
<link rel="stylesheet" href="https://cdn.signly.co/release/latest/signly.css">
</head>

### Signly JavaScript
Append Signly JavaScript to content of body element:
```
<body>
...
<script src="https://cdn.signly.co/release/latest/signly.umd.min.js"></script>
</body>
```

## Activating Signly 

Despite being included on the web page, Signly will only be active if the cookie 
key *showSignly* is set to *true*.

### This can be achieved by running the JavaScript function (available globally):
```
window.turnOnSignly()
```

## Deactivating Signly
In order to deactivate Signly, the key *showSignly* will have to be set to *false*

### This can be achieved by running the JavaScript function (available globally):
```
window.turnOffSignly()
```

## Testing functions
1. In a browser, open the link [https://signly-projects.github.io/](https://signly-projects.github.io)
2. Open the Developer tools (CTRL + SHIFT + C)
3. Write the following command in the console to start Signly:
```window.turnOnSignly()```
4. Write the following command in the console to stop Signly:
```window.turnOffSignly()```

## How it works

After all the content of a page has rendered the extension will:
1. Extract all existing text segments
2. Retrieve existing translated text segments for the current page (Signly public REST API)
3. Decorate relevant HTML element

### Page has not been translated

If the page hasn't been translated the user will be able to request it by pressing the 
*Request translation* button. The page data (i.e. title and URL) and all the extracted text 
segments will be sent to Signly's server.

### Page has been translated

If the page has been translated, the user will be able to hover over some text and click play 
to view a sign language translation video. 

If the user is using a mobile device he/she can play a translation by swiping the text. 
Some text contained in a translated web page might not be translated yet, therefore, it'll be shown in 
gray for desktop users and won't trigger any action for mobile user on a swipe action.

## Important Note

Don't include Signly module in pages that contain private data.

