## node-bluetooth ![NPM version](https://img.shields.io/npm/v/node-bluetooth.svg?style=flat)

Bluetooth serial port communication for Node.js


### Requirements

**This package require `node-gyp` installed .**

#### Linux

You'll need libbluetooth-dev. On Ubuntu/Debian : ``` $ sudo apt-get install libbluetooth-dev```

### Installation

```bash
$ npm install node-bluetooth --save
```




### Example
```js
const bluetooth = require('node-bluetooth');

const device = new bluetooth.DeviceINQ();

device.on('found', function(address, name){

  console.log('Found: ' + address + ' with name ' + name);

  device.findSerialPortChannel(address, function(channel){
    
    console.log('Found RFCOMM channel for serial port on %s: ', name, channel);

  });
  
});

device.on('finished', function(){
  
  console.log('scan finished.');
  
});

device.inquire();

```

### API

- node-bluetooth.Connection()
- node-bluetooth.DeviceINQ()
- node-bluetooth.connect()

### Contributing
- Fork this Repo first
- Clone your Repo
- Install dependencies by `$ npm install`
- Checkout a feature branch
- Feel free to add your features
- Make sure your features are fully tested
- Publish your local branch, Open a pull request
- Enjoy hacking <3

### MIT license
Copyright (c) 2016 lsong

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the &quot;Software&quot;), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED &quot;AS IS&quot;, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

---
