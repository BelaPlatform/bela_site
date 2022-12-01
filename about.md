---
layout: about
section_id: about
hero-image: hero-1.jpg
title: All about Bela
---

# What is Bela?

Bela is an embedded computing platform for creating beautifully responsive interactive projects. Bela provides ultra-low latency, high quality audio, analog and digital I/O in a tiny self-contained package that can be easily embedded into a huge range of applications. Built on the [BeagleBone](https://beagleboard.org/) family of open-source embedded computers, Bela combines the processing power of an embedded computer with the timing precision and connectivity of a microcontroller.

Bela features an on-board IDE that launches right in the browser, making it easy to get up and running without requiring any additional software. Along with dozens of pre-loaded examples, the Bela IDE is also loaded with great tools digital makers need, like an interactive pin diagram and an in-browser oscilloscope. Creating digital interaction has never been so easy to start or so accessible to learners.

<span class="list-header">Bela is fast.</span> Bela's dedicated hardware and software environment provides hard real-time performance with 1ms latency while retaining the capabilities and power of a 1GHz embedded computer running Linux.

<span class="list-header">Bela is connected.</span> Use Bela's stereo audio input and output to create musical instruments and audio effects. Connect to the physical world with Bela Original's 8 analog inputs and outputs (or Bela Mini's 8 analog inputs), as well as 16 digital I/O pins. You can also use ethernet, USB (including MIDI) and SD card storage.

<span class="list-header">Bela is small.</span> Bela's compact form factor means that it easily integrates into portable interactive objects, and the condensed Bela Mini means that it fits in more places than ever before. Connect to your computer to program Bela, and then power from an external battery to run in standalone mode - no laptop required.

<span class="list-header">Bela makes it easy to get started.</span> No complicated setup or complex toolchains. Just connect Bela to your computer, launch the on-board IDE in a web browser, and start coding right away.

<span class="list-header">Bela has a powerful IDE.</span>The Bela IDE has great features interactive creators need, like a huge collection of example projects in a variety of languages and an in-browser oscilloscope for visualising and examining your signals. Recently we added a GUI integration, so you can create graphical interfaces for Bela using the coding language <a href='https://p5js.org' target='_blank'>p5</a>. This means you can generate data for Bela with on-screen buttons and sliders, or use data from Bela to drive on-screen graphics.

# Why latency matters

{% include latency-graph.html %}

# The Hardware

Bela comes in two versions. Bela has 8 channels of 16-bit analog I/O, 16 digital I/O, stereo audio I/O, and 2 built-in speaker amplifiers. We have also developed the tiny Bela Mini, taking the most popular features of Bela and condensing them into a form factor 1/3 the size. Bela Mini features 8 16-bit analog inputs and 16 digital I/O, as well as 2 channels of audio input and output.

{% include photocaption.html src='bela_comparison.png' %}

# The Software

Bela runs a custom audio processing environment based on the Xenomai real-time Linux extensions. Your code runs in hard real-time, bypassing the entire operating system to go straight to the hardware. We have written a custom audio driver using the Programmable Realtime Unit (PRU), a microcontroller on the same chip as the CPU. This driver is capable of buffer sizes as small as 2 audio samples for very low latency, and its performance is not affected by other system load. No other embedded Linux platform can match this performance. (Read more in [this publication](http://eecs.qmul.ac.uk/~andrewm/mcpherson_aes2015.pdf), which describes the technical aspects of Bela in detail.)

{% include photocaption.html src='bela_software.png' %}

For development, Bela lets you code the way that suits you best, and gives you the tools you need to do it. Plug in your Bela and launch our in-browser IDE, where you can write code in C++, SuperCollider, Csound, upload PureData patches. The IDE also includes an extensive library of example projects, illustrating synthesis, sensor handling, and a range of other techniques in a variety of languages. There is also an in-browser oscilloscope which lets you visualise multiple channels of data simultaneously, without disconnecting the board - an essential tool for sensor debugging - as well as code libraries and GUI integration.

# Who makes Bela?

Bela was born in the [Augmented Instruments Laboratory](http://instrumentslab.org/), in the [Centre for Digital Music](http://c4dm.eecs.qmul.ac.uk/) at [Queen Mary University of London](https://www.qmul.ac.uk/). Bela is now developed and produced by Augmented Instruments Ltd in London, UK. Learn more about Bela's origins on the [Our Story](our-story) page.

# Making products with Bela

All the Bela hardware and software is released under open source licenses. This means you can use Bela to create your own products so long as you respect the terms of our open source license. Bela’s name and logo are trademarked, and are reserved for commercial products that are produced by or licensed by Bela and Augmented Instruments Ltd. To learn more about the licenses we use go to our [open source licenses page](https://learn.bela.io/products/products-overview/open-source-licenses/).

The Bela team is always eager to talk to people wanting to integrate Bela into commercial products, and we're available for consultancy to integrate Bela into applications for commercial deployment. Check out our [consultancy page](consultancy) for more information and please <a href="mailto:info@bela.io">drop us an email</a> with details of your plan, and we'd be happy to discuss it.
