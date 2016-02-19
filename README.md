# Winble

Noble bindings for the Universal Windows Platform

This module is **EXPERIMENTAL**.

[Noble](https://github.com/sandeepmistry/noble) is a project that enables 
programming Bluetooth 4 (aka Low Energy) devices using Node.js. 
Unfortunatly, the support Windows is quite poor. Winble is an attempt to
make Noble capable of leveraging the native Universal Windows Platform 
Bluetooth stack. This makes compatible with any Windows 10 devices, from
PCs to phones and Windows IoT devices.

In order to access the UWP APIs, Winble *must* be run using Node.js 
Chakra, which the fork of Node.js where V8 is replaced by ChakraCore,
the JavaScript engine from the Edge browser.

## How to use

As of yet, Noble is not extensible without modifiying its source code.
Noble selects which bindings to use base on the environment. See 
[here](https://github.com/sandeepmistry/noble/blob/master/lib/noble.js#L16).
After installing Noble, replace this section of code by 
`bindings = require("winble")`. You can then use Noble as intended.

I'm planning on submitting a PR to add Windle to the list of supported
bindings. Winble could be activated when the OS is Windows and the JS engine is
ChakraCore.

## Limitations

Winble implements only a small part of the Noble API, but it should be enough
to play around with Bluetooth devices. I've used it to program a Sphero BB-8.
You can connect to the device, then list services and characteristics, and read
and write to and from characteristics.