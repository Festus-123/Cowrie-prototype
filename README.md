# Cowrie

Cowrie is a browser-based prototype of a mobile banking app focused on making transfer status clear, especially when a user loses network connectivity. The project is a single-page demo, not a production banking service.

## Features

- Mobile-style account dashboard with a sample balance, recent activity, and saved recipients.
- Simulated bank-account lookup and a guided transfer flow: choose a recipient, enter an amount, review fees, and swipe to send.
- Offline transfer queue: take the demo offline before confirming a transfer, then bring it back online to simulate automatic sending.
- Transfer receipts with share, copy-reference, and print/save-as-PDF actions.
- Activity search and filters, plus demo cards, notifications, profile settings, bill payment, airtime, and add-money screens.
- Responsive layout, light/dark system theme support, and reduced-motion support.

## Run the demo

No build step or package installation is needed. Open `index.html` in a modern browser. For the browser's online/offline events and clipboard features to behave consistently, serve the project over localhost, for example:

```powershell
py -m http.server 8000
```

Then open <http://localhost:8000>.

## Try a transfer

1. On the home screen, choose **Send**.
2. Enter one of the demo account numbers below and select the account that appears.
3. Enter an amount, continue, and swipe to send.
4. To try offline handling, switch the **Online** control to **Offline** before swiping. The transfer is queued and sent in the demo when you switch back online.

| Demo account | Recipient | Result |
| --- | --- | --- |
| `0022063129` | Alfred Ubong | Simulated successful transfer |
| `0123456789` | Chioma Eze | Simulated successful transfer |
| `2034567890` | Emeka Nwosu | Simulated bank failure; retrying simulates success |

## Technology and dependencies

The interface and demo logic are implemented in plain HTML, CSS, and JavaScript in `index.html`. There is no build system and no Python or JavaScript package dependency. The Inter font is loaded from Google Fonts when an internet connection is available; system sans-serif fonts are used as fallbacks.

`requirement.txt` is retained for tooling that expects a Python requirements file; it documents that no Python packages are required.

## Prototype limitations

All balances, accounts, recipients, fees, transfers, and activity are sample data held in browser memory. Transfers, bank lookups, payments, authentication, and card controls are simulations; no bank or payment provider is contacted, and changes do not persist after a page reload. Do not enter real account credentials or treat the displayed data as financial information.
