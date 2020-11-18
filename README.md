# ScratchTalk

## Installation
1. Download
``` command
$ git clone https://github.com/zihxiangwen/ScratchTalk.git
$ cd ScratchTalk
$ git submodule init
$ git submodule update --recursive
```

2. Configurations
In `scratch-vm/src/extensions/scratch3_iottalk_multiplayer/iottalk/config.js`, set URLs.
```js
exports.iottalkCSM = "<IoTtalk URL>/csm";
exports.ccmapiURL = "<ScratchTalk Subsystem Address>/ccmapi"; //default port 8999
```

In `scratch-vm/src/extensions/scratch3_iottalk/iottalk/config.js`, set URLs.
```js
const iottalkCSM = "<IoTtalk URL>/csm";
const ccmapiURL = "<ScratchTalk Subsystem Address>/ccmapi"; //default port 8999
```

In `scratch-vm/src/extensions/scratch3_iottalk_room/iottalk/config.js`, set URLs.
```js
exports.iottalkCSM = "<IoTtalk URL>/csm";
exports.ccmapiURL = "<ScratchTalk Subsystem Address>/ccmapi"; //default port 8999
```

In `ScratchTalk-Subsystem/config.js`, set URL.
```js
exports.AutogenURL = "<AutoGen Address>/autogen/ccm_api";
```
In `ScratchTalk-Subsystem/rc/js/main.js`, set URL.
```js
const Csm_URL = "<IoTtalk URL>/csm";
```

In `scratch-vm/config.js`, set URL.
```js
exports.iottalkURL = "<iottalk URL>";
exports.serverName = "<scratch domain name>";
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
