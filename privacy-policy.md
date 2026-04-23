---
title: "Privacy policy"
layout: about
permalink: /privacy/
---

**Privacy Policy — Trace**

This privacy policy applies to the **Trace: Peptide & TRT Tracker** mobile application (the "App") published by Streamlined Studios ("we", "us"). Trace is designed as a private, on-device logbook: the default state is that no personal data leaves your iPhone. This policy describes exactly what is collected, how it is used, and the limited cases in which information is sent to a third-party service — and how you control each of those cases.

This policy is effective as of 2026-04-23.

---

**Summary (TL;DR)**

*   Trace has no user accounts, no sign-in, and no server owned by us that stores your data.
*   All health logs (doses, weights, lab results, check-ins, notes, photos) are stored locally on your device using Apple's on-device database (SwiftData). They only leave your device if *you* choose to.
*   Two features send data to third parties, and both require your explicit opt-in: (1) AI Insights, which sends a de-identified summary of your logs to OpenAI through a privacy proxy; (2) Apple Health sync, which reads and writes body mass in Apple Health if you enable it.
*   Subscription management is handled by Apple (App Store / StoreKit) and RevenueCat as the subscription-state broker. No personal health data is ever sent to RevenueCat.
*   We do not use analytics SDKs, crash reporters, advertising SDKs, or location services.

---

**Information Trace Collects**

All of the following is stored *locally on your device only*, inside the app's private container, unless you explicitly opt in to one of the third-party integrations described later.

Information you enter yourself:

