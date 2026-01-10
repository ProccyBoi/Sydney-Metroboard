# Metroboard Arduino Sketch Upload Guide

## What is Metroboard?
Metroboard is a physical, LED-based transit map that lights up to show real-time
train activity. Each board connects to Wi-Fi, fetches updates from the Metroboard
service, and renders those updates on LED strips. The `Metroboard.ino`
sketch is the firmware that runs on the board’s microcontroller.

---

## Overview
You will:
1. Install the Arduino IDE.
2. Install the ESP32 board support.
3. Connect and power your board via USB-C.
4. Open the Metroboard sketch and enter your Wi-Fi + board ID.
5. Install the required libraries.
6. Verify (compile) the sketch.
7. Upload to the board.

---

## Prerequisites
- A Metroboard device.
- A **USB-C data cable** (some cables are charge-only).
- The **board ID** from the card included with your board.
- A computer with internet access.

---

## Step 1: Install the Arduino IDE
1. Download and install the Arduino IDE from:
   - https://www.arduino.cc/en/software
2. Launch the Arduino IDE.

---

## Step 2: Install ESP32 Board Support
Metroboard runs on an ESP32-based board. Install the official ESP32 core:
1. In the Arduino IDE, go to **File → Preferences**.
2. In **Additional Boards Manager URLs**, add:
   - https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
3. Click **OK**.
4. Go to **Tools → Board → Boards Manager…**
5. Search for **ESP32** and install **“esp32 by Espressif Systems”**.

---

## Step 3: Connect and Power the Board
1. Plug your Metroboard into your computer using **USB-C**.
2. Wait for your OS to finish installing drivers (first-time only).

---

## Step 4: Open the Sketch and Enter Your Board ID
1. In the Arduino IDE, go to **File → Open…**
2. Select `metroboard_public.ino`.
3. At the top of the file, fill in your Wi-Fi credentials and **board ID**:

```cpp
#define WIFI_SSID "YOUR_WIFI_SSID"
#define WIFI_PASS "YOUR_WIFI_PASSWORD"
static const char *kBoardId = "YOUR_BOARD_ID";
```

- The **board ID** is on the card included with your board.

---

## Step 5: Select the Correct Board and Port
1. Go to **Tools → Board** and choose the ESP32 board that matches your hardware.
   - If you are unsure, use the board name provided with your Metroboard kit.
2. Go to **Tools → Port** and select the port for your connected board.
   - Windows: COM ports (e.g., COM3)
   - macOS/Linux: `/dev/tty.*` or `/dev/ttyUSB*`

---

## Step 6: Install Required Libraries
The sketch depends on **two external libraries** you must install:

1. **Adafruit NeoPixel**
2. **ArduinoJson**

To install them:
1. Go to **Sketch → Include Library → Manage Libraries…**
2. Search for **Adafruit NeoPixel** and click **Install**.
3. Search for **ArduinoJson** and click **Install**.

> Note: `WiFi.h`, `HTTPClient.h`, and `WiFiClientSecure.h` are provided by the
> ESP32 board package you installed in Step 2.

---

## Step 7: Verify (Compile) the Sketch
1. Click the **checkmark** icon (Verify) in the toolbar.
2. Wait for **“Done compiling”**.
3. If you see errors, read the **first** error line carefully—it usually indicates
   the real issue (missing library, wrong board, etc.).

---

## Step 8: Upload the Sketch
1. Click the **right-arrow** icon (Upload).
2. Wait for **“Done uploading”**.
3. The board will reset and begin running the sketch.

---

## Step 9: Confirm It’s Running
Depending on the sketch behavior:
- LEDs should light or animate.
- You may see output in **Tools → Serial Monitor** (if enabled in the sketch).

---

## Troubleshooting
**Upload failed / “Failed to connect”**
- Ensure the correct board and port are selected.
- Try a different USB-C cable or port.
- Press the **BOOT** button on the board right as upload starts (some ESP32 boards
  require this).

**No serial port appears**
- Unplug/replug the board.
- Try another USB-C cable.
- Install USB/serial drivers if your board requires them.

**Missing library errors**
- Re-check Step 6 and install the named libraries via Library Manager.

---

## You’re done!
When you see **“Done uploading”**, your Metroboard firmware is installed and
running on your board.
