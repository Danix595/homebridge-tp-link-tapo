# Homebridge TP-Link Tapo (Updated & Maintained Fork)

This is an **actively maintained fork** of the original `homebridge-tp-link-tapo` plugin, which was archived by its author.

### What's new in this fork?
- **Stability Fixes:** Fixed severe Homebridge crashing/hanging issues caused by TP-Link devices disconnecting from the network or changing IP addresses. HTTP requests now properly time out and gracefully report devices as "No Response" natively in HomeKit.
- **Homebridge v2 Ready:** Fully compatible with Homebridge v2 and Node.js v24+. 
- **Clean Dependencies:** Addressed critical vulnerabilities in older dependencies.

I recommend using the platform as a Child Bridge for the best performance. Most of the time the response time between the app and the device is ~80ms (much faster than the official app).

### Installation

If you are coming from the original plugin, you must install this new updated package.

**Using the Homebridge UI:**
Search for `homebridge-tp-link-tapo-updated` in the Plugins tab and click install.

### Current device types

- Socket/Outlet (For devices with power measurement, they have a contact sensor, open means the current is > 0 and closed is 0)
- Hub (As alarm)
- Button S200
- Contact Sensor (T110)
- Light Bulb
- LED Strip

For other device types, just open an issue on the GitHub repository.

### Config

You can add multiple devices with a single platform configuration.

```json
{
  "platforms": [
    {
      "platform": "HomebridgeTPLinkTapo",
      "name": "TPLink Tapo Platform",
      "email": "tplink-email",
      "password": "tplink-password",
      "addresses": ["192.168.x.x (the ip address of the device)"]
    }
  ]
}
```
