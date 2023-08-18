---
layout: page
title: Hamming error correcting code generator and receiver
short-title: Hamming error correction in VLSI
description: A simple error correcting scheme, based upon the least Hamming distance principle
img: assets/img/project/hamming.jpg
importance: 3
category: academic
---

Error correcting codes are essential for an error-free data communication system. In this regard, forward error correcting codes (FEC) are
better for a system, as the receiver system is prepared to handle errors. Moreover,
FECs prevent the redundancy of transmitting erroneous data back to the transmitters
end for correction. This was the inspiration to create a __simple error correcting scheme__ based upon the __least Hamming distance principle__

With this end in view, I had implemented a proof of concept system that can correct a single bit error per six transmitted
bits. The parameters of the coding scheme are hard coded to keep the system simple and
minimal enough to display the basic working principle. However those system parameters
can be easily incorporated as system inputs. This project contains the following:
1. Behavioral description of the system in verilog
2. RTL synthesis step
3. Physical design step and validation 
4. Design Rule Check and Layout Versus Schematic

The entire system was implemented using **_Verilog_** by software packages of __Cadence Design Systems__.

<div style="text-align: center;">
    <img src='/assets/img/project/hamming_inside.png' alt="Hamming ECC" style="width: 80%;" />
</div>
<br>
### The Project Report Preview
The project report is provided below:
<iframe src="/assets/pdf/EEE458_hamming.pdf" width="100%" height="600px" frameborder="0">
    Your browser does not support PDFs. Please download the PDF to view it: <a href="/assets/my_pdf_file.pdf">Download PDF</a>.
</iframe>
<!-- ![Hamming ECC](/assets/img/project/hamming_inside.png) -->
