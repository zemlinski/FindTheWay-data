> **This policy has moved.** The current version is published at <https://zemlinski.github.io/findtheway/privacy/>. The text below is a copy of it from November 3, 2026.

# Privacy Policy for FindTheWay

Last updated: November 3, 2026

FindTheWay is an outdoor navigation application for Android and Wear OS. This policy explains what data is processed, when it leaves your device, and the choices available to you.

## 1. Controller and contact

The controller of personal data processed through FindTheWay is **Paweł Zemliński**.

For privacy questions, requests to access or delete data, or questions about this policy, contact: **zemlinski.dev@gmail.com**.

## 2. Data processed on your device

The following data is normally stored and processed locally on your device:

* your current location, shown on the map and used during navigation;
* downloaded maps, offline routing data and offline search indexes;
* imported or created GPX tracks, saved places, route plans and app settings;
* your search history: the places you picked from search results (name, coordinates and type, up to 20, newest first). It is never sent anywhere or synchronized, and you can delete single entries, clear the whole list, or turn the history off in Settings, which also deletes it.

FindTheWay does not create a location history on servers operated by the developer: the download server keeps no history of downloads or locations (see section 7). You can remove locally stored data in the app or by uninstalling the app.

FindTheWay disables Android's automatic cloud backup and system device-to-device transfer for app data on the phone and Wear OS. App settings, GPX tracks, saved places, maps, logs and active navigation are not included in those system transfers. The separate phone–Wear OS synchronization described below remains available when you use paired devices.

## 3. Location and navigation

The app can use foreground location to show your position and, while navigation is active, a foreground navigation service to follow progress and provide off-route alerts. The Android system displays a persistent notification while that service is active.

Offline routing is attempted first and does not send route coordinates from your device. If the necessary offline routing data is unavailable, the app asks for your explicit permission before it calculates a route online. If you allow it, the selected route points (their coordinates), routing profile and selected routing options are sent to **BRouter** or a compatible routing provider. The app does not send continuous location tracking to that provider. You can refuse this request or turn online route calculation off later in Settings.

## 4. Phone–Wear OS synchronization

When using FindTheWay on a Wear OS smartwatch:

* large map packages and GPX tracks are transferred directly over the local Wi-Fi network using a short-lived, single-use authenticated link. The receiving device verifies the file size and SHA-256 digest before publishing the file. This local transfer does not use an external file server, but the local HTTP connection itself is not TLS-encrypted;
* smaller messages, including saved locations, transfer offers, and active navigation/location updates, use the Google Play services Wearable Data Layer. Depending on device connectivity, the Data Layer can use Bluetooth or a Google-owned cloud relay. Google documents the cloud path as end-to-end encrypted.

The synchronized data is addressed only to the matching FindTheWay app installed with the same application signature on the user's paired devices.

The watch keeps a small rotating log file (about 512 KB) for this purpose; it is not backed up or transferred anywhere except as part of a report you send.

## 5. Online services

When an online feature or online map source is used, the relevant request data is sent from your device to the provider needed to provide that feature:

* **FindTheWay server (findtheway.duckdns.org)** — a download server operated by the developer and hosted by netcup GmbH in Germany (EU). The phone downloads from it the map packages, outdoor packages (hiking, cycling, water and points), contour packages, offline search indexes and the world overview map. A Wear OS watch downloads map packages and the world overview map from it directly. When you start a map download or update, the app also reads a small file (`min_version.json`) from this server to check whether this app version can still download map data. Some requests happen without you starting a download: the phone and the watch download the world overview map when they do not have it yet, usually during first setup; each time the phone app starts with downloaded maps, it asks this server whether newer versions of the installed packages exist; and the map download list asks for package sizes. Each request names the requested file, which shows the country or package concerned. Like any web server, it receives your IP address and standard technical request headers such as the user agent, which it needs to answer the request; it does not record them, except in an error log entry about a critical server failure described in section 7.
* **GitHub** — release files of the public FindTheWay-data repository are a fallback source of several offline packages and of the world overview map, used when the FindTheWay server does not respond or does not provide the file. GitHub receives the same kind of request data.
* **BRouter offline routing data** — when a map download includes offline routing, the BRouter routing data files covering that area (each file covers 5° × 5°) are downloaded from brouter.de. The map download list also asks brouter.de for the sizes of these files. The file names identify the area.
* **Photon (Komoot)** — search text query and language code for online place search. Your current location coordinates are included only if you give explicit consent to use location for search result ranking (location bias); you can revoke or grant this consent at any time in Settings. Reverse geocoding sends the specific map coordinates you deliberately select, as this feature requires coordinates to determine place details.
* **BRouter / compatible routing providers** — selected route coordinates, routing profile and route options, but only after the explicit consent described above;
* **OpenFreeMap / OpenStreetMap and map data sources** — vector/raster map tiles, fonts, sprites, Waymarked Trails overlays, and hillshade/elevation tiles from AWS S3, shown online and downloaded for offline hillshading. Tile and map-area requests identify the geographic area being viewed or downloaded and can overlap with your current area when location following is enabled. Providers also receive your IP address and standard technical request headers.
* **Overpass API mirrors** — when optional hiking POI data is included in an offline-map download, the app sends the geographic bounds of the selected download area to an Overpass mirror.
* **Google Play** — if this app version can no longer download map data and you tap Update, the app asks Google Play for an in-app update or opens the app's page in the Play Store.

