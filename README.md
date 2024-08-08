# Siyi_A2_MINI
Configures the network to connect the SIYI A2 camera directly through the Linux ethernet port.

Attention: also read [A2-mini-User-Manual-v1.1](A2-mini-User-Manual-v1.1.pdf)

## Testing Connection

Before connecting to your media player, check the connection to the camera by running `ping 192.168.144.25`

## Connect with Gstreamer
```sh
gst-launch-1.0 -v rtspsrc location=rtsp://192.168.144.25:8554/main.264 latency=0 buffer-mode=auto ! rtph265depay ! h265parse ! decodebin ! videoconvert ! autovideosink
```

OBS:
the system **cannot be connected to the wifi network**.

## Based on:
https://discuss.cubepilot.org/t/ground-unit-eth0-not-getting-an-ip/10473/6
