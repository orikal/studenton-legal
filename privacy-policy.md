# Privacy Policy — StudenTeam

**Effective Date:** April 7, 2026  
**Last Updated:** April 7, 2026

This Privacy Policy describes how **StudenTeam** ("we", "our", or "us") collects, uses, stores, and protects personal information about users ("you") of the StudenTeam mobile application ("App").

By using the App you agree to the practices described in this policy. If you do not agree, please discontinue use of the App.

This Privacy Policy should be read together with our **[Terms of Service](terms-of-service.md)**, which set rules for using the App (including forums, private messaging, tutor session coordination, and the private tutor marketplace).

---

## 1. Who We Are

StudenTeam is a student-organizer and academic community application developed and operated by **Ori**.

- **Privacy contact:** [Orikal3107@gmail.com](mailto:Orikal3107@gmail.com)  
- **General contact:** [Orikal3107@gmail.com](mailto:Orikal3107@gmail.com)

The App is distributed on **iOS** (Apple App Store) and may also be available on **Android**. This policy applies regardless of platform.

---

## 2. Information We Collect

### 2.1 Account & authentication

When you create an account or sign in, we process:

| Data | Purpose |
|------|---------|
| **Email address** | Account identity, sign-in, and essential service messages (e.g. verification). |
| **Authentication credentials** | Password-based sign-in is handled by **Supabase Auth** (passwords are hashed; we do not store plaintext passwords). |
| **Session tokens** | Stored on your device using secure storage (**expo-secure-store**, backed by the device keychain / secure hardware where available) to keep you signed in. |
| **OAuth profile data** | If you use **Sign in with Apple** or **Google**, we receive identifiers and profile elements that those providers share with us (for example name, email as permitted by the provider, and profile image URL where applicable), in line with each provider's settings and policies. |

We do **not** receive your Apple or Google account password.

### 2.2 Profile & account settings (stored with your account)

The following may be stored in our database (Supabase) and linked to your user account:

- **Display name** — shown in the App and, when you use community features, may be visible to other users (for example next to forum posts or in message threads).
- **Profile photo** — if you upload an image or use a provider profile picture we sync, the image URL or file may be stored in our systems (including file storage) and can be visible to other users where the App shows your profile in community areas or conversations.
- **Institution** — optional link to an academic institution from our reference list.
- **Account role** — for example **student** or **private tutor**, used to label content and enable tutor-related features.
- **Locale and timezone** — used to present the App appropriately (defaults may apply if not set).

### 2.3 Optional details stored only on your device

Certain extended profile fields (for example full name, age, city, degree details, study year, semester preferences, and tutor subject/course selections used in onboarding flows) are stored **locally on your device** (using **AsyncStorage**) and are **not** uploaded to our servers as part of that local profile store. Additionally, the following are stored only on your device:

- **Notification preferences** — your choices for sounds, notifications, and alerts.
- **Assignment notification IDs** — scheduled local notification identifiers mapped to your assignments.
- **Reported content cache** — which posts, replies, or reviews you have already reported (to prevent duplicate reports).
- **Avatar images** — profile photo URIs you select are stored locally, though if you use OAuth providers (Google/Apple), your provider profile picture URL may be synced to our servers.

If you separately choose to publish information in the forum or tutor listings, or send it in a private message, that content is stored on our servers as described below.

### 2.4 Academic & organizer data (your account, cloud-synced)

Data you enter into organizer features is stored in your account on our backend so it can sync across devices. This includes, depending on what you use:

- **Courses** — name, code, credits, year, semester, grades, labels, etc.
- **Exams** — titles, dates, times, locations, notes, links to courses.
- **Assignments** — titles, due dates, status, notes, course links.
- **Schedule** — slots, times, locations, notes.
- **Grades** — entries, weights, scores, dates.
- **Study sessions** — timing, duration, mode, linked courses.
- **Gamification / stats** — for example streaks, points, levels associated with your account.
- **Practice / questions** — content you create for self-study (prompts, answers, difficulty, course links), where you use those features.

