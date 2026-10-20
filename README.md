# PulseHook

PulseHook is an Android digital-wellbeing app that helps you put limits on time spent in selected social apps. 
It monitors daily use of Instagram and TikTok, then shows a reminder screen when your configured limit is reached.
<img width="222" height="411" alt="image" src="https://github.com/user-attachments/assets/5618054b-4923-420e-a544-77ea74e72781" />
## Why PulseHook?

- Choose whether to monitor Instagram, TikTok, or both.
- Set a daily limit from 5 to 120 minutes and view today's tracked usage.
- Add personal goals that appear on the reminder screen.
- Take a short Sudoku break to snooze blocking for 10 minutes.
- Optionally enable a grayscale reward effect during the snooze period.
- Resume monitoring after a device reboot when the blocker is enabled.

The app uses Android's Usage Stats and a foreground service for monitoring. Usage and goals are stored in the app's local preferences.
<img width="210" height="354" alt="image" src="https://github.com/user-attachments/assets/cf03065f-b9eb-4cd0-a373-2c342c0fe4da" />
<img width="216" height="431" alt="image" src="https://github.com/user-attachments/assets/f04c3c34-cdbc-47eb-9aea-57953e79e85f" />

## Get started

### Requirements

- Android Studio with Android SDK 36 installed
- JDK 17
- An Android device or emulator running Android 8.0 (API 26) or later

### Build and install

Clone the repository, open its root directory in Android Studio, and let Gradle sync. Or build and install the debug app from a terminal:

```powershell
.\gradlew.bat assembleDebug
.\gradlew.bat installDebug
```

The APK is written to `app/build/outputs/apk/debug/app-debug.apk`.

### Configure the app

1. Launch **PulseHook**.
2. Select Instagram and/or TikTok and set a daily limit.
3. Tap **Check Permissions** and enable **Usage access** and **Display over other apps** for PulseHook in Android Settings.
4. Turn on **PulseHook Active** to start monitoring.
5. Optionally add goals to show on the reminder screen.

Grayscale requires Android's restricted `WRITE_SECURE_SETTINGS` permission. On a development device with USB debugging enabled, grant it from a computer with ADB:

```powershell
adb shell pm grant com.temir.instalocker android.permission.WRITE_SECURE_SETTINGS
```

This is optional; usage monitoring and blocking do not depend on grayscale. You can revoke the permission with `adb shell pm revoke com.temir.instalocker android.permission.WRITE_SECURE_SETTINGS`.

### Gemini integration status

The project contains a Gemini helper, but its API key is currently a placeholder and the app does not declare network access. As checked out, reminder text uses its built-in fallback. Do not commit a real API key to source control; configure credentials and network access using an appropriate secure approach before enabling remote Gemini requests.

## Help and documentation

- For Android setup and permission details, see the [Android developer documentation](https://developer.android.com/).
- Report bugs or ask for help in the **Issues** section of the repository where you obtained this project.
- Project-specific documentation is not currently included in the repository.

## Maintainers and contributing

No maintainer contact or contribution guide is specified in the project files. Contact the repository owner or maintainers through the hosting repository's issue tracker.

Contributions are welcome. Please submit a focused pull request with a clear description of the change and any relevant testing details. Before submitting, run:

```powershell
.\gradlew.bat assembleDebug
```

There is no project `CONTRIBUTING.md` or `LICENSE` file in this checkout. Check with the repository maintainers for contribution policies and licensing information.
