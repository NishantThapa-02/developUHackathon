# Refinements

## Behavior

- Centralized navigation in a reducer. Future steps stay locked, invalid prior details block progression, and stale duplicate Next events are rejected.
- Added legal name, calendar date, address, email, US phone, and nine-digit sample tax ID format validation with field-level messages.
- Personal fields now start empty. A clearly named sample-data action fills a fictional profile.
- Agreements start unchecked, toggle through native checkbox change events, and clear after profile or account changes.
- Free Checking and Rewards Checking selections now carry through comparison, review, and completion.
- Funding accepts cents, rejects invalid or out-of-range amounts, handles an empty field, and supports funding later.
- Completion uses the selected amount and method without adding a fictitious $5 checking balance.
- Removed simulated success alerts and delayed navigation timers. Clipboard status now reflects actual success or failure.
- Removed the global Enter handler that could advance the flow while interacting with other controls.

## Usability and accessibility

- Rebuilt the header for narrow screens, ordered stages to match the flow, and kept Help available on mobile.
- Added native modal dialogs with focus containment, Escape dismissal, backdrop dismissal, scroll locking, and focus restoration.
- Added semantic radio controls, selection states, progress announcements, form labels, error relationships, skip navigation, and heading focus on screen changes.
- Added visible keyboard focus, reduced-motion support, consistent form styling, and stronger action-button contrast.
- Replaced the fragile remote header logo with a text wordmark.
- Clearly identified the app and its identity, agreement, and funding interactions as a preview.

## Maintenance

- Enabled strict TypeScript checking and shared validation, state transition, formatting, modal, and form-action helpers.
- Removed unused AI SDK, Express, dotenv, animation, and icon-library dependencies, and removed the obsolete API-key setup requirement.
- Simplified Vite configuration and made build scripts cross-platform.
- Added a dependency lockfile, formatting configuration, unit tests, and browser regression tests.
