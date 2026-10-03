# Unraid templates

Unraid application templates maintained by CentauriPrime.

- [WeatherNode](https://github.com/centauri/WeatherNode)
- [Blink Camera Relay](https://github.com/centauri/blink-camera-relay) (experimental; Community Apps listing not yet verified)

## Install

Search for **WeatherNode** in the Apps tab on your Unraid server.

To add it by hand instead, go to **Docker > Add Container** and paste this into **Template**:

```
https://raw.githubusercontent.com/centauri/unraid-templates/main/templates/weathernode.xml
```

## What the template sets up

- One container that runs the website and the background tasks.
- Two folders under `/mnt/user/appdata/weathernode/`:
  - `storage` holds logs, caches and the secret key (`storage/app/.app-key`) that encrypts saved API keys and passwords.
  - `database` holds the SQLite database.
- The website runs on port **10130**, which no other app in Community Applications uses by default.
- The only field you must fill in is **Site address (APP_URL)**, the address you open WeatherNode on, for example `http://192.168.1.10:10130`.

Back up both folders. Without the key in `storage`, saved API keys and passwords cannot be read.

## Support

Open an issue at https://github.com/centauri/WeatherNode/issues

## Files

- `ca_profile.xml`: the repository profile shown in Community Applications.
- `templates/weathernode.xml`: the WeatherNode container template.
- `icons/weathernode.png`: the app icon.

## Blink Camera Relay

The authoritative template is [templates/blink-camera-relay.xml](templates/blink-camera-relay.xml).

Raw XML: https://raw.githubusercontent.com/centauri/unraid-templates/main/templates/blink-camera-relay.xml

This template runs one container with the onboarding dashboard, Blink livestream
worker, MediaMTX and ONVIF adapter. It uses the experimental `edge` image and
host networking. Set the server LAN IPv4 address and an admin password of at
least 12 characters. Appdata is stored under `/mnt/user/appdata/blink-camera-relay`.
Open `http://SERVER_IP:8787` and sign in as `admin`, then complete Blink onboarding.
See the [application README](https://github.com/centauri/blink-camera-relay) for
port requirements and limitations. This is not a claim of Community Apps approval.

Support: https://github.com/centauri/blink-camera-relay/issues
