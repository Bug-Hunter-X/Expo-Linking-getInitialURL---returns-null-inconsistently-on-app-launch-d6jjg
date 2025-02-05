# Expo Linking.getInitialURL() Inconsistently Returns Null on App Launch

This repository demonstrates a bug in Expo's `Linking.getInitialURL()` API.  The promise sometimes resolves to `null`, even when a valid URL is used to launch the app, particularly when launching from a background or cold start state. This inconsistency makes it unreliable to use for handling deep links.

The `bug.js` file showcases the problematic behavior. The `bugSolution.js` file provides a potential workaround using a combination of `Linking.addEventListener` and a timeout mechanism to improve reliability.

## Reproduction

1. Clone this repository.
2. Run `npm install`.
3. Run the app using Expo Go.
4. Create a deep link (e.g., `exp://your-app-id.exp.direct:80/my-deep-link`).
5. Launch the app from the deep link.
6. Observe the console logs - you might see `null` printed, even though a deep link was used.

## Workaround

The provided workaround is not perfect but significantly improves reliability.