# Account & Data Deletion Request

**Last updated:** June 2, 2026

This page explains how to request the permanent deletion of your UniPlan account and associated data.

---

## Option 1: Delete directly in the app (recommended)

The quickest way to delete your data and account is through the app itself.

### To delete all app data (local + cloud):

1. Open **UniPlan** on your device.
2. Go to the **Settings** tab.
3. Scroll to the bottom and tap **"DELETE ALL APP DATA"**.
4. Follow the on-screen confirmation prompts.
5. If you have a sync account, you will be asked whether you also want to delete your account. Tap **"Yes"** to permanently remove it.

### To delete only your sync account:

1. Open **UniPlan** on your device.
2. Go to the **Settings** tab.
3. In the **Account / Cloud Sync** section, tap **"Delete Account"**.
4. Confirm the deletion.

Once confirmed, all your cloud data is immediately deleted and your account is permanently removed.

---

## Option 2: Contact dStudios directly

If you are unable to use the in-app deletion option, you can submit a deletion request by contacting us:

**Email:** david@dstudios.org  
**GitHub Issues:** https://github.com/dStudios-735453/UniPlan_Releases/issues

When submitting a request, please include:

- Your **email address** used for your UniPlan account.
- Whether you want to delete **all data** or just your **cloud account**.

We will process your request within reasonable time and confirm once the deletion is complete.

---

## What data is deleted

When you delete your account through the app, the following data is permanently removed:

| Data                                                    | Deleted?                               |
| ------------------------------------------------------- | -------------------------------------- |
| Your class schedule                                     | Yes                                    |
| Homework assignments                                    | Yes                                    |
| To-do items                                             | Yes                                    |
| App settings & preferences                              | Yes                                    |
| Subject presets and autofills                           | Yes                                    |
| Manual holidays                                         | Yes                                    |
| Your email address and auth record (Firebase Auth)      | Yes                                    |
| Encrypted master key and recovery data                  | Yes                                    |
| Subscription status association                         | Yes                                    |
| School integration credentials (Schulmanager, Adservio) | **Local only — never stored in cloud** |

---

## What data is kept and retention periods

After you delete your account, the following data may persist for a limited time:

| Data                                                | Retention Period                              | Reason                                                                                                                                                                                                          |
| --------------------------------------------------- | --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Anonymous analytics events** (Firebase Analytics) | Up to 13 months per Google's retention policy | Aggregated usage statistics — not personally identifiable                                                                                                                                                       |
| **Error logs** (Sentry)                             | 90 days                                       | App stability monitoring — not personally identifiable                                                                                                                                                          |
| **Purchase receipts** (RevenueCat)                  | Retained for the duration of the subscription | To prevent fraudulent restoration of purchases, RevenueCat does not store personal data — only app user IDs and transaction identifiers, but the purchase records on Apple and Google can be hold on to longer. |

No personal data is sold, shared, or used for advertising purposes.

---

## Local app data

The in-app deletion process also clears all locally stored data on your device.  
If you only uninstall the app without deleting your account through the in-app option, any data that was synced to the cloud will remain there. To remove cloud data, please follow the in-app deletion steps above or contact us to request deletion.

If you have any questions, please reach out at **david@dstudios.org**.
