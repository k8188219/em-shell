# Try it out!

Go to https://k8188219.github.io/em-shell/

# Current status
* Runs on Chrome and Firefox
* Some built-in commands work
* Some vfork-exec commands work
* Gets confused when the terminal page has more than 1 tab or window opened on it

# How it works
* busybox compiled by emscripten
  * Doesn't use Emterpreter or Asyncify!
* busybox processes run in web workers
* The web workers communicate with the UI through a service worker
* The web workers use synchronous (blocking) XMLHttpRequest to wait for terminal input

# Build instructions

## Prerequisites

* Linux (tested with Ubuntu 15.04 Server)
* Node (tested with 4.2.1)
* Emscripten (tested with 1.35.2)
  * Create a symlink: emgcc -> emcc

## Procedure
    git clone https://github.com/tbfleming/em-shell.git
    git clone https://github.com/tbfleming/em-busybox.git
    cd em-shell
    either:
        js/build-busybox
        js/build-busybox-dbg
