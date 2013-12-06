
Awesome-mode Generator Plugin
===

TODO: 日本語化

This is an experimental node.js plugin for Photoshop's [Generator][1] extensibility layer. It currently implements three possibly-fun-and-or-humorous features: voice recognition, spoken feedback, and brush drawing via Leap Motion.

#### Demo:

[![Video demo of plugin](http://andyhall.github.io/generator-awesome/images/generator-demo.png)](https://www.youtube.com/watch?v=_B9gF-iRhiU)

#### Notes:
* This plugin is not meant for real-world use! It demonstrates some random things that can be done with Generator and might perhaps inspire some more useful development.
* At the moment this has only been tested on a few machines, and not at all on Windows. Issue reports and pull requests are welcome!
* Code is in demo state right now, there is some architectural weirdness to be cleaned up.

## Installation

 1. Install [npm][2] if you haven’t already.
 2. Clone or download the [generator-core][3] repository
 3. In a terminal, from `generator-core` folder, run:  `npm install`
 4. Clone or download [this][4] repository, and from inside the folder run `npm install`
 5. Install [julius][5]. The easiest way is probably to use [macports][6] and run the command `sudo port install julius`, but it can also be built from source, or perhaps run from binaries.  
> If you have trouble installing julius on Mac, installing portaudio may fix the problem. Try doing `sudo port install portaudio` and then installing julius again.

## Using the plugin

1. Start Photoshop and open a new file.
2. Run the command: `node path/to/generator-core –f path/to/awesome.generate`  
> If you get an error like "connection refused", open **Preferences > Plugins** and make sure Generator and Remote connections are enabled, and the password field is set to the default value 'password'.
3. Wait for the plugin to initialize, and then select **File > Generate > Awesome mode**
4. If julius is installed then voice commands should now be recognized, and if you have a Leap Motion device then it should be detected. 

### Voice commands

To use voice commands, preface each command with `Okay Photoshop`. You can also chain together commands with `Thank you`. That is: `Okay Photoshop... [command].. Thank you.. [command]..`

Recognized commands:

* [New / Duplicate / Delete] Layer
* Random color
* Clouds
* Undo
* Voice mode

### Voice mode

When enabled, the plugin responds to voice commands via the `say` utility. Enable it by saying `Okay Photoshop.. Voice mode`.

### Leap motion

If you have a Leap motion device, connect it any time and point with one finger. If you hover on the near side of the device (the side towards you), the plugin will mark the hover position with guide lines. To draw, move your finger forward over the plane of the device. Performance is poor for this right now - finding a faster way to draw is on the todo list.


  [1]: https://github.com/adobe-photoshop/generator-core
  [2]: https://npmjs.org/
  [3]: https://github.com/adobe-photoshop/generator-core
  [4]: https://github.com/andyhall/generator-awesome
  [5]: http://julius.sourceforge.jp/
  [6]: http://www.macports.org/
 
