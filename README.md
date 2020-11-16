# ScratchTalk

## Installation
1. Download
``` command
$ git clone https://github.com/zihxiangwen/ScratchTalk.git
$ git submodule init
$ git submodule update --recursive
```

2. Configurations
In `scratch-vm/srcextensions/scratch3_iottalk_multiplayer/iottalk/config.js`, set URLs.
```nodejs
exports.iottalkCSM = "<IoTtalk URL>/csm";
exports.iottalkCSM = "<ScratchTalk Subsystem Address>/ccmapi"; #default port 8999
```

In `scratch-vm/srcextensions/scratch3_iottalk/iottalk/config.js`, set URLs.
```nodejs
const iottalkCSM = "<IoTtalk URL>/csm";
const ccmapiURL = "<ScratchTalk Subsystem Address>/ccmapi"; #default port 8999
```

In `scratch-vm/srcextensions/scratch3_iottalk_room/iottalk/config.js`, set URLs.
```nodejs
exports.iottalkCSM = "<IoTtalk URL>/csm";
exports.iottalkCSM = "<ScratchTalk Subsystem Address>/ccmapi"; #default port 8999
```

In `ScratchTalk-Subsystem/config.js`, set URL.
```nodejs
exports.AutogenURL = "<AutoGen Address>/autogen/ccm_api";
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
$ npm start
```
