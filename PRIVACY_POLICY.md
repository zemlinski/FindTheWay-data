# Privacy Policy for FindTheWay

Last updated: July 23, 2026

FindTheWay is an outdoor navigation application for Android and Wear OS. This policy explains what data is processed, when it leaves your device, and the choices available to you.

## 1. Controller and contact

The controller of personal data processed through FindTheWay is **Paweł Zemliński**.

For privacy questions, requests to access or delete data, or questions about this policy, contact: **zemlinski.dev@gmail.com**.

## 2. Data processed on your device

The following data is normally stored and processed locally on your device:

* your current location, shown on the map and used during navigation;
* downloaded maps, offline routing data and offline search indexes;
* imported or created GPX tracks, saved places, route plans and app settings.

FindTheWay does not create a location history on servers operated by the developer. You can remove locally stored data in the app or by uninstalling the app.

FindTheWay opts out of Android cloud backup and device-to-device migration on both phone and Wear OS. In addition to setting `allowBackup=false`, the app's backup rules exclude all supported application-data domains from cloud backup and Android device transfer.

## 3. Location and navigation

The app can use foreground location to show your position and, while navigation is active, a foreground navigation service to follow progress and provide off-route alerts. The Android system displays a persistent notification while that service is active.

Offline routing is attempted first and does not send route coordinates from your device. If the necessary offline routing data is unavailable, the app asks for your explicit permission before it calculates a route online. If you allow it, the selected route points (their coordinates), routing profile and selected routing options are sent to **BRouter** or a compatible routing provider. The app does not send continuous location tracking to that provider. You can refuse this request or turn online route calculation off later in Settings.

## 4. Phone–Wear OS synchronization

When using FindTheWay on a Wear OS smartwatch:

* large map packages and GPX tracks are transferred directly over the local Wi-Fi network using a short-lived, single-use authenticated link. The receiving device verifies the file size and SHA-256 digest before publishing the file. This local transfer does not use an external file server, but the local HTTP connection itself is not TLS-encrypted;
* smaller messages, including saved locations, transfer offers, and active navigation/location updates, use the Google Play services Wearable Data Layer. Depending on device connectivity, the Data Layer can use Bluetooth or a Google-owned cloud relay. Google documents the cloud path as end-to-end encrypted.

The synchronized data is addressed only to the matching FindTheWay app installed with the same application signature on the user's paired devices.

## 5. Online services

When an online feature or online map source is used, the relevant request data is sent from your device to the provider needed to provide that feature:

* **Photon (Komoot)** — search text query and language code for online place search. Your current location coordinates are included only if you give explicit consent to use location for search result ranking (location bias); you can revoke or grant this consent at any time in Settings. Reverse geocoding sends the specific map coordinates you deliberately select, as this feature requires coordinates to determine place details.
* **BRouter / compatible routing providers** — selected route coordinates, routing profile and route options, but only after the explicit consent described above;
* **OpenFreeMap / OpenStreetMap and map data sources** — vector/raster map tiles, fonts, sprites, Waymarked Trails overlays, hillshade/elevation tiles from AWS S3, contour data from GitHub, and offline packages from GitHub or the FindTheWay download host. Tile and map-area requests identify the geographic area being viewed or downloaded and can overlap with your current area when location following is enabled. Providers also receive your IP address and standard technical request headers.
* **Overpass API mirrors** — when optional hiking POI data is included in an offline-map download, the app sends the geographic bounds of the selected download area to an Overpass mirror.

These providers process data under their own privacy policies. FindTheWay does not control their retention practices. Avoid using online features if you do not want the relevant request data to leave your device.

## 6. Voluntary feedback and bug reports

You may voluntarily send feedback or a bug report from the app. The text you enter is sent to **Discord** through a Discord webhook. A bug report also includes the app version, Android version, and device manufacturer/model. Log attachment is disabled by default. If you enable it, the report additionally includes app logs stored on your device. Before logs reach Logcat or a local log file, the app redacts exact coordinates, links, URI values, file paths, and common secret fields. The remaining logs can still describe recent app activity, route state, and device state. Please do not include sensitive personal information in a report or attach logs unless you want them sent with the report.

The developer uses these reports solely to respond to feedback and diagnose or fix problems. Reports remain stored in the developer's Discord channel until manually deleted or pruned by the developer. To request deletion of a submitted report at any time, email **zemlinski.dev@gmail.com** and include enough information to identify the report. Discord processes data under its own privacy policy.

## 7. Data retention

* Local maps, tracks, saved places, and settings remain on your device until you delete them or uninstall the app.
* The developer does not operate application servers that log or retain online routing or search requests. External providers may retain standard request data according to their own policies.
* Voluntary feedback and bug reports are retained in Discord until manually deleted or pruned by the developer or upon user request.

## 8. Your choices and rights

You can deny location permission, use downloaded data offline, decline online routing or search location bias, toggle these choices in Settings at any time, delete local content, and choose not to send feedback or diagnostic logs. Depending on applicable law, you may also request access, correction, deletion or restriction of personal data processed by the developer by contacting **zemlinski.dev@gmail.com**.

## 9. Changes to this policy

We may update this policy when the app’s data practices change. The current version is published at this page with its revision date.
