# node-bebop

Control your Parrot Bebop drone using JavaScript!

This module allows you to control, receive nav data, and receive video data from the [Parrot Bebop](http://www.parrot.com/products/bebop-drone/) WiFi controlled drone.

The implementation attempts to use the same interface as the [node-ar-drone](https://github.com/felixge/node-ar-drone) node module from [@felixge](https://github.com/felixge/), so it can be mostly NodeCopter compatible.

## How to Install

To get started, install the npm module:

    $ npm install node-bebop


## How to Use

This simple example takes off, then lands after 5 seconds:

```javascript
var bebop = require('node-bebop');

var drone = bebop.createClient();

drone.connect(function() {
  drone.takeOff();

  setTimeout(function() {
    drone.land();
  }, 5000);
});

```
### API

### createClient()

Returns a `new Bebop`

### connect(callback)

Connects to the drone and executes the callback when the drone is ready to fly

#### takeOff()

Tell the drone to lift off the ground.

#### land()

Land the drone.

#### stop()

Tell the drone to hove in place.

#### emergency()

Tell the drone to drop like a stone.

#### up(val)

Cause the drone to increase in altitude at 0-100 speed

#### down(val)

Cause the drone to decrease in altitude at 0-100 speed

#### right(val)

Cause the drone to move to the right at 0-100 speed

#### left(val)

Cause the drone to move to the left at 0-100 speed

#### clockwise(val)

Cause the drone to spin in a clockwise direction at 0-100 speed

#### counterClockwise(val)

Cause the drone to spin in a counter clockwise direction at 0-100 speed




### Events

#### video

Emits one h.264 video frame

#### ready

Emitted when the drone has successfully connected


## Release History

0.1.0 Initial release

## License

Copyright (c) 2015 The Hybrid Group. Licensed under the MIT license.
