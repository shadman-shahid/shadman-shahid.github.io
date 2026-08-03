---
layout: page
title: Aircraft Autopilot System Prototype
short-title: Aircraft Autopilot System Prototype
description: Control and balance a toy aircraft’s movement with arduino controller. 
img: assets/img/project/airplane.jpg
importance: 7
category: academic
---

An autopilot is a mechanical, electrical, or hydraulic system that guides an aerial vehicle without a pilot's assistance, maintaining orientation by monitoring flight data from inertial sensors and issuing corrective actions in response. In this project, we designed, implemented and tested an autopilot prototype on a glider-type RC aircraft. A 3-axis accelerometer and three single-axis gyroscopes provide the acceleration and angular-rate data, which are fused through a Kalman filter to estimate the roll, pitch and yaw angles on an ATMEGA32 microcontroller. The estimated orientation is passed to a fuzzy logic controller, which decides the corrective action, and a set of servo motors carries out the required correction to bring the flight path back to the desired orientation. Our main target was to maintain straight-line flight under air disturbances, and we also demonstrated controlled turning during circular flight.
{: style="text-align: justify;"}

We modeled the pitch dynamics from the aircraft's transfer function and designed a PID controller to meet a set of design requirements: overshoot under 10%, rise time under 2 seconds, settling time under 3 seconds and steady-state error under 2%. The open-loop response turned out to be unstable, with a pole on the imaginary axis; adding feedback stabilized the system and drove the steady-state error to zero, though the resulting overshoot of 17.4% exceeded our design target. The aircraft itself was built around a 2450 KV brushless DC motor driven by a 30 A electronic speed controller with a 16 V/25 A battery eliminator circuit. We carried out ten test flights between 5 and 12 February, with durations ranging from 8 to 22 seconds.
{: style="text-align: justify;"}


<br>
<iframe src="/assets/pdf/EEE318_aircraft_autopilot.pdf" width="100%" height="600px" frameborder="0">
    Your browser does not support PDFs. Please download the PDF to view it: <a href="/assets/pdf/EEE318_aircraft_autopilot.pdf">Download PDF</a>.
</iframe>
