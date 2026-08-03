---
layout: page
title: Implementing Tetris Game using Verilog
short-title: Tetris in Verilog
description: Simplified version of the Tetris game implemented using an FPGA board.
img: assets/img/project/tetris_d.jpg
# redirect: https://unsplash.com
importance: 6
category: academic
---

<!-- <div style="text-align: justify;"> -->
Tetris consists of a playing field into which tetrominoes - four-block geometric pieces - fall one at a time, and the player moves and rotates each piece to form complete horizontal lines. In this project, we implemented a simplified version of the game on an EPF10K70 FPGA (a FLEX 10K device), coded in Verilog HDL using Quartus II. Since a game cell only needs two logic states, the entire playing field and falling piece were represented as binary data: the 8x8 board was stored as a 64-bit output array, and each of the seven tetromino shapes as a 16-bit sequence, with 2D `(x, y)` positions mapped to a 1D bit index via `i = y*width + x`. A slow ~1 Hz clock, derived from the board's 25.175 MHz internal clock, drove the fall rate, while a nested loop imprinted the falling piece into the output array on every pulse and advanced its row position.
{: style="text-align: justify;"}
<!-- </div> -->
<br>
<!-- <div style="text-align: justify;"> -->
Collision was handled with two flags: `LastRowFlag`, set when a piece's bit pattern reaches the bottom row, and `DoesNOTFit`, set when the falling piece would overlap a block already on the field; either flag stacked the piece and spawned a new one at the top, chosen by a pseudo-random 1-degree polynomial generator (higher-order polynomials weren't feasible given the FPGA's logic budget). Completed lines were detected by checking each row's 8-bit flag for all-ones and, if found, clearing that row and shifting the rows above it down. Since a commercial 8x8 LED matrix only exposed 16 connection pins - not enough to address all 64 LEDs independently - we built a custom matrix by soldering 64 LEDs onto a veroboard with a common cathode, driven directly by 64 FPGA pins on active-high logic. We had to drop the scoring feature entirely, as the rest of the game already used 97% of the device's logic elements.
{: style="text-align: justify;"}
<!-- </div> -->
<br>
<iframe src="/assets/pdf/EEE304_tetris.pdf" width="100%" height="600px" frameborder="0">
    Your browser does not support PDFs. Please download the PDF to view it: <a href="/assets/pdf/EEE304_tetris.pdf">Download PDF</a>.
</iframe>
