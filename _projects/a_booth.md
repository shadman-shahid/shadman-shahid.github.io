---
layout: page
title: Implementation of 8x8 Booth Encoded Multiplier
short-title:  8x8 Booth Encoded Multiplier
description: ‘8 by 8 Booth encoded multiplier’ using the Cadence Virtuoso platform.
img: assets/img/project/booth.jpg
importance: 5
category: academic
---

A binary multiplier is an electronic circuit that is used in multiplication of two binary numbers in digital electronics such as computer. The traditional way of multiplication consists of multiplying each bit of multiplicand with multiplier and then summing up the partial products together. Booth's multiplication algorithm provides a faster process, reducing the 8 partial products needed for a traditional 8 bit by 8 bit multiplier down to 4. This was the inspiration to design an __8 by 8 Booth encoded multiplier__ using the __Cadence Virtuoso platform__, with a __Ripple-Carry__ adder used to sum the partial products.
{: style="text-align: justify;"}

With this end in view, we had implemented the multiplier from the basic building blocks of digital logic circuits, i.e MOSFETs, designing both the schematic and the layout of the circuit. This project contains the following:
{: style="text-align: justify;"}
1. Schematic design of the Booth encoder, Booth decoder and Ripple-Carry adder
2. Functional verification of each building block against the timing diagram
3. Layout design and layout area minimization
4. Design Rule Check (DRC) and Layout Versus Schematic (LVS) verification

The entire system was implemented using the **_Cadence® Virtuoso® Analog Design Environment_**.
{: style="text-align: justify;"}

Here, the booth multiplier that we have implemented is functionally correct as we can
see from the timing diagram. Also the circuit area has been minimized, as we tried to
make it as compact as possible. We used transmission gates for XOR gate, to minimize
delay . Also, the circuit only has 2 Layers of wires. These two layers also ensured that
there was minimal propagation delay and less errors.
{: style="text-align: justify;"}

<br>
### The Project Report Preview
The project report is provided below:
<iframe src="/assets/pdf/EEE454_booth.pdf" width="100%" height="600px" frameborder="0">
    Your browser does not support PDFs. Please download the PDF to view it: <a href="/assets/pdf/EEE454_booth.pdf">Download PDF</a>.
</iframe>