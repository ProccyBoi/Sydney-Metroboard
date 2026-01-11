# Metroboard Quickstart Guide

## What is Metroboard?
Metroboard is a physical, LED-based transit map that lights up to show real-time
train activity. Each board connects to Wi-Fi, fetches updates from the Metroboard
service, and renders those updates on LED strips. The firmware is preloaded on
your board, so no upload is required.

---

## Overview
You will:
1. Plug in and power the board.
2. Connect to the Metroboard setup Wi-Fi.
3. Open the setup page.
4. Enter your Wi-Fi details and board ID.
5. Let the board reboot and connect.

---

## Prerequisites
- A Metroboard device.
- A **USB-C power source** (wall adapter, power bank, or computer USB port).
- The **board ID** from the card included with your board.
- A phone or computer with Wi-Fi.

---

## Step 1: Plug In and Power the Board
1. Plug your Metroboard into power using **USB-C**.
2. Wait about 10–20 seconds for it to boot.

---

## Step 2: Connect to the Setup Wi-Fi
On first boot (or if Wi-Fi fails), the board creates its own setup network:

1. On your phone/laptop, join the Wi-Fi network:
   - **`Metroboard-Setup-<hex>`**

---

## Step 3: Open the Setup Page
1. Open a browser and go to:
   - **http://192.168.4.1**
2. You should see the Metroboard setup form.

---

## Step 4: Enter Your Details
Fill in:
- **Wi-Fi SSID**
- **Wi-Fi Password**
- **Board ID** (from your card)

Then click **Save & Restart**.

---

## Step 5: Wait for the Board to Reboot
After saving, the board will reboot, join your Wi-Fi, and remember your settings
after power cycles.

---

## Confirm It’s Running
Depending on your configuration:
- LEDs should light or animate.
- You may see output in the Serial Monitor (not required for normal use).

---

## Troubleshooting
**Can’t find the setup Wi-Fi**
- Power-cycle the board and wait 10–20 seconds.
- Ensure you’re within Wi-Fi range.

**Setup page won’t load**
- Confirm you’re connected to **Metroboard-Setup-<hex>** (not your home Wi-Fi).
- Use **http://192.168.4.1** (not HTTPS).
- Try a different browser.

**Board won’t connect after saving**
- Double-check the SSID and password.
- Reboot the board to re-open the setup portal and try again.

---

## 🔧 Board settings (edit here)
Use this link to modify board settings:
**https://damp-catlin-metroboard-7be2a3b3.koyeb.app/login**
