# Modbo 5.0 Firmware and Flash Repair Guide

[![Watch the video](https://img.youtube.com/vi/Fm0x56Zls0I/maxresdefault.jpg)](https://youtu.be/Fm0x56Zls0I)

> 🎥 **Video Walkthrough:**  
> [Watch on YouTube](https://youtu.be/Fm0x56Zls0I)


> ⚠️ **Disclaimer:**  
> This is an advanced procedure. I am **not responsible** for any damage to consoles or modchips. Proceed **at your own risk.**

---

## 📁 Firmware Files Overview

| File Name                      | Description                                         |
|-------------------------------|-----------------------------------------------------|
| `OriginalModboFirmware.bin`   | Default, unmodified Modbo 5 firmware               |
| `NoLogoOriginalModboFirmware` | Firmware with Matrix logo removed                  |
| `fhLogo.bin`                  | Custom firmware with **Foxhound** logo at startup  |
| `FOX.bin`                     | Custom firmware with **FOX (MGS3)** logo at startup|

---

## 💾 Flash Memory Details

- **Flash IC used:** Winbond `W25Q40CLSNIG`
- **Matrix PS2 disc boot image offset:** `0xE000` to `0xEFFF`

---

## 🖼️ Custom Boot Image Requirements

To insert a custom image into the firmware:

- **Image format:** BMP (monochrome)
- **Size:** 128×32 pixels
- **Color depth:** 256 grayscale (`0,0,0` to `255,255,255`)
- **Transparency:** First palette entry must be fully transparent
- **Orientation:** The BMP must be flipped vertically before insertion

> The image is rendered upside down and then displayed correctly on boot.

---

## 🛠️ Repairing a Bad Flash

### 1. Obtain a Good Dump

Get a working firmware dump from another modchip. For Modbo 5.0, you can use the provided `OriginalModboFirmware.bin`.

### 2. Flash the Replacement Memory

Use a supported flash programmer. Example:

- **Programmer:** Flashcat Xport  
- **Adapter:** SOIC-8 Narrow  
- **Flash IC:** Winbond `W25Q40CLSNIG`

### 3. Replace the Faulty IC

- Desolder the old flash IC
- Solder the new chip **with correct orientation**
  - On Modbo 5.0D, **Pin 1 should face the PCB edge**
- Incorrect orientation can permanently damage the IC

### ✅ Done!

---

## ⚠️ Notes & Limitations

- This method has been successful on **two Modbo chips**, but results may vary
- A black screen may be caused by other hardware issues
- **Do not attempt to increase flash size** (e.g., using an 8Mbit chip instead of a 4Mbit one), even if the pinout and commands are compatible
