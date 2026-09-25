# Unraid templates

Unraid Community Applications templates for [WeatherNode](https://github.com/centauri/WeatherNode).

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
- The only field you must fill in is **Site address (APP_URL)**, the address you open WeatherNode on.

Back up both folders. Without the key in `storage`, saved API keys and passwords cannot be read.

## Support

Open an issue at https://github.com/centauri/WeatherNode/issues

## Files

- `ca_profile.xml`: the repository profile shown in Community Applications.
- `templates/weathernode.xml`: the WeatherNode container template.
- `icons/weathernode.png`: the app icon.
