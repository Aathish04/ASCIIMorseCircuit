# ASCIIMorseCircuit

This repository contains the project files and report for an ASCII letter to Morse Code converter. The converter is built using only basic sequential and combinational logic circuits and was designed as the Mini-Project for the UCS2311 Digital Design Lab course. The system was designed by [Aathish Sivasubrahmanian](https://github.com/Aathish04) and [Alamelu Kannan](https://github.com/alameluk17). 

Below, you can find an abridged transcript of the handwritten project report.

## Aim
To design an ASCII Letter to Morse Code Converter using basic sequential and combinational logic.

## Apparatus Required

| Serial No. |     Component    | Specification | Quantity |
|:----------:|:----------------:|:-------------:|:--------:|
|      1     |     AND Gate     |     IC7408    |          |
|      2     |     NOT Gate     |     IC7404    |          |
|      3     |      Or Gate     |     IC7432    |          |
|      4     |   JK Flip-Flop   |     IC7476    |          |
|      5     |     NAND Gate    |     IC7400    |          |
|      6     | 16-1 Multiplexer |    IC74150    |          |
|      7     | Connecting Wires |       -       |          |
|      8     |  IC Trainer Kit  |       -       |          |

## Theory
Morse code is a system of sending messages that is used to send telegraphic information using signals and rythm. Morse code uses dots and dashes of s specific sequence to represent letters of a message. When messages are sent by sound or radio, dots are signals of a short duration, and dashes are signals of a longer duration.

ASCII is a table of characters for computers used by systems to handle text using the English Alphabet, numbers, or certain special characters. ASCII is abbreviation of "American Standard Code for Information Interchange".

In Morse, every letter is represented as a sequence of dots and dashes, with spaces between any two dots or dashes, and in ASCII, every letter is represented as a sequence of 7 binding digits, of which only 5 denote the actual letter.

The longest letters to represent in morse require 2 dashes and 2 dots. If each dash requires 2 bits, and each dot or space needs one bit, then the longest morse letters need 10 bits to be represented in a sequential format.

Thus, a converter from ASCII to Morse code would take 5 bits as input, and give 10 bits as output.

These 10 bits may be directed to a multiplexer, and the selector bits of a multiplexer may be driven by a MOD-10 [BCD] counter. This will result in the output of the multiplexer transmitting the morse code equivalent of the character at the Input.

## Specifications

1) Draw the turth table for the ASCII (5 bit) to Morse (10 bit) conversion

    1.1. For each of the output variables, draw the K-Map and solve for the boolean expression.
    
    1.2 Implement the boolean expressions for each of the output variables.

2) Connect the 10 output bits of the combinational logic circuit to the 10 Least significant bit inputs of the 16-1 multiplexer.

3) Construct a MOD10 (BCD) counter using the JK-flipflops
    
    3.1) Ensure that the counter may also be reset when the START input of the system is held low.
    3.2 The 4 output bits of this counter must be connected to the selector lines of the 16-1 MUX.

4) Ensure that signals are inverted when input to active-low inputs and verify that the morse code of a letter is correctly output when the input is set accordingly, and the START input is held high.

## Uses for Circuit in Real World Applications

- In Robust military communication systems as a failsafe when other less tedious forms of communication fail.
- As a teaching aid to help students understand morse code.
- As a teaching aid to help students understand ASCII.
- In emergency communication systems.

## Input and Output

### Inputs:
- A: 5th LSB of Ascii Character (Letter in English)
- B: 4th LSB of Ascii Character (Letter in English)
- C: 5rd LSB of Ascii Character (Letter in English)
- D: 2nd LSB of Ascii Character (Letter in English)
- E: LSB of Ascii Character (Letter in English)
- START: Signal to indicate when the circuit should start outputting morse in time with input clock signal.

### Output:
- M : Goes high for 2 clock pulses to indicate a dash '-' and goes high for 1 clock pulse to indicate a dot '.'. Is low for 1 clock pulse to denote space between any two dots or dashes. Is low when START input is low.


## Truth Table

