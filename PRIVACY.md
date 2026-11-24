# daarc2d2 privacy policy

Last updated: November 24, 2026. Applies to the project's Android app.
Developer: Jared Ringenberg (KJ7UDQ). For support, privacy questions, or
data requests, email [uzyrexthet@gmail.com](mailto:uzyrexthet@gmail.com).

## In brief

daarc2d2 controls a nearby droid over Bluetooth or a host you choose. The app
does not require an account or a maintainer-operated cloud service, and the
reviewed app code has no advertising, maintainer analytics, or automatic crash
reporting service. It is not an entirely offline app: the QR-scanning SDK can
send Google diagnostic/usage data, and your speech service may process audio
online. Android's backup services may also copy stored app data.

**Try demo mode** uses a virtual droid and accepts typed voice commands. Demo
settings, routines, and activity stay in memory and are discarded when you exit.

## What the app uses and stores

- Bluetooth discovery uses nearby droid names, device identifiers, signal strength,
  and advertised personality/affiliation information. Saved profiles can contain
  a nickname, appearance/hardware notes, settings, favorites, routines, and paths.
  Drawn paths are sketches, not GPS location records.
- Pairing with a host uses its address, port, and pairing code. The app remembers
  that host and credential in ordinary app preferences, not an encrypted secret
  vault. A device hosting the dashboard also saves its own pairing credential.
- Optional shake/tilt controls use live motion-sensor readings while enabled.
  The app does not save a motion history and turns these controls off when it
  leaves the foreground.
- Diagnostics keep a bounded in-memory session log of connection activity,
  identifiers, commands, and errors. The app does not automatically upload it
  to the maintainer. Only share logs or screenshots after removing sensitive
  information, especially pairing codes/QR codes, device IDs, and personal notes.

## Camera and Google ML Kit

The camera is used when you open the optional computer-pairing QR scanner. The
app extracts the host address and pairing credential from the QR code; it does
not save camera photos or videos. You can use manual address/code entry instead.

Android QR recognition uses Google's bundled ML Kit barcode scanner. According
to Google, image processing happens on-device; ML Kit does not send those input
images or decoded results to Google servers. ML Kit does send diagnostic/usage
metrics, including device/OS and app information, per-installation identifiers,
performance, API configuration, feature versions, input/output sizes, and event
or error information. Google says these metrics use HTTPS and are used to
diagnose, maintain, and improve its SDKs and detect misuse.

ML Kit may initialize when the app starts, not only when the scanner is opened,
and may contact Google for SDK/model updates or compatibility information. The
app has no ML Kit metrics opt-out switch. Avoiding camera permission or not
opening the scanner is not a promise that the included SDK makes no network
requests. Google's policies govern its processing and retention:

https://developers.google.com/ml-kit/terms
https://developers.google.com/ml-kit/android-data-disclosure
https://policies.google.com/privacy

## Microphone and voice shortcuts

Voice input starts when you choose Push to talk and uses Android's configured
speech-recognition service. The app does not force offline-only recognition.
Depending on your device, provider, language, and settings, audio may be sent
to that provider's servers. Review that provider's privacy settings/policy.

The app displays recognized text temporarily and matches it to droid commands.
It does not save audio recordings or transcripts in its preferences or send
them to a maintainer-operated server. The speech provider may handle or retain
audio/results under its own policy. You can avoid voice input and revoke the
app's microphone permission without losing manual controls.

## Local network and dashboard

Host discovery uses local-network mDNS. A running host advertises its service
and port, not its pairing code. Paired clients exchange control commands and
status, including droid identifiers/names, settings, active actions, and automation
client identifiers. Choosing a remote host sends the pairing credential to that
host. Only use hosts and networks you trust.

The built-in host uses HTTP: authentication does not encrypt traffic. Do not
port-forward the dashboard or expose it publicly. Pairing QR codes contain a
credential; do not publish them. The browser dashboard keeps its pairing token
and client identifier in browser session storage; browser restore/site-data
settings can affect how long that remains available.

## Software updates

Google Play installations receive updates through Google Play. On builds
downloaded directly, **Droids → Software updates → Check for updates** contacts GitHub's
public API for `daarcjared/daarc2d2-releases`. Choosing **Download & install**
downloads a release package and, when needed, checksums from GitHub and its
release CDN. GitHub receives your IP address, a generic app updater user-agent,
and ordinary request metadata under its own privacy policy:
https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement

No account, pairing credentials, droid profiles, saved routines, or session logs
are sent by the updater. It does not check in the background. Downloaded packages
are stored in the app's temporary cache until cleared by the OS or app storage
controls. Android's optional **Install unknown apps** approval lets the app open
the system package installer for a verified update; installation still requires
your approval. You can leave this permission disabled and install releases manually.

## Permissions, retention, and your choices

Bluetooth/Nearby Devices permissions enable discovery/control. On older Android
versions, location permission is used for BLE scanning; the app does not request
GPS coordinates. Camera and microphone support the optional QR/voice features.
Network access supports discovery, chosen hosts, requested software updates, and the SDK/service behavior
described above. Notifications, a foreground service, and a wake lock support
the optional background Bluetooth/LAN bridge, not a cloud push service.

Saved preferences remain until you change/delete them or clear the app's storage.
Android backup/device-transfer services may include these preferences, including
profiles and pairing credentials, depending on your device and backup settings;
the app currently supplies no custom backup exclusions. Check Android's backup
settings. Clearing local storage does not necessarily remove an existing system
backup, browser data, or information held by Google or your speech provider.

You can deny optional permissions, avoid the relevant features, clear the Droid
Lab's session log, clear app storage in Android settings, and stop the dashboard
when it is not needed. Clearing app storage can erase saved routines and profiles.
Disconnecting alone is not a full data-erasure or credential-rotation operation.

If you contact the maintainer or post a GitHub issue, you choose what to share;
public issues and third-party messaging services have their own privacy rules.
Do not send passwords, pairing QR codes, or private signing keys. This notice
describes the reviewed implementation and published SDK disclosures, not a
network-capture audit or a guarantee about every device's platform services.

The About & legal screen opens GitHub and Instagram links in another app when
you select them. Those services handle your visit under their own privacy
policies. Your email app handles any message you choose to send.
