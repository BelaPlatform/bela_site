---
layout: default
hero-image: index.jpg
title: Google Summer of Code
permalink: /gsoc
---

This page collects ideas for projects for students participanting in the Google Summer of Code.

## Live patching with Pure Data on embedded devices

Pure Data (Pd) is a visual data-flow language for audio applications and it is one of the several languages supported by Bela. Pd ships as a cross-platform software with a C backend and a Tcl/Tk GUI (replaced by HTML5 in the PurrData project). When running Pd on Bela, the user can leverage the analog and digital I/Os of the board to integrate audio processing with the physical connectivity capabilities of the board. Bela provides access to a browser-based IDE for programming the board but, since a desktop environment is not available, the current workflow for using Pure Data on Bela consists in editing the patch on the host computer and then copying it over to Bela where it gets executed.

One of the limitations of this two-step workflow is that the immediateness of the live-patching behaviour of Pd is lost. In this project, the student will leverage the fact that Pd communicates with its GUI via a socket to run the GUI on the host computer while running the audio backend on Bela. This requires a number of adaptations to Pd, including:

- managing the GUI startup process to allow GUI and audio backend to be started separately and connect to each otherA
- allowing access to paths on the remote device
- loading patches through the GUI instead of from the backend
- delegating some of the functionalities currently handled in the backend to the GUI

Knowledge of C is required as part of the work will take place in the audio backend, however there will be need to operate on the GUI side as well.
A good starting point for the project would be last year's [GSoC project](https://summerofcode.withgoogle.com/archive/2020/projects/4882628517298176/) which managed to run PurrData entirely in the browser.
At the end of a successful project we should be able to submit a pull request in the upstream Pure Data or Purr Data repositories. The benefits of this contribution will not be exclusive to Bela, but can benefit the Pd community at large, making it easier to use Pure Data on embedded devices.

## Bela browser-based workbench

Bela features a browser-based oscilloscope for visualising audio and sensor signals. This project would extend the oscilloscope into a more full-featured laboratory workbench. The oscilloscope itself could be extended in several ways, for example:
- More options for scaling the plot in each axis
- Adjustable cursors for reading off measurements in time or amplitude
- Automatic detection of amplitude or frequency from the plot
- More options for triggering
- XY mode
- Updated visual appearance
- On top of that, other workbench tools could be added, including:
- Waveform generator
- Multimeter (RMS amplitude, frequency, DC offset, etc.)
- Browser-based simulation of common analog and digital inputs (buttons, potentiometers etc.) and outputs (e.g. LEDs)
This project would be built primarily in JavaScript, with some secondary work in C++ to connect to the Bela core code. We are open to the inclusion of existing open-source libraries to build any of these components.

## Browser-based IDE

Bela's browser-based IDE is served by a node.js server running home-grown modules and a HTML5 frontend based around jquery, ace.js and scss. The codebase started out in 2015 for internal development purposes, it has since been made public and has gone through two major redesigns during its 6-year lifetime. It allows the user to browse projects and examples, edit files and build and run projects. Over time, the frontend/backend relationship has evolved to support a number of Bela-specific features.The software landscape has changed radically since 2015 and there are now several great web-based IDEs out there. The scope of this project is to evaluate how a Bela-like workflow and appearance could be implemented on top of a more modern and better supported browser-based IDE, such as Cloud9. You will start by verifying that the requirements for frontend-backend communication logic can be met on the new platform. Then you will write a proof of concept skin for the new platform that mimics, where possible, the existing Bela one. You will need knowledge of web technologies, both for frontend and backend.

## Universal Trill support

The Trill sensors are a family of capacitive sensing devices which connect to a host device via I2C. While I2C is widespread on embedded computers and microcontroller boards, it is not exposed on most desktop and laptop computers. In order to use Trill with your computer you normally need an I2C-USB adapter or a microcontroller board (e.g.: Arduino) which normally relay the information to a host computer via Serial. This project will simplify using Trill sensors on a non-embedded device by allowing to seamlessly interact with the sensors using a serial device as a proxy. In the process, you will expand the Trill library to handle the serial proxy. Additionally, you will update the interface to communicate with Trill from PureData, Supercollider and Csound, which is currently exclusive to Bela, to be accesible from these languages on any systems.

## Improving support for other programming languages on Bela

Bela officially supports C++, Pure Data, SuperCollider, Csound. However, there are a number of other programming languages that have been shown to work with Bela over the years, including (at least) gen~ (a subset of Max/MSP), Pyo, FAUST, SOUL, JUCE and Rust. However, most of these have been left mostly dormant because of other priorities in the core development team of Bela. The scope of this project is, for each (or some) of these languages, to:

- outline the prerequisites to be installed on the Bela image
- improve the workflow for using the language on Bela, where appropriate with integration with the Bela IDE
- write relevant examples to cover the basics of Bela-specific I/O as well as providing some interesting audio examples to run on Bela.
- document the new workflow on the Bela [knowledge base](https://learn.bela.io/using-bela/languages/bela-language-support/)
- where possible, automate GUI generation for parameter control or visualisation

You will need a working knowledge of the programming languages you will work with, as well as C++ skills to work on the integration with the Bela core code. If IDE and GUI integration will be performed, knowledge of node.js and web development will be useful.
The successful completion of the project will have one of these programming languages officially supported by Bela with an ease of workflow comparable to our primary supported languages.

## Bela audio driver for cross-platform audio backends

When adding support for Supercollider and Csound, we had to add a new audio driver to these pieces of software to call into Bela's C API. In order to make the process of adding Bela support to more programming languages in the future easier, we could think of simply adding Bela support to some common audio backend libraries, so that a single effort can be reused across several pieces of software that use that same library. Examples of such libraries are: portaudio, rtaudio and jack and there may be more. In this project you'll write a Bela driver for one or more of these libraries and build at least one application that uses the library (e.g.: ChucK, which uses RtAudio or Pure Data, which uses portaudio).
You will need a good knowledge of C and build systems.
Upon successful completion, the project will make it easier to add more applications and programming languages to Bela.

## Building Bela images

The image that Bela ships with is built from [this repo](https://github.com/BelaPlatform/bela-image-builder/), which was initially inspired by the upstream [image-bulder](https://github.com/beagleboard/image-builder) repo, but it has greatly diverged from it. The purpose of this project is to "rebase" the functionalities of the bela-image-builder repo on top of the image-builder one. This is not simply a matter of git rebase, as the two codebases are drastically different. It is more of a "semantic rebase": understand the motivations behind the features of the bela-image-builder repo (minimal clutter, custom kernel, custom software, custom systemd configuration) and add those to the image-builder repo in a way that makes it easier to maintain. Wherever possible, the Bela-specific changes should be made conditional so that a pull request can be opened upstream to minimise future development effort.
You will need experience with scripting (mostly bash), build systems and Linux management.
Upon successful completion of the project, the Bela image will follow more closely the upstream development and as a consequence it will be updated more often and more easily.

