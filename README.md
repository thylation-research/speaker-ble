# Speaker BLE

Phone control for the Thylation solar speaker over Bluetooth LE: play a stored
clip, stop, volume, battery, turn Wi-Fi on for a while, and the "Wi-Fi off
while a NintiCam holds the Link" switch.

Open https://thylation-research.github.io/speaker-ble/ in **Bluefy** on iPhone (iOS Safari
has no Web Bluetooth) or in Chrome on Android / desktop.

Commands are signed with the speaker's BLE key (HMAC-SHA256 over a fresh nonce),
so the page alone cannot control a speaker. The key is entered on the phone (or
opened once as a link ending in `#k=<hex>`) and kept only in that browser's
local storage; it is never sent anywhere else and is not in this repository.

Source of truth: the speaker firmware project (`main/ble.h` for the protocol);
this repository only publishes the page.
