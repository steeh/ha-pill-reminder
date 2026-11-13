# Pill Reminder for Home Assistant

A blueprint that reminds you to take your pills, morning and night, on an Android phone.

- High-priority pop-up with **✅ Taken** and **⏰ Snooze** buttons
- Repeats until you tap Taken (every 15 min by default, up to 8 times), then sends a "not taken" warning
- Reminder times come from helpers, so you can change them from the dashboard
- Tapping Taken (or switching the "taken" toggle on) stops the reminders and clears the notification

## Install

[![Open your Home Assistant instance and show the blueprint import dialog with this blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fsteeh%2Fha-pill-reminder%2Fblob%2Fmain%2Fblueprints%2Fautomation%2Fpill_reminder%2Fpill_reminder.yaml)

Or: **Settings → Automations & Scenes → Blueprints → Import Blueprint** and paste

```
https://github.com/steeh/ha-pill-reminder/blob/main/blueprints/automation/pill_reminder/pill_reminder.yaml
```

## Set up

1. **Create three helpers** in Settings → Devices & services → Helpers:
   - **Date and/or time**, *Time* only: `Morning Pill Time`
   - **Date and/or time**, *Time* only: `Night Pill Time`
   - **Toggle**: `Pills taken`
2. Set the two times (tap the helper, pick a time).
3. **Settings → Automations & Scenes → Blueprints → Pill Reminder → Create automation.**
   Pick your phone and the three helpers, change the messages if you like, and save.
4. Optional: add the three helpers to your dashboard to see and change the times and whether today's
   dose is marked as taken.

## Requirements

- Home Assistant 2024.10 or newer
- Home Assistant Companion app on **Android** (the notification options used are Android-specific)

## Tips

- **Ring on Do Not Disturb:** long-press a reminder on the phone → ⚙️ → turn on *Override Do Not Disturb*
  for the **Pill Reminders** channel.
- **Testing:** run the automation from its ⋮ menu → *Run actions*. Before 14:00 you get the morning
  reminder, after that the night one.
- Notification buttons are unique to each reminder, so an old notification's buttons do nothing.
