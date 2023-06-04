---
title: "Building a Mini JavaScript Game into a Chrome Browser Extension"
datePublished: Sun Jun 04 2023 20:12:40 GMT+0000 (Coordinated Universal Time)
cuid: clihv0u7a000109ji4yib2udg
slug: building-a-mini-javascript-game-into-a-chrome-browser-extension
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685909541813/57a5772d-bd41-437a-a0df-50cd4296d5dd.png

---

Building a game from scratch with JavaScript can be very interesting and you can even brag about such things to your friends.  
  
What if, you could take a step further and make a Chrome extension with it?

You can also make it available on the Chrome Web Store for more people to share the experience and enjoy your new game. This is a step-by-step guide on how to go about transforming it into a Chrome extension.

### Build Your Game

There are different types of games you can build with JavaScript and in this [Video](https://www.youtube.com/watch?v=rJU3tHLgb_c), You can discover how to create a Whack-a-Mole game.

<iframe width="1019" height="573" src="https://www.youtube.com/embed/rJU3tHLgb_c"></iframe>

This is a game where players try to hit as many moles as possible within a given time.

It involves a grid of holes, and moles randomly pop up at different intervals. Players need to click on the moles to score points.

A basic understanding of HTML, CSS, and JavaScript with an ability to pay close attention is enough to build your game.

once you are done and you have tested your game on your browser, You can now proceed to create the extension

### Create the Manifest File

To turn your game into a Chrome extension, you need to create a manifest file.

It is a JSON file that contains information about your extension, such as its name, description, and permissions.

Here's an example of a manifest file for our Whack-a-Mole game:

```javascript
{
  "manifest_version": 2,
  "name": "Whack-a-Mole",
  "description": "A fun game of Whack-a-Mole!",
  "version": "1.0",
  "icons": {
    "16": "icons/icon16.png",
    "48": "icons/icon48.png",
    "128": "icons/icon128.png"
  },
  "browser_action": {
    "default_icon": "icons/icon48.png",
    "default_popup": "popup.html"
  },
  "permissions": [
    "activeTab"
  ]
}
```

In this example, we specify the manifest version, name, description, version number, and icons of different sizes.

We also define a browser action that displays a popup when clicked. Additionally, we include the "activeTab" permission to allow interaction with the current tab. Now we need to let our Chrome extension work.

### Create the Popup

In order to let the Chrome extension work, We create a popup that appears when users click on the extension icon.

For our game, we'll create a simple HTML file that includes the game itself and a few buttons.

```
<!DOCTYPE html>
<html>
  <head>
    <title>Whack-a-Mole</title>
    <style>
      body {
        width: 200px;
        height: 200px;
      }

      canvas {
        border: 1px solid black;
      }

      button {
        margin-top: 10px;
      }
    </style>
    <script src="game.js"></script>
  </head>
  <body>
    <canvas id="game"></canvas>
    <button id="start">Start</button>
    <button id="stop">Stop</button>
  </body>
</html>
```

In this example, we include a canvas element to display the game and two buttons for starting and stopping the game.

### Package the Extension To package your extension

Compress your game files into a ZIP file and rename the file extension to ".crx".

For example, you can name it "whack-a-mole.crx".

### Conclusion

Congratulations! You have successfully built a game and transformed it into a Chrome extension.

Remember to thoroughly test your game, make improvements and provide an enjoyable user experience. Happy gaming!