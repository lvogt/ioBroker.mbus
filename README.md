![Logo](admin/mbus.png)
# ioBroker.mbus
======================

[![Greenkeeper badge](https://badges.greenkeeper.io/Apollon77/ioBroker.mbus.svg)](https://greenkeeper.io/)

[![NPM version](http://img.shields.io/npm/v/iobroker.mbus.svg)](https://www.npmjs.com/package/iobroker.mbus)
[![Downloads](https://img.shields.io/npm/dm/iobroker.mbus.svg)](https://www.npmjs.com/package/iobroker.mbus)
[![Code Climate](https://codeclimate.com/github/Apollon77/ioBroker.mbus/badges/gpa.svg)](https://codeclimate.com/github/Apollon77/ioBroker.mbus)

**Tests:** Linux/Mac: [![Travis-CI](http://img.shields.io/travis/Apollon77/ioBroker.mbus/master.svg)](https://travis-ci.org/Apollon77/ioBroker.mbus)
Windows: [![AppVeyor](https://ci.appveyor.com/api/projects/status/github/Apollon77/ioBroker.mbus?branch=master&svg=true)](https://ci.appveyor.com/project/Apollon77/ioBroker-mbus/)

[![NPM](https://nodei.co/npm/iobroker.mbus.png?downloads=true)](https://nodei.co/npm/iobroker.mbus/)

This adapter for ioBroker connects to a M-Bus Master via TCP or serial to provide the status and details of connected M-Bus devices.

## Description of parameters
### Gateway IP / TCP Port
IP address and port of the M-Bus Master/Gateway when using TCP.

### Serial port / baud rate
Serial Port and Baud rate of M-Bus Master/Gateway.

### Update Interval
Interval in Seconds to update the data. Default (if empty) is 3600s (1h). Consider how the devices on the M-Bus bus are powered to prevent draining batteries. If you set the interval to 0 then the device is read only once on adapter start, but then no longer automatically.

### Device IDs
You can use primary (1-250) and secondary (16 characters long) M-Bus IDs

## How to read the Device on request?
In the created states for each device one state exists called "updateNow". When you set this to true (as control action with ack=false) the device is updated immediately. If an interval is configured the interval restarts after the data are received.

## Todo
* encrypted payload handling (if needed by anyone)

## Changelog

### 1.1.1 (2018-12-10)
* (Apollon77) make sure adapter is not communicating too fast at the beginning

### 1.1.0 (2018-05-06)
* (bluefox) Error tolerance
* (apollon77) Fix Admin

### 0.1.8 (2018-04-03)
* (apollon77) fix config dialog

### 0.1.7 (2018-04-02)
* (apollon77) allow to set "0" as update interval that will cause in no automatic updates, so only manually using updateNow is possible.

### 0.1.6 (2018-03-26)
* (apollon77) disconnect/reconnect for each query

### 0.1.5 (2018-03-26)
* (apollon77) update to node-mbus 0.5 with shorter timeouts

### 0.1.4 (2018-03-26)
* (apollon77) add "updateNow" states to all devices to trigger manual update
* (apollon77) update to node-mbus 0.4.1 with shorter timeouts

### 0.1.2
* (apollon77) official released version

### 0.0.1
* (apollon77) initial release for testing

## License

The MIT License (MIT)

Copyright (c) 2018 Apollon77 <ingo@fischer-ka.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
