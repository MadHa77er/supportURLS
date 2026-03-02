# Privacy Policy for CurrentStatus

**Effective Date:** March 2, 2026

CurrentStatus is a watchOS app that displays health metrics, reminders, and utility tools on your Apple Watch. Your privacy is important to us. This policy explains what data the app accesses, how it is used, and how it is stored.

## Data We Access

### Health Data (HealthKit)

CurrentStatus reads the following data from Apple HealthKit:

- **Heart rate** — your most recent heart rate reading
- **Step count** — your daily step total
- **Walking distance** — your daily walking and running distance

Health data is **read-only**. CurrentStatus never writes, modifies, or deletes any of your health data. Access requires your explicit permission through the standard HealthKit authorization prompt.

### Reminders (EventKit)

CurrentStatus reads your incomplete reminders to display upcoming and overdue tasks. It does not create, modify, or delete any reminders. Access requires your explicit permission.

### Microphone

CurrentStatus uses the microphone to record voice memos. Recordings are saved locally on your device as audio files. Microphone access requires your explicit permission and is only active while you are recording.

## Data Storage

All data stays on your device. Specifically:

- **Health data** is read from HealthKit on demand and cached locally using UserDefaults for faster display. Cached values are replaced each day.
- **Reminders** are read from EventKit on demand and are not cached.
- **Voice memos** are saved as audio files in the app's local Documents directory on your Apple Watch.
- **Preferences** such as water intake count, favorite shortcuts, and locally dismissed reminders are stored in UserDefaults on your device.

## Data We Do Not Collect

CurrentStatus does **not**:

- Collect, transmit, or share any personal data with third parties
- Use analytics, crash reporting, or tracking services
- Contain advertising of any kind
- Require an account, login, or registration
- Send any data over the internet

The app makes **zero network requests**. All functionality is entirely on-device.

## Third-Party Services

CurrentStatus does not use any third-party services, SDKs, or frameworks that collect data.

## Children's Privacy

CurrentStatus does not knowingly collect any personal information. Because no data leaves the device, the app does not pose data collection risks for users of any age.

## Changes to This Policy

If we update this privacy policy, the revised version will be posted here with an updated effective date.

## Contact

If you have questions about this privacy policy, please open an issue on the project's GitHub repository.
