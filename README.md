# Session Desktop: Full-Screen Calls and Screen Sharing

This repository packages ARF's focused patch for Session Desktop. It adds a dedicated full-screen call view and lets a user select a window or display to share during a one-to-one call. It includes the call lifecycle, capture permission handling, and unit tests.

This is a source patch, not a standalone application or installer. The enhancement is a contribution to Session Desktop and is distributed under the upstream project's GNU General Public License, version 3. See the [upstream license](https://github.com/session-foundation/session-desktop/blob/dev/LICENSE) and [contribution terms](https://github.com/session-foundation/session-desktop/blob/dev/CONTRIBUTING.md).

## Source and status

- Upstream project: https://github.com/session-foundation/session-desktop
- ARF pull request: https://github.com/session-foundation/session-desktop/pull/2065
- Patch base: `3bfb0f1c3c4779bcb420b94b7f92a855571cc97d` (Session Desktop 1.18.5)
- Patch revision: `c24cff743fb6b58cbd607ad2562da9393f2235cf`

## Install and run from source

The commands below use the exact public upstream base and pinned Node and pnpm versions (Node 24.22.1 and pnpm 10.28.1). Install those versions first, then run:

```sh
git clone https://github.com/arf-io/session-desktop-enhancements.git
git clone https://github.com/session-foundation/session-desktop.git
cd session-desktop
git checkout 3bfb0f1c3c4779bcb420b94b7f92a855571cc97d
git submodule update --init --recursive
git apply ../session-desktop-enhancements/session-desktop-fullscreen-screen-share.patch
pnpm install
pnpm build
pnpm start-prod
```

The application launches from source. Follow the [upstream platform prerequisites](https://github.com/session-foundation/session-desktop/blob/3bfb0f1c3c4779bcb420b94b7f92a855571cc97d/README.md). On macOS, allow Screen Recording access if the operating system asks for it.

## Try the feature

1. Start a one-to-one call.
2. Choose **Full Screen** from the call controls. Press **Escape** to return to the app window; the call continues.
3. Choose screen sharing and select a window or display from the picker. Confirm any operating-system permission prompt.
4. Choose **Stop sharing** to return to the camera view.

Screen capture is user-initiated and controlled by native OS permission. This patch does not add covert capture or remote monitoring.
