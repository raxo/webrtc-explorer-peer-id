webrtc-explorer-peer-id
======

> Peer Id generator and operator, designed with circular Id namespaces in mind, used in [`webrtc-explorer`](https://github.com/diasdavid/webrtc-explorer). Currently only supports 48 bits, but I'm happy to make accept PR that make it Id size agnostic.

## Project Information

> [David Dias MSc in Peer-to-Peer Networks by Technical University of Lisbon](https://github.com/diasdavid/browserCloudjs#research-and-development)

[![](https://img.shields.io/badge/INESC-GSD-brightgreen.svg?style=flat-square)](http://www.gsd.inesc-id.pt/) [![](https://img.shields.io/badge/TÉCNICO-LISBOA-blue.svg?style=flat-square)](http://tecnico.ulisboa.pt/) [![](https://img.shields.io/badge/project-browserCloudjs-blue.svg?style=flat-square)](https://github.com/diasdavid/browserCloudjs)

This work was developed by David Dias with supervision by Luís Veiga, all in INESC-ID Lisboa (Distributed Systems Group), Instituto Superior Técnico, Universidade de Lisboa, with the support of Fundação para a Ciência e Tecnologia. 

More info on the team's work at: 
- http://daviddias.me
- http://www.gsd.inesc-id.pt/~lveiga

If you use this project, please acknowledge it in your work by referencing the following document:

David Dias and Luís Veiga. browserCloud.js A federated community cloud served by a P2P overlay network on top of the web platform. INESC-ID Tec. Rep. 14/2015, Apr. 2015

# Badgers

[![NPM](https://nodei.co/npm/webrtc-explorer-peer-id.png?downloads=true&stars=true)](https://nodei.co/npm/webrtc-explorer-peer-id/)
[![Dependency Status](https://david-dm.org/diasdavid/webrtc-explorer-peer-id.svg)](https://david-dm.org/diasdavid/webrtc-explorer-peer-id)
[![Build Status](https://travis-ci.org/diasdavid/webrtc-explorer-peer-id.svg)](https://travis-ci.org/diasdavid/webrtc-explorer-peer-id)

# Properties

- Uses sha1 to guarantee that ID's are generated with an uniform distribution 
- Runs in Node.js and in the browser
- Respects the natural circular ID namespace DHT are known to use (meaning that there is no ID higher than 48 bits)

# How to use

```JavaScript
var Id = require('dht-id);

var idA = new Id(); // generates a new random Id with 48 bits length

var idB = new Id(<value to generate the Id from>); // generates an Id based on the value, same value always generates same Id

idA.toHex(); // returns the hex value of the Id in a string

idA.toDec(); // returns the dec value of the Id in a number

idA.next(); // basically this id + 1, useful to send to Sucessor

Id.hash(content); // convinient way to find the Id of a content and guarantee that it has our ideal id length
```
