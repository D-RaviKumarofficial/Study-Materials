# Flutter Setup & Installation Guide (Windows)

## 1. Install Visual Studio Code

Download and install Visual Studio Code:

* https://code.visualstudio.com/

---

# 2. Install Flutter & Dart Extensions

1. Open **Visual Studio Code**.
2. Click **Extensions** (`Ctrl + Shift + X`).
3. Search for **Flutter**.
4. Install the **Flutter** extension.
5. The **Dart** extension will be installed automatically (or install it manually if needed).

---

# 3. Download Flutter SDK

Download the latest Flutter SDK from the official website:

https://docs.flutter.dev/get-started/install/windows

Extract the downloaded ZIP file to:

```text
C:\src\flutter
```

The final folder structure should look like:

```text
C:\
 └── src
      └── flutter
```

> **Note:** Avoid installing Flutter inside `Program Files` or folders containing spaces.

---

# 4. Configure Environment Variables

Add the following directory to the Windows **Path** environment variable:

```text
C:\src\flutter\bin
```

### Verify

Open a new Command Prompt and run:

```bash
flutter --version
```

or

```bash
flutter doctor
```

---

# 5. Install Android Studio

Download Android Studio:

https://developer.android.com/studio

During installation, ensure the following components are selected:

* ✅ Android SDK
* ✅ Android SDK Platform
* ✅ Android SDK Platform-Tools
* ✅ Android SDK Build-Tools
* ✅ Android SDK Command-line Tools (Latest)
* ✅ Android Emulator
* ✅ Android Virtual Device (AVD)

After installation:

1. Open **Android Studio**.
2. Complete the first-time setup wizard.
3. Allow it to download all required SDK components.

---

# 6. Accept Android Licenses

Run:

```bash
flutter doctor --android-licenses
```

Press:

```text
y
```

for every license.

---

# 7. Verify Installation

Run:

```bash
flutter doctor -v
```

A successful installation should show:

```text
[✓] Flutter
[✓] Android toolchain
[✓] Chrome
[✓] Visual Studio
[✓] Connected device
```

---

# 8. Connect an Android Phone

On your Android device:

* Enable **Developer Options**
* Enable **USB Debugging**

Connect the phone using a **USB data cable**.

If prompted:

```
Allow USB Debugging?
```

Select:

* ✅ Always allow from this computer
* ✅ Allow

---

# 9. Check Connected Devices

```bash
flutter devices
```

Example:

```text
Found 2 connected devices

SM-A546E (mobile)
Windows (desktop)
```

---

# 10. Create a New Flutter Project

```bash
flutter create my_app
```

Example:

```bash
flutter create interview_prep_app
```

---

# 11. Open the Project

```bash
cd interview_prep_app
```

Open it in VS Code:

```bash
code .
```

---

# 12. Run the Flutter Application

Run on the default connected device:

```bash
flutter run
```

Run on a specific device:

```bash
flutter run -d windows
```

```bash
flutter run -d chrome
```

```bash
flutter run -d <device_id>
```

---

# 13. Build APK

Debug APK

```bash
flutter build apk
```

Release APK

```bash
flutter build apk --release
```

APK Location

```text
build\app\outputs\flutter-apk\
```

---

# 14. Clean Project

```bash
flutter clean
```

Removes:

* Build cache
* Generated files
* Temporary files

Useful after dependency or configuration changes.

---

# 15. Get Packages

```bash
flutter pub get
```

Downloads all dependencies listed in `pubspec.yaml`.

---

# 16. Upgrade Packages

```bash
flutter pub upgrade
```

Updates dependencies to newer compatible versions.

---

# 17. Update Flutter SDK

```bash
flutter upgrade
```

Updates Flutter to the latest stable version.

---

# 18. Check Flutter Version

```bash
flutter --version
```

Displays:

* Flutter Version
* Dart Version
* Engine Version

---

# 19. Check Flutter Installation