| letter | A | B | C | D | E |   | a | b | c | d | e | f | g | h | i | j |
|--------|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| INV    | 0 | 0 | 0 | 0 | 0 |   | x | x | x | x | x | x | x | x | x | x |
| a      | 0 | 0 | 0 | 0 | 1 |   | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| b      | 0 | 0 | 0 | 1 | 0 |   | 1 | 1 | 0 | 1 | 0 | 1 | 0 | 1 | 0 | 0 |
| c      | 0 | 0 | 0 | 1 | 1 |   | 1 | 1 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 0 |
| d      | 0 | 0 | 1 | 0 | 0 |   | 1 | 1 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 |
| e      | 0 | 0 | 1 | 0 | 1 |   | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| f      | 0 | 0 | 1 | 1 | 0 |   | 1 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 0 | 0 |
| g      | 0 | 0 | 1 | 1 | 1 |   | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 0 | 0 | 0 |
| h      | 0 | 1 | 0 | 0 | 0 |   | 1 | 0 | 1 | 0 | 1 | 0 | 1 | 0 | 0 | 0 |
| i      | 0 | 1 | 0 | 0 | 1 |   | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| j      | 0 | 1 | 0 | 1 | 0 |   | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 1 |
| k      | 0 | 1 | 0 | 1 | 1 |   | 1 | 1 | 0 | 1 | 0 | 1 | 1 | 0 | 0 | 0 |
| l      | 0 | 1 | 1 | 0 | 0 |   | 1 | 0 | 1 | 1 | 0 | 1 | 0 | 1 | 0 | 0 |
| m      | 0 | 1 | 1 | 0 | 1 |   | 1 | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 |
| n      | 0 | 1 | 1 | 1 | 0 |   | 1 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| o      | 0 | 1 | 1 | 1 | 1 |   | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 0 |
| p      | 1 | 0 | 0 | 0 | 0 |   | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 0 |
| q      | 1 | 0 | 0 | 0 | 1 |   | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 0 | 1 | 1 |
| r      | 1 | 0 | 0 | 1 | 0 |   | 1 | 0 | 1 | 1 | 0 | 1 | 0 | 0 | 0 | 0 |
| s      | 1 | 0 | 0 | 1 | 1 |   | 1 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| t      | 1 | 0 | 1 | 0 | 0 |   | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| u      | 1 | 0 | 1 | 0 | 1 |   | 1 | 0 | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
| v      | 1 | 0 | 1 | 1 | 0 |   | 1 | 0 | 1 | 0 | 1 | 0 | 1 | 1 | 0 | 0 |
| w      | 1 | 0 | 1 | 1 | 1 |   | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 0 | 0 |
| x      | 1 | 1 | 0 | 0 | 0 |   | 1 | 1 | 0 | 1 | 0 | 1 | 0 | 1 | 1 | 0 |
| y      | 1 | 1 | 0 | 0 | 1 |   | 1 | 1 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 |
| z      | 1 | 1 | 0 | 1 | 0 |   | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 0 | 1 | 0 |
| INV    | 1 | 1 | 0 | 1 | 1 |   | x | x | x | x | x | x | x | x | x | x |
| INV    | 1 | 1 | 1 | X | X |   | x | x | x | x | x | x | x | x | x | x |

## K-Maps and Output Equations

For the sake of brevity, the KMaps are not included here, but you can find the 20 KMaps in [the project report](DPSDMiniProjectReportFinal.pdf), and in the [./OutputKMaps/images/jpg](./OutputKMaps/images/jpg) folder.

> The KMap solutions were verified with the help of the online solver at [32x8.com](http://32x8.com/index.html).
To automate the process, [a Python script](./KMapSolving.ipynb) was written to query the website for the KMaps given the truth table.

## Circuit Diagrams
For the sake of brevity, the Circuit Diagrams are not included here, but you can find them in the project report.

> The combinational logic circuit that facilitates the ASCII-Morse conversion was drawn with the help of [Logisim-evolution](https://github.com/logisim-evolution/logisim-evolution). The corresponding project file is [MorseCodeEncoder.circ](MorseCodeEncoder.circ) .
