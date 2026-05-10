# App Store Connect Privacy Answers Draft

Last updated: 2026-05-09 America/Chicago

Use this as a draft while completing App Store Connect App Privacy. Confirm against the final hosted privacy policy, enabled services, and any analytics/crash SDKs before publishing.

## Tracking

- Does this app use data for tracking? `No`
- Does this app use third-party advertising? `No`

## Data Types To Consider Declaring

These data types may be collected or processed for app functionality depending on enabled features:

- Contact Info / User ID: Sign in with Apple account identity, if stored or associated with app account state.
- User Content: watchlists, notes, ratings, group watch activity, votes, wheel items, partner/shared activity.
- Purchases: subscription entitlement and purchase state from StoreKit if products are enabled.
- Identifiers: CloudKit record identifiers or app account identifiers used for app functionality.
- Usage Data: only declare if analytics is later added. No analytics SDK is currently present in the project.
- Diagnostics: only declare if crash reporting or diagnostics collection is later added. No third-party crash/analytics SDK is currently present in the project.

## Suggested App Privacy Rows

Confirm in App Store Connect against the final enabled features before publishing:

| Data type | Collected | Linked to user | Tracking | Purpose |
| --- | --- | --- | --- | --- |
| User ID | Yes, when Sign in with Apple or iCloud-backed sharing is used | Yes | No | App Functionality |
| Name | Yes, if users enter display names for group watch or sharing | Yes | No | App Functionality |
| User Content / Other User Content | Yes, for watchlists, notes, ratings, votes, group sessions, and partner-shared activity | Yes | No | App Functionality |
| Purchase History | Yes, if subscriptions are enabled through StoreKit | Yes | No | App Functionality |
| Product Interaction | No, unless analytics is later added | No | No | Not declared |
| Crash Data / Performance Data | No, unless diagnostics tooling is later added | No | No | Not declared |
| Advertising Data | No | No | No | Not declared |

## Linked To User

Data used for account-backed app functionality, iCloud sharing, purchases, or shared watchlists should be treated as linked to the user when App Store Connect asks.

## Purposes

Recommended purposes:

- App Functionality: account/session state, watchlists, partner sharing, group watch, preferences, subscription entitlement, notifications.
- Product Personalization: only if App Store Connect requires it for recommendation/personalized watchlist behavior; otherwise keep the purpose as App Functionality.

## Not Used

- Advertising
- Third-Party Advertising
- Developer's Advertising or Marketing
- Analytics, unless analytics tooling is added later

## Notes

- Personal watchlists are local by default in build `1.0 (9)`.
- CloudKit Sharing is used when a user invites a partner.
- CloudKit public database records are used for group watch sessions and can include session codes, host/member display names, votes, wheel items, vetoes, status, and timestamps.
- TMDB requests are for content metadata lookup and app functionality.
- `WatchWarden/PrivacyInfo.xcprivacy` currently declares no tracking and only the required UserDefaults accessed API reason.
- User Privacy Choices URL can point to the hosted `privacy-choices.html` page if App Store Connect requests one.
