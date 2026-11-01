# Privacy Policy & Google Play Data Safety Disclosure

**Effective Date:** November 1, 2026  
**Developer / Entity:** Anyone-Hub LLC (`info-dev.io` / `anyonehub.tech`)

## 1. Information We Collect & Purpose of Collection
To provide authentication, cloud synchronization, collaborative editing, and companion wearable features across **Dev.io**, **anyone-Connect**, and **Dev.io Build Commander**, we collect only the minimum required data:
- **Account & Identity Data (OAuth 2.1 / OIDC):** When you sign in via Email/Password, GitHub, LinkedIn (OpenID Connect), or Dev.io OAuth 2.1, we receive your unique user identifier, display name, profile avatar URL, and primary email address to provision your developer profile, verify module licenses, and authenticate sessions. If you grant LinkedIn `w_member_social` permissions, social actions are executed strictly at your explicit direction.
- **User-Generated Content & Messaging:** We process Developer Stories (`Dev Drops`), public community posts, collaborative CRDT document deltas, and chat messages you explicitly send. In **anyone-Connect**, standard messages are stored with participant-scoped Row-Level Security (RLS), while **Burn-on-Exit** private chat sessions transmit encrypted messages ephemerally in-memory and automatically purge session data when a participant exits or after 30 minutes of inactivity.
- **IDE Telemetry & Verification Diagnostics:** We log verified build milestones, plugin installation checksum integrity (`log-telemetry`), and crash diagnostics strictly to award developer achievement badges, enforce security policies, and maintain system reliability.
- **Wear OS Sensor Data (Dev.io Build Commander):** On Wear OS devices, the watch face and companion app access hardware step counter data (`android.permission.ACTIVITY_RECOGNITION` / `Sensor.TYPE_STEP_COUNTER`) locally on the watch strictly to display your daily step progress on the watch face complication. Health and step sensor data is processed locally on your device, is never transmitted to advertising networks, and is never sold to third parties.

## 2. How We Use & Protect Your Data
All data transmitted between your devices and our backend infrastructure (powered by Supabase) is encrypted in transit using TLS 1.3 and protected at rest via PostgreSQL Row-Level Security (RLS) and RFC 7636 PKCE (`S256`) authentication. Private profile attributes (such as push notification tokens and birthdates) are isolated from public profile views. **We do not sell, rent, or trade your personal data or source code to third parties or advertisers.**

## 3. Data Retention & Account Deletion Policy
You retain full ownership of your personal data and may request permanent deletion of your account and all associated cloud records at any time:
- **In-App Account Deletion:** Open **Dev.io** or **anyone-Connect**, navigate to **Settings → Account → Delete Account**, and confirm deletion.
- **Email / Web Deletion Request:** If you no longer have the application installed, send an account deletion request from your registered email address to **tomslinkard@anyonehub.tech** or **anyone-hub.dev@zohomail.com** with the subject line `"Account Deletion Request"`. All profile records, authentication tokens, messages, and cloud data associated with your account will be permanently purged within 7 business days.

## 4. Contact Information
For privacy or data deletion requests, support, or questions regarding this policy, please contact:
- **Primary Support & Legal:** tomslinkard@anyonehub.tech  
- **Developer Support:** anyone-hub.dev@zohomail.com  
- **Web:** https://info-dev.io

Copyright © 2024–2026 Anyone-Hub LLC. All rights reserved.
