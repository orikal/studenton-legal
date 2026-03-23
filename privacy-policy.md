# Privacy Policy — Studenton

**Effective Date:** March 23, 2026  
**Last Updated:** March 23, 2026

This Privacy Policy describes how **Studenton** ("we", "our", or "us") collects, uses, stores, and protects the personal information of users ("you") of the Studenton mobile application ("App").

By using the App you agree to the practices described in this policy. If you do not agree, please discontinue use of the App.

---

## 1. Who We Are

Studenton is a student-organizer mobile application developed and operated by **Ori** (contact: **privacy@studenton.app**).  
The App is available on iOS via the Apple App Store.

---

## 2. Information We Collect

### 2.1 Account & Identity Information
When you create an account or sign in, we collect:
- **Email address** — used to identify your account and send account-related communications.
- **Display name** — the name you choose to show within the App.
- **Authentication tokens** — securely stored on your device via iOS Keychain (expo-secure-store) to keep you signed in.

If you sign in with **Google**, we receive your email address and name from Google in accordance with Google's privacy policy. We do not receive or store your Google password.

### 2.2 Academic & Usage Data
All academic data you enter is stored in your personal account in our database:
- **Courses**: name, course code, credits, academic year, semester, final grade, color label.
- **Exams**: course link, title, date, time, location, notes.
- **Assignments**: title, course link, due date, status, notes.
- **Schedule slots**: day, start/end times, location, notes.
- **Grade entries**: label, score, maximum score, weight, date recorded.
- **Study sessions**: start time, end time, duration, study mode, linked course.
- **Study statistics**: streak (consecutive study days), total points, level, total study time.
- **Questions**: prompts, answer choices, correct answer, difficulty, source course.

### 2.3 Profile Settings (Stored Locally on Your Device)
The following preferences are stored **only on your device** and are never transmitted to our servers:
- Full name, age, city, degree program, institution, and academic year (entered in Settings).
- Profile photo — stored on your device only and never uploaded.
- Cached practice materials (PDF/Word files and Google Drive links you save per course).
- Scheduled notification identifiers for assignment reminders.

### 2.4 Institution Reference Data
We maintain a reference list of academic institutions and their semester calendars. This data is read-only and contains no personal information.

### 2.5 Device & Technical Data
We do not collect device identifiers, IP addresses, or usage analytics. The App does not include any analytics or advertising SDKs.

---

## 3. How We Use Your Information

We use the information we collect solely to:

| Purpose | Legal Basis |
|---------|-------------|
| Provide core App functionality (syncing your courses, exams, assignments, grades, study sessions across sessions) | Contract performance |
| Authenticate your identity and maintain your session | Contract performance |
| Send **local** push notifications for upcoming assignment deadlines (scheduled on-device, no data leaves the device) | Legitimate interest / your consent |
| Improve and maintain the App's reliability | Legitimate interest |

We **do not** use your data for advertising, profiling, or selling to third parties.

---

## 4. Third-Party Services

### 4.1 Supabase
We use **Supabase** (Supabase Inc.) as our backend infrastructure for database storage and authentication. Your data is stored on servers located in the **European Union (Frankfurt, Germany — eu-central-1 region)**.

Supabase's privacy policy: https://supabase.com/privacy

### 4.2 Google Sign-In
If you choose to sign in with Google, the authentication is handled via Google's OAuth 2.0 service. We only receive your email address and display name. Google may collect additional information as described in their privacy policy: https://policies.google.com/privacy

### 4.3 Apple App Store
The App is distributed through the Apple App Store. Apple may collect certain information as described in Apple's privacy policy: https://www.apple.com/legal/privacy/

---

## 5. Data Retention

- Your account data is retained for as long as your account is active.
- If you delete your account, all data associated with your account will be permanently deleted from our servers within **30 days**.
- Locally stored data (profile details, photos, practice materials) remains on your device until you uninstall the App or clear app data.

---

## 6. Data Security

We implement industry-standard security measures:
- All data in transit is encrypted using **TLS/HTTPS**.
- Authentication tokens are stored in the **iOS Keychain** (via expo-secure-store), not in plain-text storage.
- Our database enforces **Row Level Security (RLS)** policies, ensuring each user can only access their own data.
- We do not store passwords — they are managed by Supabase's authentication service using bcrypt hashing.

---

## 7. Children's Privacy

The App is not directed at children under the age of **13** (or the applicable minimum age in your jurisdiction). We do not knowingly collect personal information from children. If you believe a child has provided us with personal information, please contact us at **privacy@studenton.app** and we will delete it promptly.

---

## 8. Your Rights

Depending on your jurisdiction, you may have the following rights regarding your personal data:

- **Access**: Request a copy of the data we hold about you.
- **Rectification**: Request correction of inaccurate data.
- **Erasure ("Right to be Forgotten")**: Request deletion of your account and all associated data.
- **Portability**: Request your data in a machine-readable format.
- **Objection**: Object to certain processing of your data.

To exercise any of these rights, contact us at **privacy@studenton.app**. We will respond within **30 days**.

If you are in the **European Economic Area (EEA)**, you have the right to lodge a complaint with your local data protection authority.

---

## 9. Notifications

The App uses **local notifications only** — reminders are scheduled directly on your device for assignment due dates. No notification data is transmitted to our servers or to any push notification service.

---

## 10. International Data Transfers

If you are located outside the European Union, please be aware that your data will be stored on servers within the EU (Frankfurt, Germany) in compliance with GDPR requirements.

---

## 11. Changes to This Policy

We may update this Privacy Policy from time to time. We will notify you of significant changes by updating the "Last Updated" date at the top of this page. Continued use of the App after changes constitutes your acceptance of the updated policy.

---

## 12. Contact Us

If you have questions or concerns about this Privacy Policy, or wish to exercise your data rights, please contact us:

**Email:** privacy@studenton.app  
**App:** Studenton  
**Platform:** iOS (Apple App Store)

---

*This Privacy Policy was written in plain language to help you understand how we handle your data. We are committed to protecting your privacy.*