### 2.5 Community forum & user-generated content

If you use the **forum** or related features, we store content you submit on our servers, including:

- **Posts and replies** — text, images (PNG, JPG, GIF), and file attachments (PDF, Word, Excel, PowerPoint, and other document formats) you upload.
- **Metadata** — subject/course association, post type (question, tip, summary, resource, discussion), timestamps, moderation status, reply counts, and similar fields required to operate the forum.
- **Tutor marketplace listings** — posts intended to connect students and private tutors (for example offers or requests); may include descriptive text, pricing indications you type (in NIS), teaching mode (in-person/online), and attachments you choose to upload.
- **Forum reports** — when you report content as inappropriate, we store the report record (reporter ID, reported content ID, reason, timestamp) for moderation purposes. These are accessible only to app administrators and service-role access.
- **Forum moderation metadata** — including warning counts, blocked status, and admin flags on user profiles.

Forum content you publish may be **visible to other users** of the App according to how the feature is designed (for example by subject or listing type). Your **display name** and **profile image** (if any) may appear alongside your content.

**IMPORTANT: Files uploaded to the forum (images and documents) and tutor profile documents (CV/certifications) are stored in public storage buckets on Supabase Storage**, which means they are **accessible by anyone with the direct URL**. Do not upload sensitive personal information, passwords, or confidential documents unless you intend them to be publicly accessible.

We process forum submissions through **Supabase Edge Functions** (`forum-submit`) with the following optional safety features:

- **OpenAI text moderation** — When enabled (`FORUM_USE_OPENAI_MODERATION=true`), forum post and reply text is analyzed by **OpenAI's Moderation API** to detect policy violations (hate speech, violence, sexual content, etc.). Your text content is sent to OpenAI for this purpose.
- **Hugging Face image moderation** — When enabled (`FORUM_USE_HF_IMAGE_MODERATION=true`), raster images (not documents) uploaded to the forum may be analyzed by **Hugging Face** models to detect inappropriate visual content (NSFW). Your image data is processed by Hugging Face for this purpose.

These moderation services operate in **fail-open mode** — if they are unavailable, your content will still be published. We do not share these moderation results with third parties beyond the analysis itself.

### 2.6 Private tutor profile documents

If you register as a **private tutor** and upload optional documents (for example a CV or certifications in PDF or image formats), those files are stored in the **Supabase Storage bucket `tutor-profile-documents`**, which has a **public read policy**.

**This means:**

- Files uploaded as tutor documents are **publicly accessible** to anyone with the direct URL.
- They are intended to support your public tutor profile visible to students in the App's private tutor marketplace.
- Do not upload sensitive personal information (ID numbers, passwords, financial details, etc.) unless you intend them to be publicly viewable.

The App displays a warning message when you upload tutor documents informing you that these files will be viewable in the forum/marketplace.

### 2.7 Private direct messages

If you use **private messaging** (one-to-one conversations with other users), we store on our servers:

- **Conversation records** — identifiers linking you and the other participant, timestamps, and optional link to a related forum post if the conversation was started from a post.
- **Messages** — text you send and optional **image attachments** and **file attachments** (file URLs and display names stored in the database). Images and files uploaded in direct messages use the same public storage mechanisms as forum uploads.
- **Delivery and read state** — for example when a message was read, as needed to show read status in the App.
- **Blocking** — if you block another user for messaging, we store that relationship (in the `user_blocks` table) so the App can enforce blocks. You can manage blocked users from the App settings.

Direct messages are **not** published to the forum; they are intended to be visible **only to you and the other participant** in that conversation (and to our systems as needed to operate the feature, secure the service, and handle abuse reports).

**Note:** Files and images attached to direct messages, like forum attachments, are stored in **public storage buckets** and may be accessible to anyone with the direct URL. Do not send sensitive personal information, passwords, or confidential documents through direct messages.

We may process messages through **Supabase** (database, storage, and server-side functions) for delivery, moderation when reported, and safety.