Third-party providers process data under their own privacy policies. FindTheWay does not control their retention practices. Avoid using online features if you do not want the relevant request data to leave your device.

## 6. Voluntary feedback and bug reports

You may voluntarily send feedback or a bug report from the app. The text you enter is sent to **Discord** through a Discord webhook. A bug report also includes the app version, Android version, and device manufacturer/model. Log attachment is disabled by default. If you enable it, the report additionally includes app logs stored on your phone and, when a paired Wear OS watch with FindTheWay is reachable at that moment, a snapshot of the app logs stored on the watch, which the watch sends to the phone through the Wearable Data Layer. The same redaction applies on the watch and again on the phone before sending. Before logs reach Logcat or a local log file, the app redacts exact coordinates, links, URI values, file paths, and common secret fields. The remaining logs can still describe recent app activity, route state, and device state. Please do not include sensitive personal information in a report or attach logs unless you want them sent with the report.

The developer uses these reports solely to respond to feedback and diagnose or fix problems. Reports remain stored in the developer's Discord channel until manually deleted or pruned by the developer. To request deletion of a submitted report at any time, email **zemlinski.dev@gmail.com** and include enough information to identify the report. Discord processes data under its own privacy policy.

## 7. Data retention

* Local maps, tracks, saved places, and settings remain on your device until you delete them or uninstall the app. Android's automatic cloud backup and system device migration do not preserve FindTheWay app data.
* The FindTheWay server keeps no access log: it does not record IP addresses or the files you download. The only exception is its error log, which records only critical server failures; such an entry can include the IP address of the connection it concerns and details of that request, such as the requested file. Error log entries are kept for up to 15 days, then deleted automatically, and are used only to operate the server and keep it secure.
* Online routing and online search requests go to the external providers described in section 5, not to a server operated by the developer. External providers may retain standard request data according to their own policies.
* Voluntary feedback and bug reports are retained in Discord until manually deleted or pruned by the developer or upon user request.

## 8. Legal basis

Under Article 6(1) of the EU General Data Protection Regulation (GDPR), the developer relies on:

* **legitimate interests (Art. 6(1)(f))** for delivering the files the app requests from the FindTheWay server, including map packages and update checks, for the server's error log, which is needed to run the server and keep it secure, and for sending the requests described in section 5 that the online features you use need, other than those based on consent below;
* **consent (Art. 6(1)(a))** for online route calculation, for using your location to rank search results (location bias), and for logs attached to a bug report. You can withdraw consent at any time: online routing and location bias in Settings, and logs already sent by asking the developer at **zemlinski.dev@gmail.com** to delete the report. Withdrawal does not affect processing that took place before it;
* **legitimate interests (Art. 6(1)(f))** for the feedback and bug reports you send and the emails you write to the developer, which are used to reply to you and to diagnose and fix problems.

## 9. Your choices and rights

You can deny location permission, use downloaded data offline, decline online routing or search location bias, toggle these choices in Settings at any time, delete local content, and choose not to send feedback or diagnostic logs. Depending on applicable law, you may also request access, correction, deletion or restriction of personal data processed by the developer, or object to processing based on legitimate interests, by contacting **zemlinski.dev@gmail.com**. You also have the right to lodge a complaint with a data protection supervisory authority: in Poland, the President of the Personal Data Protection Office (Prezes Urzędu Ochrony Danych Osobowych, UODO), or the authority in the EU/EEA country where you live or work or where the alleged infringement took place.

## 10. Changes to this policy

We may update this policy when the app’s data practices change. The current version is published at this page with its revision date.
