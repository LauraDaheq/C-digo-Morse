# Morse Code Converter 📡

A text-to-Morse code converter using an Arduino Uno and the built-in LED on pin 13.

## Project Description

This project converts text messages into Morse code and transmits them visually using LED flashes. Users can send characters through the Serial Monitor, and the LED will blink according to the corresponding Morse code pattern.

## Components Used

- **Arduino Uno** – Main microcontroller
- **LED** – Visual indicator (Built-in LED on Pin 13)
- **1 kΩ Resistor** – LED protection (optional when using the built-in LED)
- **USB Serial Connection** – Used to send messages from a computer
- **Breadboard** – For circuit connections

## Features

- ✅ Converts letters (A–Z) to Morse code
- ✅ Converts numbers (0–9) to Morse code
- ✅ Supports both uppercase and lowercase characters
- ✅ Automatically handles spaces between words
- ✅ Serial communication at **9600 baud**
- ✅ Uses the built-in LED on pin 13

## Pin Configuration

| Component | Arduino Pin |
|----------|------------|
| LED | 13 (Built-in LED) |
| USB Serial | RX/TX |

## Implemented Morse Code

### Letters (A–Z)

```text
A .-     N -.
B -...   O ---
C -.-.   P .--.
D -..    Q --.-
E .      R .-.
F ..-.   S ...
G --.    T -
H ....   U ..-
I ..     V ...-
J .---   W .--
K -.-    X -..-
L .-..   Y -.--
M --     Z --..
```

### Numbers (0–9)

```text
0 -----  5 .....
1 .----  6 -....
2 ..---  7 --...
3 ...--  8 ---..
4 ....-  9 ----.
```

## How It Works

1. Upload the `MORSE.ino` sketch to your Arduino Uno.
2. Open the **Serial Monitor**.
3. Set the baud rate to **9600**.
4. Type a message containing letters, numbers, and spaces.
5. The built-in LED will blink according to Morse code timing:

- **Dot (.)** → Short flash (200 ms)
- **Dash (-)** → Long flash (600 ms)
- **Space between symbols** → 200 ms
- **Space between letters** → 600 ms
- **Space between words** → 800 ms

## Timing Table

| Element | Duration |
|---------|---------:|
| Dot (.) | 200 ms |
| Dash (-) | 600 ms (3 × dot) |
| Space between symbols | 200 ms |
| Space between letters | 600 ms |
| Space between words | 800 ms |

## Example

```text
Input:
SOS

LED Output:
...   ---   ...

(S)   (O)   (S)
```

## Notes

- A **200 ms dot delay** corresponds to approximately **12 words per minute** in Morse code.
- The `dotDelay` value can be modified to increase or decrease the transmission speed.
- The built-in LED on pin 13 does not require an external resistor.
- The Serial Monitor must be configured to **9600 baud**.

## Future Improvements

- Add a buzzer for audible Morse code transmission
- Support input from physical push buttons
- Store messages in EEPROM memory
- Implement Morse-to-text decoding
- Add transmission speed control using a potentiometer

## Technologies

- Arduino Uno
- Arduino IDE
- Embedded Systems
- C/C++
- Serial Communication
- Digital Electronics
- Morse Code Encoding
