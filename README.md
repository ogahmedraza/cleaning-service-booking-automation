# Cleaning Service Booking Automation

> A booking workflow for cleaning businesses that checks availability before it confirms a job.

## The use case

A booking form should not promise a time slot that has already been taken. This workflow validates a booking request, checks the connected calendar, saves only confirmed jobs, and notifies both the customer and the operations team.

## Workflow map

```text
Booking webhook
  → normalize and validate booking details
  → check calendar availability
  ├─ available: create Sheet record + Calendar event + send confirmations
  └─ unavailable: return an alternative / unavailable response
```

## What is included

- Booking-data validation before calendar actions
- Calendar conflict check
- Confirmed-booking log in Google Sheets
- Job creation in Google Calendar
- Customer confirmation by Gmail
- Staff notification through Telegram
- Separate handling for unavailable slots and workflow failures

## Configure before use

1. Import `workflow.json` into n8n.
2. Connect Google Calendar, Google Sheets, Gmail, and Telegram.
3. Select the actual job calendar and booking sheet.
4. Replace sample staff-chat, sender, service-area, timezone, and business rules.
5. Run tests with a non-production calendar before enabling the webhook.

## Operational decisions you still own

This template does not decide your service area, travel buffer, booking duration, deposit policy, cancellation terms, or staff allocation. Put those rules into the form, calendar logic, or a human review step before going live.

## Why the calendar check matters

The workflow makes the availability decision before it creates the calendar job or sends a confirmation. That sequence reduces double-booking risk, but the final result still depends on your calendar access, timezone configuration, and the data sent by the booking form.

## Repository contents

| File | Purpose |
| --- | --- |
| `workflow.json` | Importable n8n booking workflow |
| `SECURITY.md` | Guidance for safe credential and webhook handling |
| `LICENSE` | MIT license |

## License

MIT — see [LICENSE](LICENSE).