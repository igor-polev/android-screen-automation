# Android Screen Automation

Automation of Android applications driven by real-time video capture and computer vision.

## Overview

The application mirrors an Android device to the host through `scrcpy`, receives the video
stream as a V4L2 loopback device, searches each frame for predefined graphics patterns with
OpenCV, and triggers input actions depending on the state recognised on screen.

Patterns and the actions bound to them are described in JSON configuration files, so
supporting another application means writing a new configuration rather than new code.

## Runtime requirements

- `dkms`, `v4l2loopback-dkms`, `v4l2loopback-utils`
- `scrcpy` (see scrcpy's Video4Linux notes)
- `sudo` — required to set up the v4l2loopback devices

## Build dependencies

OpenCV, nlohmann_json, CMake. C++17.

Clone with submodules:

    git clone --recurse-submodules https://github.com/igor-polev/android-screen-automation.git

## Usage

    asa <config.json>

## Third-party code

The V4L2 C++ wrapper by Michel Promonet is included as a submodule
(https://github.com/mpromonet/libv4l2cpp) and remains under its own licence.

## Related project

A later Windows version of the same idea, based on desktop screen capture instead of
device mirroring: https://github.com/igor-polev/screen-vision-automation
