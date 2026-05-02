# Campus Notification Frontend

React.js implementation for the campus hiring notification evaluation.

## Run

Install dependencies once:

```powershell
npm install
```

Run the React development server:

```powershell
npm run dev
```

Then visit:

```text
http://localhost:3000
```

## Implemented Requirements

- Fetches notifications from `http://20.207.122.201/evaluation-service/notifications`.
- Uses React components and hooks for state, filtering, rendering, and API loading.
- Sends the required query parameters:
  - `limit`
  - `page`
  - `notification_type`
- Supports the documented notification types:
  - `Event`
  - `Result`
  - `Placement`
- Displays message, type, ID, and timestamp.
- Prioritizes results with `Placement > Result > Event`, then newest first.
- Uses browser `localStorage` to distinguish new notifications from already viewed notifications.
- Includes responsive layout for desktop and mobile screens.
- Falls back to sample notifications if the API is unavailable, so the frontend remains testable.
