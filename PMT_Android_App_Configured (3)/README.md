# PMT Material Management - Android WebView App

This Android project wraps the existing PMT Google Apps Script web application. It keeps the existing HTML frontend and Google Sheets / Apps Script backend, including login, materials, inward, stock search, dispatch, reports, photos, imports, audit, users and admin controls.

## 1. Set the Web App URL

Open:
`app/src/main/java/com/perfectmarktechnology/materialmanagement/MainActivity.kt`

Replace:
`https://script.google.com/macros/s/AKfycbwIsGTJLQLRv7XU0IAbQXWtSQB_OYPSP6JB_8MYRW5je2pJe1Eo2LenDuwax8S7njsQvQ/exec`

with the deployed Apps Script Web App URL, for example:
`https://script.google.com/macros/s/XXXXXXXXXXXX/exec`

## 2. Build

Open the folder in Android Studio and let Gradle sync. Then run on an Android phone or emulator.

For a debug APK use Android Studio's Build > Build APK(s).

## 3. Apps Script deployment

Deploy the Apps Script project as a Web app. The deployment must be accessible to the intended users. The Android app does not bypass Apps Script authentication or permissions; it uses the same web application.

## 4. Important behavior

- Username/password login remains required by the existing web app.
- No automatic login credentials are added by this wrapper.
- JavaScript and DOM storage are enabled because the existing frontend uses `google.script.run`.
- File selection is enabled for Excel/photo uploads.
- Camera permission is requested because the web application may use photo capture.
- Android back button navigates inside the web app before closing the app.
