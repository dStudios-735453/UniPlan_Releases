# Privacy Policy

**Last updated: June 2, 2026**

## 1. DATA UniPlan COLLECTS AND STORES

### 1.1 Data You Provide

UniPlan stores the following data locally on your device and, if you enable cloud sync, on Firebase Firestore:

- **Account Information**: If you create an account, Firebase stores your email address and a salted hash of your password (via Firebase Authentication). You may also sign in with Google or Apple, in which case Firebase receives your email address and profile information from Google or Apple.
- **Class Schedule**: Class names, times, locations, teachers, room numbers, colors, recurrence patterns, and daily notes you create (encrypted with aes-256 on Firestore, sent only with sync on).
- **Homework & Todo Items**: Assignment descriptions, due dates, due times, checklist items, page numbers, completion status, pinned status, and notification settings (encrypted with aes-256 on Firestore, sent only with sync on).
- **App Settings**: Theme preferences, tab order, language selection (English/German/Romanian), default lesson/break durations, subject and teacher presets, autofill configurations, manual holidays, and vacation mode settings (encrypted with aes-256 on Firestore, sent only with sync on).
- **School Integration Credentials**: If you connect to Schulmanager or Adservio, UniPlan stores your username and password.
- **User PIN**: A PIN you set for encrypting your data is stored in the device's Secure Enclave (iOS Keychain / Android Keystore) on mobile. On desktop, the encryption key is stored via the platform's standard storage. The PIN itself is never stored or sent to Firestore in plaintext.

### 1.2 Data Collected Automatically

- **Calendar Events**: With your permission, UniPlan reads events from your device's calendar to display them alongside your schedule. On iOS this is read-only access. Event titles and locations may be synced to Firestore in encrypted form if cloud sync is enabled.
- **Analytics Events**: UniPlan uses Firebase Analytics to collect anonymous usage data, including screen views, user engagement, and specific actions (adding, editing, or deleting schedule items, homework, and todos). No personally identifiable data is included — only event names and basic engagement metrics. Ad ID collection is disabled.
- **Error and Performance Data**: UniPlan uses Sentry (sentry.io) to collect error reports, performance traces, and session replay data. On mobile, this captures native screen recordings; on desktop/web, it captures page interactions (clicks, scrolls, navigation). Data includes device model, OS version, stack traces, and navigation timing. IP addresses may be collected. Sentry data is used solely to improve app stability and performance.
- **Device Information**: The app generates a random device ID for calendar sync coordination. No personal device identifiers (IMEI, serial numbers, etc.) are collected.

### 1.3 In-App Purchase Data

If you purchase a premium subscription or lifetime access:

- **Purchase Information**: When you make a purchase, the transaction is processed by the platform's app store (Apple App Store or Google Play Store). UniPlan uses RevenueCat to manage and verify subscriptions. RevenueCat receives your app user ID, purchase receipts, and subscription status.
- **Subscription Status**: Your subscription status (active/inactive, plan tier, expiration date) is stored locally and, if signed in, associated with your Firebase account via custom claims for cross-device sync.
- **No Payment Data**: UniPlan does not collect, store, or process credit card numbers or other payment information. All payment processing is handled by the app store platform.

### 1.4 School Integration Data

If you connect third-party school platforms:

- **Schulmanager (Germany)**: UniPlan fetches your lesson schedules, substitutions, class hour definitions, and holiday data from Schulmanager Online.
- **Adservio (Romania)**: UniPlan fetches your grades, absences, averages, subjects, class info, and academic periods from Adservio.
- This data is stored locally and never sent to Firebase, regardless of cloud sync settings.

## 2. HOW UniPlan STORES AND PROCESSES DATA

### 2.1 Local Storage

