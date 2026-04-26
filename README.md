# Nox-Dimmer

<br />
<p align="center">
  <a href="https://github.com/YashvardhanG/Nox-Dimmer">
    <img src="https://github.com/YashvardhanG/Nox-Dimmer/blob/main/nox_icon.ico" alt="Logo" width="128" height="128">
  </a>
  <h3 align="center">Nox Dimmer</h3>
  <p align="center">
    A Modern, Portable Screen Dimmer for Windows to Reduce Eye Strain
  </p>

  <p align="center">
  <a href="https://github.com/YashvardhanG/Nox-Dimmer/releases/latest"><img src="https://img.shields.io/github/v/release/YashvardhanG/Nox-Dimmer?style=flat-square&color=007ec6&label=Latest%20Release" alt="Version"></a>
  <img src="https://img.shields.io/badge/Platform-Windows_10%20%7C%2011-blue?style=flat-square" alt="Platform">
  <a href="https://github.com/YashvardhanG/Nox-Dimmer/blob/main/LICENSE"><img src="https://img.shields.io/github/license/YashvardhanG/Nox-Dimmer?style=flat-square&color=green" alt="License"></a>
  <img src="https://img.shields.io/badge/Price-Free-brightgreen?style=flat-square" alt="Price">
</p>


  <p align="center">
  <a href="https://ko-fi.com/I3I31XL6SJ" target="_blank">
    <img src="https://img.shields.io/badge/Buy%20me%20a%20coffee!-%235e8bde?style=flat&logo=ko-fi&logoColor=white" alt="Buy me a coffee!">
  </a>
</p>
</p>

<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about">About</a></li>
    <li><a href="#modes-explained">Modes Explained</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#installation">Installation</a></li>
    <li><a href="#development-setup">Development Setup</a></li>
    <li><a href="#uninstall--cleanup">Uninstall & Cleanup</a></li>
    <li><a href="#contribute">Contribute</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

## About

**Nox** is a lightweight utility designed to solve a common problem: **Monitors are often too bright, even at their lowest setting.**

Many external monitors and laptop screens have a minimum hardware brightness that is still uncomfortable in a dark room. Standard Windows settings can only go so far. Nox bridges this gap by using software-level adjustments to dim your screens beyond the physical hardware limits, significantly reducing eye strain during late-night work or media consumption.

It is built as a completely **portable application**. You do not need to install Python or any dependencies. Just download the executable, and it works.

Read more about it here: <a href = "https://medium.com/@yashvardhang11/my-monitors-0-brightness-was-still-blinding-me-so-i-built-nox-105e078dbe7e">Medium: Nox Dimmer</a>

## Modes Explained

Nox features two distinct dimming technologies to give you complete control over your viewing experience.

### 1. Normal Mode (Default)
In this mode, Nox uses **Gamma Ramps** to adjust the brightness signal sent to your monitor. 
* **How it works:** It manipulates the color curve of your graphics card.
* **Best for:** General use. It lowers brightness while maintaining decent contrast.
* **Limitation:** Gamma ramps have a "floor." They cannot turn a screen pitch black because the backlight usually stays on.

### 2. Hyper Mode 🚀
This is for when "dark" isn't dark enough.
* **How it works:** It combines the Gamma Ramp dimming from Normal Mode with a **transparent black overlay window** that sits on top of your desktop.
* **Why use it:** If you want your screen to be near-pitch-black (similar to an OLED experience) without turning it off. 
* **Smart Integration:** Unlike other dimmers that cover everything, Hyper Mode is designed to keep your **Taskbar visible** (though dimmed), so you don't lose track of your open apps.

## Usage

The interface is designed to be intuitive and minimal.

* **Master Slider:** This is the main control at the top. Moving this slider adjusts the brightness for **all connected monitors** simultaneously. Use this for quick, global adjustments across your entire setup. 
    * *Note:* The Master slider is designed to be dimmed and inaccessible when there is only one monitor connected (to reduce confusion) - Two monitors onwards, the master slider becomes accessible
* **Individual Display Controls:** Below the master slider, you will see a separate slider for every monitor connected to your PC (e.g., "Display 1", "Display 2"). You can fine-tune each screen independently. 
    * *Example:* You might want your main screen bright for gaming but your secondary screen dim for reading Discord/Spotify.
* **Run at Startup:** Check the box at the bottom left to have Nox launch quietly in the system tray every time you turn on your computer.
* **Check for Updates:** Nox automatically checks for updates on startup, otherwise you can manually check/download update from the button.

## Installation

Nox is a standalone app. 

1.  Go to the **[Releases](https://github.com/YashvardhanG/Nox-Dimmer/releases)** section on the right side of this page.
2.  Download the latest `Nox_v1.0.zip`.
3.  Extract the zip file.
4.  Run `Nox.exe`.

**⚠️ A Note on Windows SmartScreen**

Because Nox Dimmer is a free, open-source indie utility, it does not currently have an expensive publisher certificate. As a result, Windows Defender SmartScreen will likely flag the application as an "unrecognized app" the first time you try to run it.

This is completely normal for new indie software. To safely run Nox:
- Click "More info" on the SmartScreen popup.
- Click the "Run anyway" button that appears.
(If you ever have security concerns, the full source code is always open and available to review right here in the repository!)

That's it! No installation wizard required.

## Development Setup

If you want to edit the code, run the source file directly, or build the executable yourself, follow these steps.

### Prerequisites
* Python 3.x installed.

### Steps
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YashvardhanG/Nox-Dimmer.git](https://github.com/YashvardhanG/Nox-Dimmer.git)
    cd Nox-Dimmer
    ```

2.  **Install dependencies:**
    Run the following command to install the necessary libraries (`screeninfo`, `pystray`, `Pillow`, etc.) from the requirements file.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the source code:**
    You can now run the app directly via Python:
    ```bash
    python nox.py
    ```

## Uninstall & Cleanup

To uninstall Nox, you simply need to **delete the `Nox.exe` file**.

**Important Note:** If you enabled "Run at Startup" and deleted the app without unchecking it first, Windows might still try to launch it (and fail). To cleanly remove the startup registry entry, run the following command in **PowerShell**:

```powershell
Remove-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "Nox Dimmer" -ErrorAction SilentlyContinue; Write-Host "Startup entry 'Nox Dimmer' removed."
```

## Contribute

Every program is ever evolving and, that is possible only with valuable contributions. Any contributions you make are greatly appreciated. 
<ol>
  <li>Fork the Project</li>
  <li>Create your Feature Branch (git checkout -b functionalities/Feature)</li>
  <li>Commit your Changes (git commit -m 'Add a Feature')</li>
  <li>Push to the Branch (git push origin functionalities/Feature)</li>
  <li>Open a Pull Request</li>
</ol>

<br>**Liked the app?** Please **Star ✨** the repository, and if you do want to support further, you can always <a href='https://ko-fi.com/I3I31XL6SJ' target='_blank'>buy me a coffee!</a> ☕

<!-- CONTACT -->
## Contact

<p align="center">
  <br>
  <img src="https://github.com/YashvardhanG/YashvardhanG/blob/main/Wolf_1.jpg" alt="Logo" width="150" height="150"><br>
  <a href = "https://www.yashvardhang.dev/">Connect with me! | Yashvardhan Gupta</a><br><br>
  <a href='https://ko-fi.com/I3I31XL6SJ' target='_blank'>
    <img height='40' style='border:0px; height:40px;' src='https://storage.ko-fi.com/cdn/kofi5.png?v=6' border='0' alt='Buy Me a Coffee!' />
  </a>
</p>
