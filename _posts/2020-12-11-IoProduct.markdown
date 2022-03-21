---
layout: post
title: "IoProduct: IoT Product Dispenser"
author: "Tino Trangia"
tags: projects
excerpt_separator: <!--more-->
---

I made a simple, proof-of-concept project to build a product dispenser that was connected to the "Internet of Things". Intended to serve as a hypothetical solution for automated inventory and user count tracking for free menstrual product dispensers at UC Berkeley.<!--more--> Check out the video below to learn more:

<br>

<div style="position: relative; padding-bottom: 56.25%; padding-top: 0; height: 0;">
    <iframe style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
    src="https://www.youtube.com/embed/Xlw_nAnmnzQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
    </iframe>
</div>

<br>

## Context

Spring 2020. My fellow Engineering Student Council members and I had been overseeing a menstrual product distribution program (also known as the Free Menstrual Product Initiative) for several months. We had distributed over 3000 pads and tampons from 7 different sites throughout Berkeley's engineering campus. Then, the pandemic hit, and the project was put on pause.

That fall, I took an Internet of Things Course (ME100) that required a final project. Since I wasn't able to expand the Free Menstrual Product Initiative while the world was locked down, I decided to work on something closely related &mdash; an automated menstrual product dispenser that would signal when restocking was needed, rather than waiting for volunteers to do their daily runs.

## Design

The course provided me with several tools that I integrated into my project design. Most important was an ESP32 Microcontroller, which ran a Python script dictating all of the logic behind the dispenser. Also crucial was an ultrasonic sensor, which used ultrasonic waves to measure the height of the product stack. As products were removed, this height would change, allowing the dispenser to estimate how much was remaining. It then published this information to an MQTT broker, allowing communication with users through Zapier. The chart below outlines the design in greater detail:

<br>

![Design Summary](../_images/ioproduct.png)