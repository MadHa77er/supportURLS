# CurrentStatus Support

## Frequently Asked Questions

**How do I change which tiles appear on the home screen?**
Tap the gear icon in the top-left corner of the home screen to open the Favorites Settings view. From there you can select or deselect tiles. A maximum of 4 tiles can be displayed at once.

**Why does my heart rate show "--"?**
The heart rate tile reads the most recent sample from HealthKit. If no sample is available (for example, on a simulator or if the sensor hasn't taken a reading yet), the tile will show "--". Make sure HealthKit permissions are granted in Settings > Privacy & Security > Health.

**How often does data refresh?**
Most tiles refresh automatically every 90 seconds. The Heart Rate tile refreshes every 15 seconds for a more up-to-date reading. You can also tap the refresh button (circular arrow in the top-right corner) at any time to manually refresh all tiles.

**How do I complete a reminder?**
Tap the Reminders tile to open the reminders list, then swipe left on a reminder and tap the checkmark to complete it. The list will automatically backfill with the next available reminder.

**Why does a completed reminder come back?**
CurrentStatus tracks completed reminders locally on the watch. Completions are stored in the app's local data, not written back to Apple Reminders (EventKit on watchOS is read-only for reminder completion). If you clear the app's data, previously completed reminders may reappear. To permanently complete a reminder, mark it as done in the Reminders app on your iPhone.

**Where are voice memos stored?**
Voice memos are saved as `.m4a` files in the app's local Documents directory on the Apple Watch. They are not synced to iCloud or any external service.

**Does the water count reset each day?**
Yes. The water intake counter resets to zero automatically at the start of each new calendar day.

**Can I use CurrentStatus without an Apple Watch?**
No. CurrentStatus is a standalone watchOS application and requires an Apple Watch running watchOS 10.0 or later.

---

## Data Collection and Storage

CurrentStatus does **not** collect, transmit, or share any personal data with external servers or third parties. All data stays on your Apple Watch.

### Data stored locally on the device

| Data | Storage method | Purpose |
|------|---------------|---------|
| Favorite tile selection | UserDefaults | Remembers which 4 tiles you chose to display |
| Completed reminder IDs | UserDefaults | Hides reminders you have swiped away so they don't reappear |
| Daily water glass count | UserDefaults | Tracks glasses of water consumed today; resets daily |
| Voice memo audio files | App Documents directory (`.m4a` files) | Stores recordings you create with the Voice Memo tile |

### Data read from system frameworks (not stored by CurrentStatus)

| Data | Source | Purpose |
|------|--------|---------|
| Heart rate | HealthKit | Displays your most recent heart rate reading |
| Step count and walking distance | HealthKit | Displays daily step count on the Steps tile |
| Reminders | EventKit | Displays upcoming and overdue reminders |

CurrentStatus does **not** write data back to HealthKit or EventKit. It only reads from these frameworks.

### Network activity

CurrentStatus makes **no network requests**. It does not contain analytics, advertising, or crash-reporting SDKs. All processing happens entirely on the device.

---

## Permissions

CurrentStatus requests the following system permissions. Each is requested only when you first interact with the relevant tile.

| Permission | System prompt | Why it is needed |
|------------|--------------|-----------------|
| **HealthKit (read)** | "CurrentStatus would like to read your Health data" | Required to display heart rate and step count on their respective tiles |
| **Reminders (full access)** | "CurrentStatus would like full access to your Reminders" | Required to fetch and display your incomplete reminders. Full access is requested because the EventKit API on watchOS requires it to read reminder data. CurrentStatus does not create, modify, or delete reminders. |
| **Microphone** | "CurrentStatus would like to access the microphone" | Required to record voice memos |

You can revoke any of these permissions at any time in the system Settings app under Privacy & Security.

---

## Licensing

CurrentStatus is an independently developed application. It does not incorporate third-party libraries, frameworks, or licensed code. All source code is original.

The application relies on the following Apple system frameworks, which are provided as part of watchOS and governed by Apple's standard SDK license:

- **SwiftUI** -- User interface
- **HealthKit** -- Heart rate and step data
- **EventKit** -- Reminders
- **AVFoundation** -- Audio recording and playback
- **WatchKit** -- Haptic feedback

No additional open-source or commercial licenses apply to this project.
