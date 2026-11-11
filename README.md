# Speaker BLE

Phone control for the Thylation solar speaker over Bluetooth LE: play a stored
clip, stop, volume, battery, turn Wi-Fi on for a while, and the "Wi-Fi off
while a NintiCam holds the Link" switch.

Open https://thylation-research.github.io/speaker-ble/ in **Bluefy** on iPhone (iOS Safari
has no Web Bluetooth) or in Chrome on Android / desktop.

Commands are signed with a key made from the speaker's 6-digit PIN
(HMAC-SHA256 over a fresh nonce, key = SHA-256("speaker-pin:" + PIN)), so the
PIN itself never goes over the air and the page alone cannot control a speaker.
The PIN is typed once and kept only in that browser's local storage. Five wrong
tries in a row lock the speaker's commands for 10 minutes.

Source of truth: the speaker firmware project (`main/ble.h` for the protocol);
this repository only publishes the page.