- **Primary Storage**: All your data is persisted on-device using React Native AsyncStorage. This includes schedules, homework, todos, settings, and integration data.
- **Secure Storage**: Your encryption Master Key and certain authentication tokens are stored in expo-secure-store, which uses the platform's hardware-backed secure storage (iOS Keychain, Android Keystore).
- **Desktop (Tauri)**: On desktop builds, storage is handled via AsyncStorage (mapped to the browser's local storage context within the Tauri webview).

### 2.2 Cloud Storage (Optional)

Cloud sync is **opt-in** and disabled by default. When enabled:

- Data is synchronized with Firebase Firestore under the collection path `users/{uid}/data/{category}/items/{itemId}`. Adservio and Schulmanager data is never sent to Firebase.
- **All data is encrypted client-side** using AES-256 (via crypto-js) with a Master Key derived from your PIN before it leaves your device.
- The Master Key itself is encrypted with your PIN (SHA-256 of PIN as AES key) and backed up to your Firestore document for recovery.
- Settings (excluding deviceId and integration credentials) are also synced when cloud sync is enabled.

### 2.3 Calendar Data

With your permission:

- UniPlan uses `expo-calendar` to read events from your selected calendars.
- Events are fetched for a range of 7 days past to 30 days future.
- One device can be designated as the "Calendar Source" — it encrypts and pushes calendar events to Firestore so other devices can decrypt and display them.
- Calendar events are **never** stored in unencrypted form on Firestore.

## 3. THIRD-PARTY SERVICES

| Service                                | Purpose                                                     | Data Shared                                                                           |
| -------------------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Firebase (Google)**                  | Authentication, Cloud Firestore, Cloud Functions, Analytics | Email, authentication tokens, encrypted user data, anonymous analytics events         |
| **Google/Apple Sign-In**               | Account creation and login                                  | Email address, profile information (name, avatar URL)                                 |
| **Google reCAPTCHA**                   | Bot protection during login/registration                    | Browser behavior signals (anonymous)                                                  |
| **OpenHolidays API**                   | Fetching school and public holiday data                     | Country and subdivision selections                                                    |
| **Schulmanager Online**                | German school management integration                        | Your Schulmanager credentials and fetched schedule data                               |
| **Adservio**                           | Romanian school management integration                      | Your Adservio credentials and fetched grade/absence data                              |
| **Flag CDN (flagcdn.com)**             | Country flag images in settings                             | None (public image requests)                                                          |
| **GitHub (raw.githubusercontent.com)** | Desktop app update checks                                   | None (anonymous GET requests to check version)                                        |
| **Sentry (sentry.io)**                 | Error tracking and performance monitoring                   | Device information, OS version, stack traces, navigation performance data, IP address |
| **RevenueCat (revenuecat.com)**        | In-app purchase and subscription management                 | App User ID, purchase receipts, transaction identifiers, subscription status          |

## 4. DATA RETENTION AND DELETION

### 4.1 Local Data

You can delete all locally stored data at any time by:

- Uninstalling the app from your device.
- Clearing the app's data through your device settings.

### 4.2 Cloud Data

If you have cloud sync enabled and wish to delete your cloud data:

- You can delete your account through the app's settings, which removes your Firestore data and authentication record.
- You can also contact dStudios to request account deletion.

### 4.3 Analytics Data

Firebase Analytics data is retained for a limited period as per Google's data retention policies. You cannot be personally identified from analytics data.

## 5. DATA SECURITY

- **Encryption at Rest**: All cloud-synced data is AES-256 encrypted client-side before transmission.
- **Encryption in Transit**: All network communication uses TLS/SSL encryption.
- **Authentication**: Firebase Authentication handles secure credential storage and token management.
- **Secure Enclave**: Your PIN encryption key is stored in the platform's hardware-backed secure storage.
- **No Plaintext Credentials**: School integration credentials are never stored or transmitted.

## 6. CHILDREN'S PRIVACY

UniPlan is designed for students, including those under 13. UniPlan does not knowingly collect personal information from children. The app does not display targeted advertising or sell user data.

## 7. YOUR RIGHTS

Depending on your jurisdiction, you may have the right to:

- Access the personal data dStudios holds about you.
- Request correction or deletion of your data.
- Withdraw consent for calendar access at any time through your device settings.
- Export your data (available through the app's settings).

## 8. CHANGES TO THIS POLICY

We may update this Privacy Policy from time to time. Changes will be posted on this page.

## 9. CONTACT

If you have questions about this Privacy Policy, please open an issue at [github.com/dStudios-735453/UniPlan_Releases](https://github.com/dStudios-735453/UniPlan_Releases) or contact dStudios via email at david@dstudios.org.