```bash
flutter doctor
```

Checks:

* Flutter SDK
* Android SDK
* Chrome
* Visual Studio
* Connected Devices

---

# 20. Detailed Installation Report

```bash
flutter doctor -v
```

Shows:

* SDK Paths
* Android Toolchain
* Device Details
* Versions
* Environment Information

---

# 21. List Connected Devices

```bash
flutter devices
```

Displays:

* Android phones
* iOS devices
* Windows
* Chrome
* Edge
* Linux
* macOS

---

# 22. List Available Emulators

```bash
flutter emulators
```

Shows all installed Android emulators.

---

# 23. Launch an Emulator

```bash
flutter emulators --launch <emulator_id>
```

Example:

```bash
flutter emulators --launch Pixel_9_API_36
```

---

# 24. Install Dependencies

Whenever you clone a Flutter project:

```bash
flutter pub get
```

---

# 25. Analyze Code

```bash
flutter analyze
```

Checks for:

* Errors
* Warnings
* Lint issues

---

# 26. Format Source Code

Format a specific file:

```bash
dart format lib/main.dart
```

Format the entire project:

```bash
dart format .
```

---

# 27. Run Tests

```bash
flutter test
```

Runs all unit and widget tests.

---

# 28. View Installed Flutter Configuration

```bash
flutter config
```

Shows the current Flutter configuration.

---

# 29. Set Android SDK Path

If Flutter cannot find the Android SDK:

```bash
flutter config --android-sdk "C:\Users\<YourUser>\AppData\Local\Android\Sdk"
```

Verify:

```bash
flutter doctor
```

---

# 30. Check ADB Devices

```bash
adb devices
```

Example:

```text
List of devices attached

245a56a0    device
```

If it shows:

```text
unauthorized
```

Unlock your phone and tap **Allow USB Debugging**.

---

# 31. Restart ADB

```bash
adb kill-server
```

```bash
adb start-server
```

```bash
adb devices
```

Useful when your Android device is not detected.

---

# 32. Common Flutter Commands

| Command                               | Usage                                       |
| ------------------------------------- | ------------------------------------------- |
| `flutter doctor`                      | Checks Flutter installation                 |
| `flutter doctor -v`                   | Detailed installation report                |
| `flutter devices`                     | Lists connected devices                     |
| `flutter emulators`                   | Lists available emulators                   |
| `flutter run`                         | Runs the application                        |
| `flutter create project_name`         | Creates a new project                       |
| `flutter clean`                       | Cleans build files                          |
| `flutter pub get`                     | Downloads project dependencies              |
| `flutter pub upgrade`                 | Updates dependencies                        |
| `flutter build apk`                   | Builds a debug APK                          |
| `flutter build apk --release`         | Builds a release APK                        |
| `flutter upgrade`                     | Updates Flutter SDK                         |
| `flutter analyze`                     | Analyzes project code                       |
| `flutter test`                        | Runs tests                                  |
| `flutter config`                      | Displays Flutter configuration              |
| `flutter config --android-sdk <path>` | Sets Android SDK path                       |
| `flutter --version`                   | Displays Flutter version                    |
| `flutter doctor --android-licenses`   | Accepts Android SDK licenses                |
| `adb devices`                         | Lists Android devices connected through ADB |
| `adb kill-server`                     | Stops the ADB server                        |
| `adb start-server`                    | Starts the ADB server                       |
| `code .`                              | Opens the current folder in VS Code         |

---

# 33. Recommended Folder Structure

```text
C:\
│
├── src
│   └── flutter
│
├── Users
│   └── <YourUser>
│       └── AppData
│           └── Local
│               └── Android
│                   └── Sdk
│
└── Projects
    ├── InterviewPrepApp
    ├── FlutterDemo
    └── PortfolioApp
```

Following this setup ensures Flutter, Android Studio, the Android SDK, and ADB are configured correctly for developing and running Flutter applications on Windows, Android devices, and emulators.
