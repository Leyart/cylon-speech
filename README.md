# Cylon.js For Speech

Cylon.js (http://cylonjs.com) is a JavaScript framework for robotics and physical computing using Node.js.

This repository contains the Cylon adaptor for text to speech capabilities.

For more information about Cylon, check out the repo at https://github.com/hybridgroup/cylon

[![Build Status](https://secure.travis-ci.org/hybridgroup/cylon-speech.png?branch=master)](http://travis-ci.org/hybridgroup/cylon-speech) [![Code Climate](https://codeclimate.com/github/hybridgroup/cylon-speech/badges/gpa.svg)](https://codeclimate.com/github/hybridgroup/cylon-speech) [![Test Coverage](https://codeclimate.com/github/hybridgroup/cylon-speech/badges/coverage.svg)](https://codeclimate.com/github/hybridgroup/cylon-speech)

## How to Install

Install the module via NPM:

    $ npm install cylon-speech

After the module is installed, but before you run any scripts using it, ensure the `espeak` utility is installed on your computer.

There are packages available for Linux, OS X, and Windows.

### Linux

On most Linux distros, there should already be a package you can install.
If you use Aptitude Package Manager (apt-get), just install it with:

    $ sudo apt-get install espeak

This is also true for Single-Board Linux Computers like the Raspberry-Pi and the Beaglebone Black.

Once the package has finished installing, try this command to verify everything is working as expected:

    $ espeak "This is awesome, Linux speaking"

If you hear your computer talking to you, everything is working as expected.
If not, please refer to the [espeak docs](http://espeak.sourceforge.net/commands.html) for more help.

### OS X

Install espeak through Homebrew.

    $ brew install espeak

After installing, test it out:

    $ espeak "This is awesome, OS X speaking"

### On Windows

For Windows systems there is a `.exe` file you can download from [SourceForge](http://espeak.sourceforge.net/download.html).

Same as with the above operating systems, make sure it works as advertized when the instalation has completed.

    $ espeak "This is awesome, Windows OS speaking!"

## How to Use

```javascript
var Cylon = require('cylon');

Cylon.robot({
  // voice for espeak can be specified either in one string or as params for the adaptor.
  // both connections below will reproduce with the same voice.
  // connections: { speech: { adaptor: 'speech', language: 'en, gender: 'f', 'voice: '3' } },
  connections: {
    speech: { adaptor: 'speech', voice: 'en-f3', speed: 130 }
  },

  devices: {
    mouth: { driver: 'speech' }
  },

  work: function(my) {
    my.mouth.say("This is awesome!");
    my.mouth.say("I'm a Cylon.JS robot, and I'm talking!");
  }
}).start();
```

## Documentation

We're busy adding documentation to our web site at http://cylonjs.com/ please check there as we continue to work on Cylon.js

Thank you!

## Contributing

* All patches must be provided under the Apache 2.0 License
* Please use the -s option in git to "sign off" that the commit is your work and you are providing it under the Apache 2.0 License
* Submit a Github Pull Request to the appropriate branch and ideally discuss the changes with us in IRC.
* We will look at the patch, test it out, and give you feedback.
* Avoid doing minor whitespace changes, renamings, etc. along with merged content. These will be done by the maintainers from time to time but they can complicate merges and should be done seperately.
* Take care to maintain the existing coding style.
* Add unit tests for any new or changed functionality & Lint and test your code using [Grunt](http://gruntjs.com/).
* All pull requests should be "fast forward"
  * If there are commits after yours use “git rebase -i <new_head_branch>”
  * If you have local changes you may need to use “git stash”
  * For git help see [progit](http://git-scm.com/book) which is an awesome (and free) book on git

## Release History

Version 0.6.0 - Compatibility with Cylon 0.22.0

Version 0.5.0 - Compatibility with Cylon 0.21.0

Version 0.4.0 - Compatibility with Cylon 0.20.0

Version 0.3.0 - Compatibility with Cylon 0.19.0

Version 0.2.0 - Updates, compatibility with Cylon 0.18.0

Version 0.1.1 - Updated README, adaptor now creates one process per text to speech message.

Version 0.1.0 - Initial release, cylon speech now working

## License

Copyright (c) 2014 The Hybrid Group. Licensed under the Apache 2.0 license.

