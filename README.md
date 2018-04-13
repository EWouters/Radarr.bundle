## This project is not working at the moment! Feel free to fix. I just forked this to check what it would take to convert this to work for Radarr.

# Radarr.bundle

A plugin for [Plex Media Server](https://plex.tv/) that is a client for [Radarr](https://radarr.video/) (forked from [Sonarr.bundle](https://github.com/jamorin/Sonarr.bundle)).

![Screenshot](screenshot.png)

- View your TV shows, calendar (current week), queue, missing episodes, history and more.
- Add new series to your collection
- Auomatic search, delete, and update existing shows, seasons, or episodes.
- Manual searches for individual episodes.
- Supports basic auth reverse proxies.
- Updating the plugin should be possible through the plugin when newer versions become available (but this is untested :smile:).

## Install
1. Download "Source Code (zip)" from the [Latest Release](https://github.com/EWouters/Radarr.bundle/releases/latest).
2. Unzip `Radarr.bundle-VERSION.zip`
3. Rename `Radar.bundle-VERSION` to `Radarr.bundle`
4. Move `Radarr.bundle` folder to `"<PMS Installation>/Library/Application Support/Plex Media Server/Plug-ins"` along with the rest of your plugins.
5. Might need to restart Plex Media Server to detect the new plugin.
6. Change the plugin's settings by adding your endpoint, API Key, etc...
7. Profit.
	
## Configuration
|Key|Default Value|Required|Description|
|---|---|---|---|
|Endpoint|http://127.0.0.1:7878|Yes|Radarr's URL endpoint including the URL base. Example behind a reverse proxy: https://sub.mydomain.com/radarr|
|API Key|_empty_|Yes|Found in Radarr's General Settings|
|Username|_empty_|No|Username for Basic Auth. This is **NOT** the Username in Sonarr's settings. This is for cases where Plex has to access Sonarr behind a nginx proxy configured with basic auth.|
|Password|_empty_|No|Optional - See Username.|

Note - If datetimes appear wrong, please check the timezone of your server and set it to your desired timezone. If you're running Plex in a [Docker](https://hub.docker.com/r/linuxserver/plex/) container, it's probably UTC. You can set the timezone with an environment variable such as `TZ=America/Phoenix`. There is an example docker-compose.yml file in the `docker` folder.

It's recommended now to install from the zip file as explained above. Previously recommended that you could install the plugin by cloning the repo. However, going forward you should be able to update the plugin from within the plugin now.
