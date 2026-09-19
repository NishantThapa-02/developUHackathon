# UFCU Membership Onboarding

A refined React + TypeScript prototype with ten onboarding steps. The existing navy and orange design is retained, with responsive navigation, validated forms, keyboard support, and consistent account selection.

## Run locally

Use Node.js 22.18 or later.

```sh
npm install
npm run dev
```

Open http://127.0.0.1:3000. No API keys or environment variables are required.

The included pnpm lockfile also supports a reproducible installation with pnpm 11:

```sh
pnpm install --frozen-lockfile
pnpm dev
```

## Checks

```sh
npm run lint
npm test
npm run build
npm run format:check
```

Browser tests use Playwright and axe. Install Chromium once, then run them:

```sh
npx playwright install chromium
npm run test:e2e
```

To use an installed Edge browser on Windows:

```powershell
$env:PLAYWRIGHT_CHANNEL = 'msedge'
npm run test:e2e
```

The browser suite covers desktop and mobile layouts, all ten steps, keyboard dialogs, validation, account choice, consent, decimal deposits, funding later, clipboard errors, and restart behavior. It checks WCAG A/AA rules with axe on the covered screens; automated checks do not replace a full accessibility audit.

## Try the flow

1. Choose an intent, priorities, and life stage.
2. Continue with Free Checking or choose Rewards Checking in **Compare options**.
3. Pick an identity method. Use **Use sample information** on the next screen, or enter fictional details.
4. Review the sample profile and check the three sample agreement boxes.
5. Enter an amount such as **25.75**, or select **I’ll fund later**.
6. Review and copy the simulated summary, or start a new preview.

Completed steps remain available in the step selector. Changing profile details or account choice clears previous consent and requires review again.

## Project structure

- `src/App.tsx`: screen composition and focus management.
- `src/onboarding.ts`: state transitions, validation, account descriptions, sample profile, and formatting.
- `src/types.ts`: application state and step metadata.
- `src/components/Dialog.tsx`: reusable native modal with focus restoration and Escape dismissal.
- `src/components/StepActions.tsx`: shared form navigation.
- `src/components/steps/`: the ten screens.
- `tests/onboarding.test.ts`: validation and state transition regression tests.
- `tests/browser/onboarding.spec.ts`: browser journeys and accessibility checks.

## Prototype boundaries

Identity scanning, digital identity, payments, account creation, legal agreements, and account terms are illustrative. No real verification or banking integrations are implemented. Financial terms retained from the supplied design are sample content, not verified current UFCU offers.

Use fictional information. Entries remain in React memory and are cleared by refresh or restart. There is no local storage, analytics, or application submission. Google Fonts and some original decorative images load from external hosts.

Before a live release, replace sample product terms and agreements with approved content and connect authenticated backend validation, membership eligibility, identity verification, consent records, and payment processing. Client-side validation currently checks input format; it does not verify identity, eligibility, tax identifiers, email ownership, or phone ownership.
