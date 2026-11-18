# Changelog

What changed in each release of the PluggedIn Desk Bridge, newest first.
Downloads are on the [releases page](https://github.com/pluggedin-tech/pluggedin-bridge-app/releases).

When you release: add a `## [x.y.z] - YYYY-MM-DD` section here before tagging.
The release workflow copies that section into the GitHub release notes, and
stops before building if the section is missing.

## [0.7.0] - 2026-11-18

### Security
- Your pairing token is now encrypted by your computer's own secure storage
  (Windows credential protection, the macOS Keychain, or the Linux keyring)
  instead of being saved as plain text. If you paired with an earlier version,
  the token is encrypted the first time 0.7.0 starts. You don't need to pair
  again.
- Updated the app's underlying browser engine (Electron 31 to 45). Version 31
  no longer received security fixes.

### Notes
- On a Mac, the first launch may ask whether PluggedIn Desk Bridge can use your
  Keychain. Choose **Always Allow**. The app isn't code-signed yet, so macOS may
  ask again after each update.
- If you copy the app's settings to another computer, the saved token can't be
  read there. The app shows the pairing screen and you pair again.

## [0.6.2] - 2026-11-18

Everything in 0.6.1, which was never published. No other changes to the app.

### Added
- A download for Intel Macs. Macs now get two: `-arm64.dmg` for Apple Silicon
  (M1 and later) and the plain `.dmg` for Intel. Earlier releases had Apple
  Silicon only.

## [0.6.1] - 2026-11-18

Tagged but never published: GitHub couldn't provide a Mac build machine. Its
changes shipped in 0.6.2.

### Fixed
- Pairing works out of the box. Earlier versions were set up to look for
  PluggedIn on the computer itself, so pairing failed unless you found
  **Advanced** and typed the server address. The app now connects to
  trypluggedin.com, and an old saved address is cleared automatically.
- After you load a patch from a file, changing the Patch or Layout selector no
  longer swaps your file for the previously selected event.

### Security
- The app only connects to PluggedIn over https, so your token is always
  encrypted in transit. A plain http address is refused unless it's on this
  computer (for development).
- The app window can only show the app itself: it can't be navigated to a
  website, open new windows, or use the camera, microphone or similar.

## [0.6.0] - 2026-06-23

### Changed
- Live push now covers only the desks proven to accept it: Behringer X32 /
  Midas M32, and Behringer X-Air / Midas M-Air (beta).
- For other desks, download the patch file from the event page in PluggedIn.

### Removed
- Live push for Yamaha CL/QL and Allen & Heath SQ/dLive, pending tests on real
  hardware. Their patch files on the event page are verified instead.
- The Allen & Heath Show CSV download, which moved to the event page.

## [0.5.1] - 2026-06-22

### Added
- Load one band's patch between sets, not just the whole night. Pick the band
  in the new **Patch** selector, then choose **Layout**: on that band's master
  patch channels, or as a fresh scene starting at channel 1.

## [0.5.0] - 2026-06-21

### Added
- A **Console** selector, which sets the network port for you and pre-selects
  the venue's saved desk.
- Live push for Behringer X-Air / Midas M-Air. Also, as betas: Yamaha CL/QL
  and Allen & Heath SQ/dLive (removed again in 0.6.0).

### Fixed
- A macOS download (Apple Silicon). 0.4.0's Mac build had failed, so it shipped
  for Windows and Linux only.

## [0.4.1] - 2026-06-18

Tagged but never published (the release build failed). Its fixes shipped in
0.5.0.

## [0.4.0] - 2026-06-18

### Added
- First desktop version, for Windows and Linux. Pair once with a code
  from PluggedIn, pick an event, enter the desk's IP address, and push channel
  names, colours, inputs and 48V to a Behringer X32 / Midas M32. You can
  preview first, or load a patch from a file to work offline.
