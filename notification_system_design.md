# Notification System Design

## Overview

The notification application fetches campus hiring notifications from the evaluation API and displays them in a React frontend. Users can filter notifications by type, page, limit, search text, and viewed status.

## Frontend

- Built with React.js and Vite.
- Main UI lives in `notification_app_fe/src/App.jsx`.
- Styling lives in `notification_app_fe/src/styles.css`.
- The app fetches data from `http://20.207.122.201/evaluation-service/notifications`.
- Query parameters used by the frontend are `limit`, `page`, and `notification_type`.

## Notification Priority

Notifications are sorted so that important items appear first:

1. New notifications before viewed notifications.
2. `Placement` notifications before `Result`.
3. `Result` notifications before `Event`.
4. Newer timestamps before older timestamps.

## Viewed Status

The frontend stores viewed notification IDs in browser `localStorage`. This keeps the UI simple and avoids needing a database for the frontend evaluation stage.

## Fallback Data

If the evaluation API is unavailable or returns an authorization error, the React app displays sample notification data so that the UI remains testable.
