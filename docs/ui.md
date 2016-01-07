# User Interface

The UI is simply a frontend for the daemon. It requests data from the daemon and presents it in a way that is useful to humans.

It should give a consistent L&F (Look & Feel) across all operating systems and desktop environments.
The only way to do this consistently is by using some form of HTML5 + browser technology.

An easy way to implement this is with [Electron](http://electron.atom.io/) which Atom is built upon.
This allows the UI to be made in javascript or typescript (using ES6 to a degree).

Unfortunately, Servo isn't nearly ready enough as an engine replacement for blink/webkit and doesn't even work on Windows.
So Electron will do for now.

To simplify writing bridges between nodejs and rust, [neon](https://github.com/rustbridge/neon) should be used.