### 2.8 Tutor session coordination (in-app scheduling)

The App may allow students and private tutors to **coordinate lesson times** (for example proposals, confirmations, rescheduling, or cancellation of suggested sessions) and to display **context such as an hourly rate in NIS** for scheduling purposes. Related records stored in our database (`tutor_session_bookings`) include:

- Session proposal details (date, time, duration, hourly rate)
- Booking status (pending, confirmed, cancelled, completed)
- Participant identifiers (student and tutor user IDs)
- Links to related forum posts or conversations
- Estimated revenue calculations (UI-only, not financial transactions)

This feature is for **coordination and scheduling only**; the App does **not** process payments for lessons. All financial arrangements, meetings, and contracts are **solely between you and the other party** outside the App (see our Terms of Service).

### 2.9 In-app notifications and subscriptions

We store **in-app notification records** in our database for the following purposes:

- **Forum reply notifications** (`forum_reply_notifications`) — When someone replies to a forum thread you participate in or subscribe to.
- **Forum tutor booking notifications** (`forum_tutor_booking_notifications`) — When students or tutors propose, confirm, reschedule, or cancel tutor sessions.
- **Direct message notifications** (`direct_message_notifications`) — Helper records to alert you of new direct messages when you are not actively viewing the conversation.
- **Forum subscription preferences** (`forum_post_reply_subscribers`) — Which forum threads you have subscribed to for reply notifications.

These records are tied to your account and displayed in the App's notifications inbox. The App uses **Supabase Realtime subscriptions** (WebSocket-based) to listen for new notifications and direct messages while you are actively using the App, triggering local on-device notifications as needed.

This is separate from **local assignment reminders** scheduled on your device (see Section 10).

### 2.10 Tutor reviews

If you are a student and you write a **review** for a private tutor, we store:

- **Review text** and **rating** (e.g., 1-5 stars).
- **Metadata** — reviewer ID, tutor ID, timestamps, visibility status.
- **Reports** — If other users report a review as inappropriate, those reports are stored in `tutor_review_reports` for moderation.

Reviews are visible to other App users viewing the tutor's profile. If you report a review, we store your report record for moderation purposes (admin-accessible only).

### 2.11 User statistics and gamification

The App may track **gamification metrics** tied to your account, including:

- **Streaks** — consecutive days of activity.
- **Points** and **levels** — based on your use of study features.
- **Achievement milestones** — stored in the `user_stats` table.

These are used solely to provide motivational features within the App and are not shared with third parties for marketing purposes.

### 2.12 Local device data (not sent to us)

Examples of data that typically remain **on-device** unless you explicitly upload or publish something:

- Preferences for **local assignment reminders** (scheduled notification identifiers mapped to your assignments) stored in **AsyncStorage**.
- **Notification preferences** (sounds, alerts) stored locally.
- **Reported content cache** (which posts/replies/reviews you reported) stored locally.
- **Extended profile fields** (full name, age, city, degree, study year) stored in **AsyncStorage** via `ProfileDetails`.
- **Avatar image URIs** selected from your device stored locally (OAuth avatars may sync to server).
- Cached copies of files you open for your own use.
- App preferences and UI state (theme, language, onboarding completion status).

### 2.13 Technical & automatic data

- We **do not** embed third-party **advertising** or **analytics** SDKs for behavioral tracking in the App (no Firebase Analytics, Segment, Amplitude, Sentry, etc.).
- When you use online features, **standard technical information** is processed automatically as part of operating any internet service — for example **IP address**, timestamps, request metadata, device OS version, and App version — by us and by our infrastructure providers (such as **Supabase**, hosting networks, and CDN providers) for **security**, **fraud prevention**, **reliability**, **abuse detection**, and **legal compliance**.
- We do **not** sell this information to third parties for marketing purposes.
- **Device information accessed by the App:**
  - **App version and name** (via `expo-constants`) displayed in About/Settings screens.
  - **Locale and timezone** (via `expo-localization`) for UI localization (Hebrew/English).
  - **Camera and photo library access** (via `expo-image-picker`) for profile photo upload and forum/DM image attachments — only when you explicitly trigger these features. Permission purpose strings (in Hebrew) are declared in `app.json`.
  - **Document picker** (via `expo-document-picker`) for forum/DM file attachments.
  - **Notification permissions** (via `expo-notifications`) for local assignment reminders and in-app activity alerts.
  - **Web browser** (via `expo-web-browser`) to open legal documents and external links.
  
