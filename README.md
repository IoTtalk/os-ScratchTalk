# ScratchTalk

## Installation
1. Download
``` command
$ git clone https://github.com/zihxiangwen/ScratchTalk.git
$ git submodule init
$ git submodule update --recursive
```

2. Run Scratch GUI (frontend)
``` command
$ cd ./scratch-vm && npm install && npm link

# Link the scratch-vm to GUI
$ cd ../scratch-gui && npm install && npm link scratch-vm
$ npm start
```

3. Run ScratchTalk-Subsystem (backend)
``` command
$ cd ScratchTalkSubsystem
$ npm start
```
