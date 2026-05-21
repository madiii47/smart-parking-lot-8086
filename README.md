# Smart Parking Lot Management System (8086 Assembly Language)

A robust, low-level console application simulating an automated parking garage management system, written in **8086 Assembly Language** and designed for the **EMU8086** environment.

This project implements strict hardware-representative logic, register-level optimization, dynamic variable-length numeric input processing, and boundary safety limits ($0$ to $80$ spots).

## 🚀 Features

- **Secure Terminal Access:** Protected by a 4-digit operator gate passcode verification routine.
- **Dynamic Variable-Length I/O:** Natively parses keystrokes into 16-bit integers until `ENTER` (ASCII 13) is pressed, resolving register-contamination bugs common in static 4-digit input routines.
- **Upper-Bound Safety Validation:** Restricts total available slots to a hard cap of 80. Prevents operators from "freeing" space if no cars are parked (Lot Empty Check).
- **Lower-Bound Safety Validation:** Evaluates incoming vehicle batches against active vacant spaces to prevent integer underflow and flag overflow issues (Lot Full Check).
- **Auto-Spacing UI:** Automatically injects clean carriage returns and line feeds (`10,13`) when looping the administrative menu back to the console for high readability.

## 🛠️ Concepts & Technologies Used

- **Language:** 8086 Assembly Language
- **IDE/Emulator:** EMU8086
- **DOS Interrupts:** `INT 21H` (Functions `01H` for input, `02H` for character output, `09H` for string printing, and `4CH` for process termination).
- **Memory Manipulation:** Direct segmentation management, custom stack utilization (`PUSH`/`POP`) for reversing digit strings during base-10 division, and immediate addressing modes.
- **Flow Control:** Conditional branching (`JE`, `JNE`, `JA`, `JB`) paired with comparison operations (`CMP`) to enforce physical data limitations.

## 💻 How to Run

1. Download and install the **EMU8086** emulator.
2. Clone this repository or copy the `.asm` source file.
3. Open the file inside EMU8086.
4. Click **Compile** and then **Emulate**.
5. Run the program and enter the default gate operator passcode: `1234`.

---
*Developed as part of the Computer Organization and Assembly Language (COAL) Lab curriculum.*
