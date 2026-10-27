# magiment

A layer of iron filings for your screen. Open on a phone,
hold a magnet against or near the device, and the field of black dots
pulls toward it. Remove the magnet and the layer settles back into a
uniform grain.

**How it works**

- A jittered grid of canvas dots forms a homogeneous layer on white.
- The [Generic Sensor](https://developers.google.com/web/updates/2018/04/generic-sensor)
  `Magnetometer` API (Chrome on Android) reads the ambient magnetic field.
  The Earth's ~50 µT background is subtracted with a rolling baseline, so
  only the *change* a magnet causes moves the dots.
- Field strength scales the pull; the horizontal field direction places a
  virtual anchor the dots gravitate toward. A little friction and a spring
  back to their home positions keep the layer calm when the magnet leaves.
- Desktop visitors get a QR code pointing at the same page, since the
  trick needs a phone's compass.
- On browsers without compass access (e.g. iOS Safari), drag your finger
  to feel a virtual magnet instead.

**Run locally**

```sh
python3 -m http.server 8000   # Generic Sensor APIs need https, or localhost
# then open http://localhost:8000
```

**Deploy** — GitHub Pages: deploy from the `main` branch, root.

**Credits** — © Markus · [@mkshoff](https://www.instagram.com/mkshoff/)