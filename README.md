# GPS Connect Android — Native starter (v0.1.0)

This is an Android Studio source project, **not a compiled APK**.

## Included
- Native Android app with two role screens: GPS Locator and GPS Viewer.
- Android runtime precise/coarse location permission request.
- Foreground location service with persistent notification.
- Fused Location Provider GPS updates every ~5 seconds.
- Stops location service when user taps Stop.

## Not yet implemented
- Remote device pairing and live map receiver.
- WebRTC data transport and automatic signaling.
- Background-location permission flow for Android versions/policies that require it.
- Production signing, testing, and Play distribution.

**Do not treat this build as a working remote tracker.** It can acquire GPS fixes on the Locator phone, but it does not yet transmit them to the Viewer. Phones on separate networks require a signaling mechanism to establish a peer connection; GPS payloads can then travel directly peer-to-peer.

## Build APK
1. Open this folder in Android Studio (Giraffe or newer).
2. Allow Gradle sync and install Android SDK Platform 35 if prompted.
3. Build > Build Bundle(s) / APK(s) > Build APK(s).
4. Debug APK output: `app/build/outputs/apk/debug/app-debug.apk`.

The build requires internet for Gradle dependencies and Google Play Services Location.

## Build APK using GitHub Actions (no local Android Studio required)
1. Create a new GitHub repository and upload the contents of this project.
2. Open the repository's Actions tab.
3. Select **Build GPS Connect APK** and click **Run workflow**, or push to `main`.
4. When the workflow completes, open the run and download the `GPS-Connect-debug-apk` artifact.
5. Extract the artifact ZIP and install `app-debug.apk` on your Android phone.

This workflow builds a debug APK. It does not add the missing remote P2P/signaling or Viewer map functionality.
