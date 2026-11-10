# 📱 BuyBuddy Mobile — Cross-Platform Shopping App

<p align="center">
  <img src="showcase.jpg" alt="BuyBuddy Mobile, Web, and Tablet Showcase" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/IsravelTECH/BuyBuddy/actions"><img src="https://img.shields.io/github/actions/workflow/status/IsravelTECH/BuyBuddy/build_mobile.yml?branch=main&style=for-the-badge&logo=githubactions&logoColor=white&label=Build%20APKs%20%26%20iOS" alt="Build Status"></a>
  <img src="https://img.shields.io/badge/Flutter-3.x-02569B?style=for-the-badge&logo=flutter" alt="Flutter">
  <img src="https://img.shields.io/badge/Dart-3.x-0175C2?style=for-the-badge&logo=dart" alt="Dart">
  <img src="https://img.shields.io/badge/Platforms-Android%20%7C%20iOS%20%7C%20Windows%20%7C%20Web-4285F4?style=for-the-badge" alt="Platforms">
  <img src="https://img.shields.io/badge/State-Provider-green?style=for-the-badge" alt="Provider">
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="License">
</p>

---

## 🌟 Overview

The **BuyBuddy Mobile App** is a responsive, cross-platform e-commerce client built with Flutter, Provider, and Dio. It seamlessly connects to the BuyBuddy cloud backend, featuring an ambient video hero banner, 7 rich product categories with 7 styles each, animated carousel browsing, real-time cart calculations, coupon redemption, and secure authentication.