*   Peptide, vial, and dose log entries (peptide name, concentration, dose amount, timestamp, injection site, notes)
*   Daily check-in scores (energy, mood, sleep, libido, morning wood) on a 1–5 scale, if enabled
*   Weight entries (value, unit, timestamp)
*   Lab results (test name, value, unit, timestamp, notes)
*   Progress photos you attach (stored as references to your device's Photos library)
*   Protocol template selection and onboarding preferences

Information Trace derives on-device:

*   Reconstitution math (mg / mL → syringe markings) computed from values you entered
*   Reminder schedules that power local iOS push notifications

**Information Trace Does NOT Collect**

Trace does not collect, transmit, or store any of the following:

*   Your name, email address, phone number, Apple ID, or any other identifier
*   Your IP address (the app does not make any direct network calls to our infrastructure — we have no user database)
*   Your precise or approximate location
*   Your device identifier, advertising identifier (IDFA), or any persistent device ID
*   Analytics, crash reports, or telemetry of any kind — there is no analytics SDK, no Firebase, no Sentry, no Crashlytics in the app
*   Contacts, photos (unless you attach one to a progress entry), calendar events, or any other system data

---

**How Your Information Is Used**

All locally stored data is used solely to render your logs back to you — timelines, charts, check-in history, vial expiry tracking, and local reminder notifications. None of this data leaves your device for that purpose.

Data is only transmitted off-device in the following cases, each of which you control:

1.  **AI Insights (opt-in, see "AI Processing" below)** — sends a de-identified summary of your logs to OpenAI through AIProxy to generate pattern observations.
2.  **Apple Health sync (opt-in)** — reads and writes body mass to Apple Health, under Apple's HealthKit permission system. Data remains on your device and inside Apple's Health app.
3.  **CSV export (user-initiated)** — if you tap "Export dose log" in Settings, Trace writes a CSV file to the iOS share sheet. It's then up to you where that file goes.
4.  **Subscription purchase (if you buy Trace Pro)** — Apple handles payment via StoreKit, and RevenueCat brokers the entitlement state. No health data is shared; see "Third-Party Services" below.

---

**AI Processing (Third-Party AI Disclosure)**

This section is required by App Store Review Guidelines 5.1.1(i) and 5.1.2(i) and describes in full what happens when you turn on AI Insights.

AI Insights is an **opt-in** feature. Before the first insight is generated, Trace presents an in-app disclosure sheet that names the data, the processor, and requires you to tap "Allow insights". You can revoke this consent at any time in Settings → Privacy → AI Insights, which also deletes any cached insight from your device.

**What is sent to the AI service:**

*   Weight trend — numeric values only, in your chosen unit
*   Dose counts by peptide name (last 30 days)
*   Check-in scores (energy, mood, sleep, libido) on the 1–5 scale
*   Lab results you have entered (numeric value + unit)

**What is NOT sent:**

*   Your name, email, Apple ID, or iCloud identifier
*   Photos or any image data
*   Free-text notes you have written
*   Device identifier, advertising identifier, or IP address

**Who sees the data:**

*   The request is routed through **AIProxy** (Lam Labs LLC), a privacy proxy that terminates your TLS connection on its server, strips your IP address, and forwards the payload to OpenAI. AIProxy does not store the payload.
*   **OpenAI** (OpenAI, L.L.C.) generates the insight text using the `gpt-4o` model, under OpenAI's API terms — which contractually exclude submitted data from being used to train OpenAI's models and limit retention to the minimum required to operate the service.
*   Streamlined Studios (us) never receives, reads, or stores the payload or the generated insight on any server — the response goes directly back to your device and is cached locally.

AIProxy privacy policy: <https://www.aiproxy.com/docs/privacy.html>  
OpenAI API data usage: <https://openai.com/policies/api-data-usage-policies>

Insights are observational only. They are not medical advice, and Trace's system prompt explicitly instructs the model never to recommend doses or diagnose conditions.

---

**Third-Party Services**

Trace integrates the following third parties. Each is listed with the specific data that flows to it and the vendor's own privacy policy.

*   **AIProxy** — AI Insights only, opt-in. See "AI Processing" above.  
    Privacy policy: <https://www.aiproxy.com/docs/privacy.html>

*   **OpenAI** — AI Insights only, opt-in. See "AI Processing" above.  
    Privacy policy: <https://openai.com/policies/privacy-policy>

*   **RevenueCat** — used to verify and refresh your Trace Pro subscription status. RevenueCat receives a randomly generated, anonymous user ID tied to your device plus Apple's StoreKit transaction receipts. No health data, no personal identifiers, and no log content is ever sent to RevenueCat.  
    Privacy policy: <https://www.revenuecat.com/privacy/>

*   **Apple (App Store / StoreKit)** — handles the purchase of Trace Pro subscriptions. Apple's own privacy policy applies to that transaction.  
    Privacy policy: <https://www.apple.com/legal/privacy/>

*   **Apple HealthKit** — used only if you opt in to weight sync in Settings → Health. Data is exchanged between Trace and Apple's Health app under Apple's HealthKit permission system. No HealthKit data is sent to any other third party.

We require each third party named above to provide a level of data protection at least equivalent to what is described in this policy. In particular, AIProxy's proxy-based architecture and OpenAI's API terms ensure that data sent for AI Insights is not retained beyond what is required to generate a response and is not used to train models.

---

**Your Controls**

*   **Turn off AI Insights** — Settings → Privacy → AI Insights toggle. Cached insights are deleted on the device when you turn it off.
*   **Turn off Apple Health sync** — Settings → Health, or revoke permission from the iOS Health app itself.
*   **Delete all data** — Settings → Data → Delete all data removes every peptide, vial, dose, weight, photo reference, and lab result from your device. This action cannot be undone.
*   **Uninstall** — removing the Trace app from your device also removes all locally stored data.
*   **Export your data** — Settings → Data → Export dose log (CSV) produces a file containing your logs, which you can then share or archive.

---

**Data Retention**

Locally stored data remains on your device until you delete it or uninstall the app. We do not retain any of your health data on a server because we do not have one; there is no account to delete.

AI Insights: the request/response pair is not retained by AIProxy or OpenAI beyond what is required to generate the response (see OpenAI API data usage policy linked above). Trace caches the generated insight text locally on your device until you refresh it or revoke AI Insights consent.

Subscription state: RevenueCat retains the anonymous subscription ID and transaction history for the duration required to provide subscription validation and refund/entitlement recovery, per RevenueCat's own policy.

---

**Security**

Your data is stored inside the app's private iOS sandbox, which is protected by iOS file-system encryption tied to your device passcode. We offer an optional Face ID / Touch ID lock (Settings → Privacy) that requires biometric authentication before the app's UI loads.

Network traffic for AI Insights is TLS-encrypted end to end — Trace → AIProxy → OpenAI.

No system is perfectly secure, but because Trace stores your data locally rather than on a central server, there is no "Trace database" for a third party to breach.

---

**Children**

Trace is rated 17+ on the App Store due to frequent references to medications and treatment information. The App is not directed to, and we do not knowingly collect information from, anyone under the age of 17. If you believe someone under 17 is using Trace and has provided information through it, please contact us.

---

**Your Rights (GDPR / CCPA)**

Because Trace does not collect personal information that identifies you, most of the access / deletion rights under GDPR and CCPA are satisfied by the in-app controls listed in "Your Controls" above — your logs never leave your device unless you opt in. If you have a specific request (for example, you want confirmation in writing that we hold no personal data about you), contact matt@streamlinedstudios.com.

We do not sell, rent, or share personal information for advertising purposes. We have never received a government or law enforcement request for user data, and if we did, we would have no user data to produce.

---

**Changes to This Policy**

We may update this policy as Trace evolves. Material changes will be reflected by updating the effective date at the top and, where the change is significant (for example, adding a new third-party service), we will surface a notice in-app on the next launch.

---

**Contact**

Questions about this policy, or a request related to your data, can be sent to:

**matt@streamlinedstudios.com**
