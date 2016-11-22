# Vult Platform

![Vult](/images/Vult-Small.png?raw=true "Vult")

## Overview

This document describes the architecture and functionality of the future platform for audio synthesis and music composition based on Vult.

The platform will consists of:
- One or more clients
- One audio synthesis engine

![Overview](/images/overview.png?raw=true "Overview")

The main purpose of the clients is to simplify the description of the audio synthesis tasks. The clients can be, for example:
- A code editor: this will allow writing Vult code and execute it directly.
- A graphical editor: this editor can be used to describe synthesis algorithms by connecting blocks without requiring coding.

The audio engine is in charge of taking Vult code, compile it and execute it. The engine will have different (but compatible) implementations.
- JavaScript/Web based: this implementation of the engine will be able to run entirely in a web browser by using the Web Audio and MIDI APIs.
- C++/LuaJIT based: this implementation is intended for high performance synthesis and will run locally on a computer.

The clients will be able of communicating with any implementation of the audio engine. For example: if the the client is web based it can use the audio engine running in the same browser.

## Ideas for Clients

### Eurorack Graphical Client

The idea behind this client is to provide an emulation of the audio workflow in a modular synthesizer.

![Modular](/images/basicpatch.png?raw=true "Modular")

*image source: www.synthesizers.com*

This approach has been implemented in a few commercial products like: Propellerheads Reason, Reaktor or Softube Modular.

The client will be a platform where `modules` can be connected, created or modified. Based on the connections, the Vult code will be generated and sent to the Audio Engine to be executed.

Note: one cool thing about describing the modules in Vult is that the same code could be exported and programmed into an equivalent hardware module.

### Code Editor

As the name says, this client is intended to write Vult code. This can be something similar to the [Live Demo](http://modlfo.github.io/vult/demo/) in the Vult web page.