- 🌐 **Web & Backend Repository:** [IsravelTECH/E-commerce-store](https://github.com/IsravelTECH/E-commerce-store)
- ☁️ **Live Cloud API Endpoint:** `https://e-commerce-store-anqa.onrender.com/api`
- ⚡ **Automated CI/CD Builds:** [GitHub Actions](https://github.com/IsravelTECH/BuyBuddy/actions)

---

## ✨ Features

- 👖 **7 Curated Fashion Categories**:
  - **Jeans** (7 curated styles)
  - **T-Shirts** (7 curated styles)
  - **Shoes** (7 curated styles)
  - **Glasses** (7 curated styles)
  - **Jackets** (7 curated styles)
  - **Suits** (7 curated styles)
  - **Bags** (7 curated styles)
- 🎬 **Motion / Video Hero Banner**: Clean auto-playing carousel banner with quick category discovery navigation.
- 🛒 **Full-Featured Cart**: Real-time quantity steppers, subtotal updates, and coupon voucher discounts (`SAVE20`).
- 🔐 **Persistent Authentication**: Secure JWT token storage using `flutter_secure_storage`.
- 🎨 **Modern Light-Theme UI/UX**: Designed with crisp typography, smooth card elevation, responsive padding, and the BuyBuddy brand palette (`#2563EB`).
- 🤖 **Automated GitHub Actions CI/CD**: Automatically compiles Android APKs (Debug & Release) and iOS packages on every push.

---

## 📁 Project Structure

```text
mobile/
│
├── .github/
│   └── workflows/
│       └── build_mobile.yml    # CI/CD pipeline for Android APK & iOS build
│
├── android/                    # Native Android project configuration & Gradle
├── ios/                        # Native iOS Xcode workspace & project configuration
│
├── assets/
│   ├── images/
│   │   ├── categories/         # High-definition images for all 7 categories
│   │   │   ├── jeans/
│   │   │   ├── t-shirts/
│   │   │   ├── shoes/
│   │   │   ├── glasses/
│   │   │   ├── jackets/
│   │   │   ├── suits/
│   │   │   └── bags/
│   │   └── showcase.jpg        # Multi-device showcase banner
│   └── icons/                  # Custom BuyBuddy launcher & app icons
│
├── lib/
│   ├── core/
│   │   ├── constants.dart      # Colors, typography, and API URLs
│   │   └── api_service.dart    # Dio client with JWT authentication interceptors
│   ├── data/
│   │   └── models.dart         # User, Product, CartItem, Coupon models
│   ├── providers/
│   │   ├── auth_provider.dart  # User sign-in, registration, and session state
│   │   ├── product_provider.dart # Catalog fetching & category filtering
│   │   └── cart_provider.dart  # Cart synchronization, quantities & coupons
│   ├── views/
│   │   ├── auth/               # Login, Sign-up & Profile screens
│   │   ├── cart/               # Cart, Voucher redemption, Order summary
│   │   ├── category/           # Category-filtered product catalog
│   │   ├── home/               # Hero banner, category pills, product grid
│   │   │   └── widgets/        # VideoHeroBanner, CategoryCard, etc.
│   │   └── shell_screen.dart   # Bottom navigation shell
│   └── main.dart               # App root, MultiProvider & MaterialApp setup
│
├── test/
│   └── widget_test.dart        # Unit and data model test suite
│
├── build_apk.ps1               # Local helper script to build debug APK
├── run_web.ps1                 # Local helper script to run in Chrome
├── run_windows.ps1             # Local helper script to run on Windows Desktop
├── showcase.jpg                # Multi-device mockup preview image
├── pubspec.yaml                # Flutter dependencies & asset declarations
└── README.md
```

---

## 🚀 How to Run the Project Locally

### 📋 Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install) (v3.22+ recommended)
- [Dart SDK](https://dart.dev/get-dart) (included with Flutter)
- [Android Studio](https://developer.android.com/studio) (with Android SDK & Command-line Tools) or VS Code with Flutter extension
- [Git](https://git-scm.com/)

---

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/IsravelTECH/BuyBuddy.git
cd BuyBuddy
```

---

### 2️⃣ Install Flutter Dependencies

```bash
flutter pub get
```

---

### 3️⃣ Run on Your Preferred Device

#### Option A: Run on Android (Physical Device or Emulator)
Make sure your phone is connected with USB Debugging enabled, or start an Android Emulator:
```bash
flutter run
```

#### Option B: Run on Windows Desktop
```bash
flutter run -d windows
```
*(Or run `.\run_windows.ps1` in PowerShell)*

#### Option C: Run in Google Chrome (Web)
```bash
flutter run -d chrome --web-browser-flag "--disable-web-security"
```
*(Or run `.\run_web.ps1` in PowerShell)*

---

## 📦 How to Build the APK File Locally

### 🔹 Build Debug APK (Fastest, Installs Instantly)
```bash
flutter build apk --debug
```
- **Output File:** `build/app/outputs/flutter-apk/app-debug.apk`
- *(Or run `.\build_apk.ps1`)*

### 🔹 Build Release APK (Optimized & Minified)
```bash
flutter build apk --release
```
- **Output File:** `build/app/outputs/flutter-apk/app-release.apk`

### 🔹 Build App Bundle (For Google Play Console)
```bash
flutter build appbundle
```
- **Output File:** `build/app/outputs/bundle/release/app-release.aab`

---

## 🤖 Automatic Builds via GitHub Actions (CI/CD)

Every time code is pushed to the `main` branch, GitHub Actions automatically:
1. Runs code quality checks (`flutter analyze`).
2. Runs unit tests (`flutter test`).
3. Compiles both `BuyBuddy-debug.apk` and `BuyBuddy-release.apk`.
4. Compiles the iOS app (`BuyBuddy-iOS-unsigned.ipa`).
5. Publishes the compiled files as downloadable artifacts!

### 📥 How to Download and Install the APK from GitHub Actions:

1. Open the [BuyBuddy Actions Tab](https://github.com/IsravelTECH/BuyBuddy/actions).
2. Click on the latest workflow run with a green checkmark (e.g., *Fix Android build...*).
3. Scroll down to the **Artifacts** section at the bottom of the page.
4. Click on **BuyBuddy-Android-APKs** to download `BuyBuddy-Android-APKs.zip`.
5. **Important for Phone Installation**:
   - Transfer or download the `.zip` file onto your Android phone.
   - **Extract / Unzip** the `.zip` file using your phone's built-in Files app, ZArchiver, or RAR.
   - Tap directly on `BuyBuddy-debug.apk` (or `BuyBuddy-release.apk`) to install!
   > *Note: Android's package installer cannot read APK files directly inside a ZIP archive; unzipping first ensures proper installation.*

---

## 🌐 Backend Configuration

By default, the mobile app is configured to communicate with the live cloud backend:
- `lib/core/constants.dart`:
  ```dart
  static const String apiBaseUrl = 'https://e-commerce-store-anqa.onrender.com/api';
  ```

If you wish to test with a locally running Express server on your machine:
- **Android Emulator:** Use `http://10.0.2.2:5000/api`
- **Physical Device:** Use your computer's local Wi-Fi IP `http://192.168.x.x:5000/api`
- **Windows / Web:** Use `http://localhost:5000/api`

---

## 🧪 Testing & Code Quality

Run tests and static analysis:
```bash
flutter analyze
flutter test
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
