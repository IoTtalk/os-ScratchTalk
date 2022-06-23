# ScratchTalk

## Required Systems
----------------------------------------------------------------------
1. os-IoTtalk
2. os-AutoGen
3. os-EduTalk
## Installation
1. Download
``` command
$ git clone https://github.com/IoTtalk/os-ScratchTalk.git
$ cd os-cratchTalk
$ git submodule init
$ git submodule update --recursive
```

2. Configurations
In `scratch-gui/src/components/library/library.jsx`,line 21 set URL.
```js
const serverName = "<ScratchTalk Address>"
```

In `scratch-gui/config.js` line 1, 2 set URLs.
```js
exports.iottalkCSM = "<IoTtalk Address>";
exports.serverName = "<ScratchTalk Address>";
```

In `scratch-vm/src/extensions/scratch3_iottalk/iottalk/config.js`,line 1, 2 set URLs.
```js
exports.iottalkCSM = "<IoTtalk Address>";
exports.serverName = "<ScratchTalk Address>";
```

In `ScratchTalk-Subsystem/config.js`, set URLs.
```js
exports.serverName = "<ScratchTalk Server Domain Name>";
exports.serverPort = "<ScratchTalk Server Port>";
exports.autogenURL = "<AutoGen Address>/autogen/ccm_api";

exports.authIssuer = "<OAuth server URL>";
exports.authClientID = "<clientID>";
exports.authClientSecret = "<clientSecret>";
exports.authURI = "<OAuth Auth URI>";
exports.authCallbackURI = "<OAuth callback URI>";
exports.authTokenURI = "<URI for exchange token>";
```
In `ScratchTalk-Subsystem/rc/js/main.js`, line 2 set URL.
```js
const csmURL = "https://<iottalk address>";
```

In `ScratchTalk-Subsystem/rc/js/csmapi.js`, line 2 set URL.
```js
var ENDPOINT = "https://<iottalk address>";
```

3. Run Scratch GUI (frontend)
``` command
$ cd ./scratch-vm && npm install && npm link

# Link the scratch-vm to GUI
$ cd ../scratch-gui && npm install && npm link scratch-vm
$ npm start
```

4. Run ScratchTalk-Subsystem (backend)
``` command
$ cd ScratchTalkSubsystem
$ npm install
$ npm start
```

## TLS settings
In `scratch-gui/webpack.config.js`, add `public` in the `devServer` section.
```js
devServer: {
    public: '<scratch GUI domain name>' // That solved it
}
```
