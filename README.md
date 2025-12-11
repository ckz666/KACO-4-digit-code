# KACO-4-digit-code
This repository provides a small, browser‑based helper tool to derive the 4‑digit device code from the serial number (SN) of a KACO blueplanet NX3 M2 inverter. The calculation is performed entirely client‑side in the browser using HTML and JavaScript.

Background
The logic implemented here is based on the excellent reverse engineering work by Jan Dittmer in the following project:

[trixing/kaco-http](https://github.com/trixing/kaco-http)

In that repository you will find a detailed description of the HTTP interface, the Android app behaviour, and a Python implementation of the password generation algorithm (kaco_pass.py).

This project simply re‑implements the same algorithm in JavaScript and exposes it via a small responsive web page that can be opened locally (no backend, no network connection required once the file is loaded).

How it works
Input: inverter serial number (SN), e.g. 20.0NX312077827

Processing: AES‑ECB encryption with a fixed key, Base64 encoding, MD5 hashing, and extraction of a 4‑character substring

Output: 4‑digit device code plus some intermediate values for debugging (encrypted string, MD5, L16)

All computation happens in the browser; no data is sent to any server.

Usage
Clone or download this repository.

Open the index.html file in a modern web browser (desktop or mobile).

Enter the inverter serial number and press Calculate.

The 4‑digit device code and intermediate values will be displayed.

Disclaimer
This tool is provided for informational and testing purposes only. Any use is at your own risk.
The author assumes no responsibility or liability for any loss, damage, misconfiguration, or other consequences resulting from the use of this tool.

This project is not affiliated with or endorsed by KACO new energy GmbH or any related entity.