The App does **not** access your device GPS location. Any "location" fields in exams or schedule slots are **user-entered text** (e.g., classroom names), not geographic coordinates.

### 2.14 Bug reports and support

If you send a **bug report** from the App, we process:

- The **message text** you enter (please avoid including passwords, payment details, or unnecessary personal data).
- **Account-related identifiers** needed to route the report (for example your **email address** or user ID associated with your session), so we can investigate and reply if needed.
- **Submission timestamp** and other metadata for tracking purposes.

Reports are submitted through the **Supabase Edge Function** `send-bug-report`, which:

1. Stores the report in the `bug_reports` table in our database.
2. Sends an email notification to our support team via **Resend** and/or **Gmail SMTP**, depending on our server configuration.

**Third-party email providers** (Resend and/or Gmail) process your bug report content and email address in transit to deliver the notification to our team. They handle this data according to their own privacy policies:

- **Resend**: [https://resend.com/legal/privacy-policy](https://resend.com/legal/privacy-policy)
- **Google Gmail**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

The App implements rate limiting (server-side and client-side cooldown) to prevent abuse of the bug report system.

We use this information only to **diagnose issues, improve the App, and respond to you** where appropriate.

---

## 3. How We Use Your Information

We use personal information to:

| Purpose | Typical legal basis (where GDPR applies) |
|--------|-------------------------------------------|
| Provide sign-in, sync, and core organizer features | Performance of a contract / steps at your request |
| Operate the forum, marketplace listings, direct messaging, tutor coordination, and in-app notifications | Performance of a contract; legitimate interests in operating a safe community |
| Moderate content, enforce rules, respond to reports | Legitimate interests; legal obligations |
| Store and display profile and content you choose to publish or send | Performance of a contract; consent where required (e.g. certain optional uploads) |
| Secure the service and troubleshoot errors | Legitimate interests |
| Comply with law and respond to lawful requests | Legal obligation |
| Review bug reports and provide support | Legitimate interests / performance of a contract |

We **do not** sell your personal information. We **do not** use your data for third-party advertising profiling.

---

## 4. How Information Is Shared

We share your information in the following circumstances:

### 4.1 Service providers (data processors)

- **Supabase** — for database, authentication, file storage (public storage buckets), server-side Edge Functions, and real-time subscriptions. They process data on our instructions. Privacy policy: [https://supabase.com/privacy](https://supabase.com/privacy)
- **Resend** — email delivery service for bug reports (when configured). Privacy policy: [https://resend.com/legal/privacy-policy](https://resend.com/legal/privacy-policy)
- **Gmail / Google Workspace SMTP** — email delivery for bug reports (when configured). Privacy policy: [https://policies.google.com/privacy](https://policies.google.com/privacy)

### 4.2 AI and moderation services (optional, when enabled)

- **OpenAI** — text moderation for forum submissions (when `FORUM_USE_OPENAI_MODERATION=true`). Your forum text content is sent to OpenAI's Moderation API. Privacy policy: [https://openai.com/policies/privacy-policy](https://openai.com/policies/privacy-policy)
- **Hugging Face** — image moderation for forum uploads (when `FORUM_USE_HF_IMAGE_MODERATION=true`). Raster images are analyzed for inappropriate content. Privacy policy: [https://huggingface.co/privacy](https://huggingface.co/privacy)

These moderation features are **optional server-side configurations** and may be enabled or disabled by us without notice. They operate in **fail-open mode** — if unavailable, content is still published.

### 4.3 Authentication providers

- **Apple** — if you use Sign in with Apple. Privacy policy: [https://www.apple.com/legal/privacy/](https://www.apple.com/legal/privacy/)
- **Google** — if you use Google Sign-In or Sign in with Google. Privacy policy: [https://policies.google.com/privacy](https://policies.google.com/privacy)

### 4.4 Other users

- **Forum and marketplace content** you publish is visible to other App users according to the feature design (by subject, listing type, etc.).
- **Direct messages** are shared only with the **other participant(s)** in that conversation (and with our systems for delivery and moderation purposes).
- **Profile information** (display name, avatar, user role) may be visible to other users in community features.
- **Public storage** — Files uploaded to forum posts, direct messages, and tutor profile documents are stored in **publicly accessible storage buckets** and may be viewed by anyone with the direct URL.

### 4.5 Legal compliance and safety

We may disclose information:

- If required by law, regulation, legal process, or governmental request.
- If we reasonably believe disclosure is necessary to protect rights, property, safety, or the integrity of the service.
- In connection with suspected fraud, abuse, or violations of these Terms or applicable law.
- In connection with a business transaction (merger, acquisition, sale of assets), subject to confidentiality obligations.

### 4.6 No selling of personal information

We do **not** sell your personal information to third parties for their own marketing purposes.

---

## 5. Data location & international transfers

Your data is processed using cloud infrastructure operated by **Supabase** and may be stored or processed in the regions configured for our project (potentially including the **European Union** or other regions Supabase supports). If you are outside those regions, your information may be **transferred internationally**. We rely on appropriate safeguards where required (such as standard contractual clauses or equivalent mechanisms offered by our providers).

---

## 6. Data retention

### 6.1 Active accounts

We retain account and content data **while your account is active** and as needed to provide the service, including:

- Authentication credentials and session tokens.
- Profile information, academic organizer data (courses, exams, assignments, grades, schedule).
- Forum posts, replies, direct messages, tutor listings, reviews, and session bookings.
- Notification records, subscriptions, and user statistics.
- Bug reports submitted from the App.

### 6.2 Account deletion

If you **delete your account** (via the App's Settings → Delete Account feature), we invoke the **`delete_current_user()` SECURITY DEFINER function**, which deletes your `auth.users` record from Supabase Auth.

**What happens after deletion:**

- Your personal authentication data (email, password hash, session tokens) is deleted.
- Associated data in tables with foreign key relationships to your user ID will be handled according to database cascade rules (typically deleted or anonymized).
- We will delete or anonymize associated personal data within a reasonable period, generally **within 30 days**, subject to backup cycles and legal retention requirements.
- **Forum content, messages, and tutor listings** you published may remain in the database if they are referenced by other users' interactions (e.g., replies to your posts), but will be dissociated from your identifiable account information or marked as from a deleted user.
- **Files uploaded to public storage** (forum attachments, tutor documents, DM files) are **not automatically deleted** from Supabase Storage upon account deletion. If you want specific files removed, contact us at **Orikal3107@gmail.com** with file URLs or identifying information before deleting your account.

### 6.3 Content seen by others

**Important:** Forum content, messages, or files you sent may have been **seen, downloaded, or copied by other users** before deletion. We cannot control copies made by others outside our systems.

### 6.4 Local data

Local on-device data (AsyncStorage, SecureStore) remains until you **uninstall the App** or **clear app storage** from your device settings. Uninstalling the App does **not** delete your account or server-side data; you must use the in-app delete account feature or contact us.

---

## 7. Security

We implement appropriate technical and organizational measures, including:

- **Encryption in transit (TLS/HTTPS)** for network communication with our backend services.
- **Secure credential storage** on device using **custom encrypted storage** (`LargeSecureStore`): session tokens are encrypted using **AES-CTR** with encryption keys stored in **Expo SecureStore** (backed by iOS Keychain / Android Keystore), and ciphertext is stored in **AsyncStorage**.
- **Database access controls (Row-Level Security)** — Many tables use Supabase RLS policies so users cannot read other users' **private** organizer data (courses, exams, assignments, grades, personal events, etc.) or **other users' direct messages**.
- **Security definer functions** — Sensitive operations (account deletion, tutor booking management) use SECURITY DEFINER stored procedures with restricted access.
- **Service-role restrictions** — Forum reports and certain admin operations are accessible only to service-role API keys, not user sessions.
- **Community content** is intentionally readable by other users **only** where the product exposes it (forum/listings), not your private grades or personal planner data.
- **Public storage awareness** — Files uploaded to forum and direct messages are stored in **public storage buckets** with world-readable access policies. Users are informed in the App and in these legal documents.

**Important security considerations:**

- No method of transmission or storage is 100% secure.
- **Public storage buckets** mean that files you upload (forum attachments, tutor documents, DM files) are accessible to anyone with the direct URL. Do not upload sensitive personal information.
- We encourage strong passwords, device security (screen lock), and caution when sharing content in the App.
- If you suspect unauthorized access to your account, contact us immediately at **Orikal3107@gmail.com**.

---

## 8. Children's privacy

The App is **not directed at children under 13** (or the minimum age required in your jurisdiction). We do not knowingly collect personal information from children below that age. If you believe we have done so, contact **Orikal3107@gmail.com** and we will take appropriate steps to delete the information.

---

## 9. Your rights

Depending on your location, you may have rights to **access**, **rectify**, **delete**, **restrict**, or **object** to certain processing, and **data portability**. You may also withdraw consent where processing is consent-based.

To exercise these rights, contact **Orikal3107@gmail.com**. We will respond within **30 days** where applicable law requires it.

If you are in the **EEA/UK**, you may lodge a complaint with your local data protection authority.

**California residents (summary):** You may have rights under the **CCPA/CPRA** (for example to know, delete, and opt out of sale/sharing). We do not sell personal information as defined by California law. To submit a request, email **Orikal3107@gmail.com**.

---

## 10. Notifications

The App uses notifications in the following ways:

- **Assignment reminders** — Implemented as **local notifications** scheduled on your device using **expo-notifications**. Scheduling metadata (notification IDs mapped to assignments) is stored locally on your device in **AsyncStorage**. No remote push notification service is used for assignment reminders.
- **Forum activity** — Uses **in-app notification records** stored in our database (for example when someone replies to a thread you participate in or subscribes to). These are displayed in the App's notifications inbox.
- **New direct messages** — May trigger **local notifications** on your device when enabled in your system settings. The App uses **Supabase Realtime subscriptions** to detect new messages and schedule local notifications when you are not actively viewing the conversation. No remote push service (FCM, APNs) token upload or remote marketing push is required for core functionality.
- **Tutor booking notifications** — In-app notification records for session proposals, confirmations, and changes are stored in the database (`forum_tutor_booking_notifications`) and displayed in the App.

**Notification permissions:**

The App requests notification permissions from your device OS (iOS/Android) to display local notifications. You can manage these permissions in your device system settings. The App is configured in **production mode** for `expo-notifications` with no custom notification sounds.

---

## 11. Third-party websites or services

The App may allow you to open links or documents in a browser or in-app web view. Those third parties have their own privacy practices; this policy does not apply there.

---

## 12. Changes to this policy

We may update this Privacy Policy from time to time. We will update the **Last Updated** date at the top. If changes are material, we may provide additional notice (for example in the App). Continued use after the effective date constitutes acceptance of the updated policy where permitted by law.

---

## 13. Contact

**Privacy:** [Orikal3107@gmail.com](mailto:Orikal3107@gmail.com)  
**General:** [Orikal3107@gmail.com](mailto:Orikal3107@gmail.com)  
**App name:** StudenTeam  

---

*This policy is intended to be clear and accurate. If anything here does not match what you see in the App, the App's actual data practices and App Store disclosures should be aligned — please contact us so we can correct documentation.*
