# Cleaning Service Booking Automation

An n8n booking workflow for cleaning businesses. It validates booking data, checks calendar availability, handles unavailable slots, saves confirmed bookings, creates calendar jobs, emails the client, and alerts staff through Telegram.

## Flow

`Webhook → Validation → Calendar availability → Booking decision → Sheets/Calendar → Gmail + Telegram`

## Included

- Booking validation and normalization
- Availability and conflict handling
- Alternative response for unavailable slots
- Google Sheets booking record
- Google Calendar job creation
- Client confirmation and staff notification
- Error and production notes

## Setup

Import `workflow.json` into n8n and connect your own Google Calendar, Google Sheets, Gmail, and Telegram credentials. Configure the calendar, sheet, staff chat, webhook, and timezone before activation.

This is a demo workflow and contains no credentials or client data.
