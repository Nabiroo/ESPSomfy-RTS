# VIBRABOX firmware investigation — baseline checkpoint

Target: ESPSomfy-RTS v2.4.6, branch `fix/vibrabox-rf-events`.

Before changing firmware, reproduce the stock build, identify the toolchain and board configuration, verify web assets and LittleFS packaging, establish flash partition layout, and document recovery. Do not flash the live awning controller during baseline investigation.

Source observation: `Web.cpp` serves `/index.html` from LittleFS, and returns an error if the file is missing. Preserve the existing direct wind-sensor-to-motor pairing.
