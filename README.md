# Privacy Policy & Data Safety

**Effective Date:** August 31, 2026  
**Last Updated:** August 31, 2026

---

## 1. Core Privacy Philosophy: 100% Local & Offline-First

This application is designed with a **Zero-Knowledge, Offline-First** privacy architecture.

- **No Remote Telemetry or Tracking:** The application does not collect, log, transmit, sell, or share personal data, analytics, crash logs, or advertising identifiers.
- **No External Servers:** All features—including the Password Manager, Private Vault, Distraction App Blocker, and Security Audit—operate entirely on the user's local device.
- **No Third-Party Tracking SDKs:** The application does not include third-party marketing, analytics, advertising, or user-profiling libraries.

---

## 2. Information Handled & Local Storage

| Data Category | Purpose | Storage & Protection |
|---|---|---|
| **Passwords & Credentials** | Storing normal and restricted account credentials. | Stored in a local encrypted database protected using **Android KeyStore** and AES-256 encryption. |
| **Vault Files & Media** | Keeping user-selected files, photos, or documents secure. | Stored exclusively inside the application's isolated sandbox storage and encrypted before being written to disk. |
| **Distraction Rules & Schedules** | Managing blocked apps, time windows, and focus schedules. | Stored locally in on-device application storage/database (`AppDatabase`). |
| **Biometric & Master Credentials** | Authenticating user access to sensitive sections. | Authentication is handled by Android's hardware-backed **BiometricPrompt / TEE (Trusted Execution Environment)**. The application never accesses, stores, or transmits raw biometric templates. |

---

## 3. Permissions & Transparent Usage

### A. Accessibility Service — `DistractionBlockAccessibilityService`

**Purpose:**  
The Accessibility Service is used strictly to detect when a user-configured distraction application is launched in the foreground while a focus schedule or blocking rule is active.

**Non-Collection Guarantee:**

The Accessibility Service does **not** read or collect:

- Screen text
- Keystrokes
- Personal messages
- Passwords
- Form contents
- Browsing history
- User inputs
- Other personal content displayed inside applications

It is used only to monitor **foreground application/package changes** so that the application can trigger the configured blocking overlay when required.

---

### B. Display Over Other Apps / System Alert Window — `BlockOverlayManager`

**Purpose:**  
This permission allows the application to display a blocking overlay when a restricted application is launched during an active focus-blocking session.

The overlay is used solely for the application's distraction-blocking functionality.

---

### C. Storage & Media Access — `VaultStorageManager`

**Purpose:**  
Allows users to select and import files or documents into the secure private vault and export them back to device storage when explicitly requested.

Files imported into the vault are encrypted before being written to the application's protected storage.

---

### D. Run at Startup — `BootCompletedReceiver`

**Purpose:**  
Allows the application to restore active focus schedules and re-establish configured distraction-blocking rules after the device restarts.

---

### E. Biometrics & Device Credentials

**Purpose:**  
Provides secure PIN and biometric authentication for accessing restricted passwords and encrypted vault folders.

The application relies on Android's secure authentication mechanisms and does not access or store raw biometric data.

---

## 4. Data Transmission & Third-Party Sharing

### No Data Transmission

The application is designed to operate entirely offline.

User data is **not transmitted to remote servers**, including:

- Passwords
- Credentials
- Vault files
- Photos
- Documents
- Focus schedules
- Blocked-app rules
- Authentication information

### No Third-Party Data Sharing

The application does not sell, rent, or share user data with third parties for:

- Advertising
- Analytics
- Marketing
- Profiling
- Behavioral tracking

---

## 5. Data Security

The application uses multiple layers of on-device security, including:

- **Android KeyStore**
- **Hardware-backed authentication where supported**
- **AES-256 encryption**
- **Android application sandboxing**
- **BiometricPrompt / device credential authentication**
- Local-only data processing

Security mechanisms may vary depending on the capabilities of the user's Android device.

---

## 6. Data Deletion

Users maintain control over their locally stored data.

Data can be permanently removed by deleting the relevant records/files through the application or by uninstalling the application.

When the application is uninstalled, Android removes the application's private sandbox data. Encryption keys stored in Android KeyStore are also managed by the Android operating system.

> **Important:** Users should export any data they want to retain before uninstalling the application.

---

## 7. Google Play Data Safety

If this application is published on the **Google Play Store**, the Google Play Console Data Safety form should be completed based on the application's actual implementation and Google's current definitions.

Based on the architecture described in this document:

### Does the app collect or share user data?

**No**, provided that the implementation does not contain any code or SDK that collects or transmits user data.

### Is user data encrypted in transit?

**Not applicable to locally stored data that never leaves the device.**

If the application does not transmit user data over a network, there is no user-data transmission requiring encryption in transit.

### Can users request deletion of their data?

**Yes.**

Users can delete locally stored application data through the application where supported, or remove the application's local data by uninstalling the application.

> **Note:** Google Play's Data Safety declarations must accurately reflect the application's actual code, permissions, SDKs, and behavior. The declarations above should be verified against the final production build before submitting the application.

---

## 8. Privacy & Security Commitment

> ### Your Privacy Comes First
>
> This application is designed to keep your data on your device.
>
> - **Zero Tracking:** No advertising, analytics, or remote tracking.
> - **Offline-First:** Core functionality operates locally without external servers.
> - **Encrypted Security:** Passwords and vault files are encrypted locally using strong encryption and Android KeyStore protection.
> - **Ethical Accessibility Use:** The Accessibility Service is used only to detect foreground applications for scheduled distraction blocking. It does not read keystrokes, screen contents, messages, or personal information.
> - **No Third-Party Data Sharing:** User data is not sold or shared for advertising, analytics, or profiling.
> - **User Control:** Users can permanently delete their locally stored application data.

---

## 9. Scope

This privacy policy applies to the Android application and its locally processed data.

The policy should be updated if future versions introduce:

- Cloud synchronization
- Remote servers or APIs
- Analytics
- Crash reporting
- Advertising
- Third-party SDKs
- Account-based services
- Online backups
- Any other functionality that transmits user data outside the device

If any such functionality is introduced, this privacy policy and the Google Play Data Safety declaration should be updated accordingly.

---

**Last Updated:** August 31, 2026
