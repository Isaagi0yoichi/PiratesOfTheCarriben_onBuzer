# PiratesOfTheCaribbean_onBuzzer

An Arduino-based audio-visual project that plays the iconic **"He's a Pirate"** theme from *Pirates of the Caribbean* using a passive piezo buzzer and a synchronized 5-LED sequence.

---

##  Project Overview
This project utilizes the Arduino `tone()` function to generate specific frequencies (notes) defined in a `pitches.h` library. As the melody plays, a 5-LED array cycles through a sequence, providing a visual rhythm that matches the tempo and "swagger" of the music.

### ✨ Key Features
* **Melody Playback:** High-fidelity recreation of the theme song using frequency-to-note mapping.
* **LED Synchronization:** A modular sequence where LEDs pulse in time with each note’s duration.
* **Dynamic Timing:** Automatically calculates note lengths in milliseconds based on standard musical notation (quarter notes, eighth notes, etc.).

---

##  Components Required

| Component | Quantity | Connection (Pin) |
| :--- | :--- | :--- |
| **Arduino Uno/Nano** | 1 | - |
| **Passive Buzzer** | 1 | Digital Pin 9 |
| **LEDs** | 5 | Digital Pins 2, 3, 4, 5, 6 |
| **Resistors** | 5 | 220Ω (for LEDs) |
| **Breadboard & Wires** | 1 | - |

---

##  How to Use

1.  **Library Setup:** Ensure you have the `pitches.h` file in the same directory as your `.ino` sketch. This file is essential as it maps musical notes to their respective frequencies.
2.  **Circuitry:** * Connect the **Buzzer** positive lead to **Pin 9** and GND.
    * Connect the **5 LEDs** to **Pins 2 through 6** using 220Ω resistors.
3.  **Upload:** Open the code in the Arduino IDE and upload it to your board.

---

##  Code Logic

The timing for each note is calculated using a simple ratio to convert musical notation into milliseconds:

$$noteDuration = \frac{1000}{\text{noteDurations}[i]}$$

To ensure the performance sounds professional and the lights look sharp:
* **LED Timing:** A delay factor of `1.3` is applied to ensure the LED remains lit for the duration of the note.
* **Staccato Effect:** A `noTone()` command followed by a brief `50ms` pause is called after every note to prevent frequencies from bleeding together.

---

###  Potential Improvements
* [ ] Add a push button to start/stop the melody.
* [ ] Use a Potentiometer to control the tempo (BPM) in real-time.
* [ ] Expand the LED sequence to create a "Knight Rider" back-and-forth effect.
