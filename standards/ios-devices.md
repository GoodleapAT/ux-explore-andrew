# iOS devices

**Scope:** any work that builds, runs or checks an iOS app, in any project.

**Surfaces:** Claude Code on a Mac with Xcode. Other surfaces can skip this file.

**How hard to hold this.** The first rule is **Always**. The rest are **Default**. Markers mean: **Always**, breaking it is a defect and you say so first. **Default**, do it unless you have a reason and say the reason. **Prefer**, a leaning.

**Learned from:** 15 Nov 2026, Field Copilot hackathon. A session told Andrew twice that it could not see or tap his real iPhone. It then wrote this standard naming Xcode's MCP server (`xcrun mcpbridge`) as the way to tap, which was a guess. The method Andrew actually uses on his personal computer, for the sketch app's iPad, is the one below.

**Replaced, 15 Nov 2026:** the first version said to drive the phone through `xcrun mcpbridge` and its `DeviceInteraction` tools. That was not the method in use, so the rule is withdrawn. The MCP server stays registered; it is not how we tap.

---

## The rules

- **Always: check Apple's own developer tools before saying a real iPhone cannot be seen or
  controlled.** `xcrun devicectl` and `xcodebuild` reach a paired phone. The desktop app's iOS Simulator
  tool does not, and its limits are not the machine's limits. The first check is whether
  `xcrun devicectl list devices` shows the phone at all.
- **Default: before any run, check the phone is unlocked.**
  `xcrun devicectl device info lockState --device <UDID> -q -j /dev/stdout`. Only an explicit
  `"passcodeRequired": false` counts as ready; anything else, stop and ask Andrew to unlock it. A locked
  or sleeping phone makes `xcodebuild` hang without saying why.
- **Default: these need nothing set up beyond pairing.**
  - Screenshot: `xcrun devicectl device capture screenshot --device <UDID> --destination <file>.png`.
    Look before asking Andrew what is on the phone.
  - Install: `xcrun devicectl device install app --device <UDID> <App.app>`.
  - Launch with logs: `xcrun devicectl device process launch --device <UDID> --console <bundle.id>`
    streams the app's output back to the Mac.
  - Pull a file: `xcrun devicectl device copy from --device <UDID> --domain-type appDataContainer
    --domain-identifier <bundle.id> --source Documents/<file> --destination ./<file>`.
- **Default: tap and swipe with an XCUITest driver run by `xcodebuild`.** A UI-test target holds one
  test that reads a list of steps from an environment variable (`launch`, `tap <label>`, `tapxy x y`,
  `drag`, `hold`, `type`, `wait`, `tree`, `shot <name>`) and carries them out. Build once with
  `xcodebuild build-for-testing -destination id=<UDID>`, run with
  `TEST_RUNNER_STEPS="..." xcodebuild test-without-building -only-testing:<target>/Driver/testSteps
  -resultBundlePath run.xcresult`, then pull the screenshots with
  `xcrun xcresulttool export attachments`. The sketch app's `tools/ipad-drive.sh`,
  `tools/ipad-lock.sh` and `ios/SketchUITests/Driver.swift` are the working example.
  On the work Mac, the Field Copilot driver is `fc-phone-driver/`, beside the other repos; run its
  `drive.sh "activate; tree; shot home"`. It is a separate project, changes nothing in the app, and
  its README says how a teammate opts in with their own phone and team.
- **Default: the driver does not have to live in the app's project.** It opens the app with
  `XCUIApplication(bundleIdentifier:)`, which drives any installed app. A separate small Xcode project,
  a do-nothing host app plus a UI-test target pointed at the app's bundle ID, taps an app without
  touching its code. Use that where the app's repository is not ours to change.
- **Default: tap by accessibility label, not coordinates.** Give the app's controls accessibility
  identifiers where we own the code.
- **Default: one-time phone setup.** Pair in Xcode over USB first, then Developer Mode (Settings >
  Privacy & Security), then Settings > Developer > UI Automation, without which nothing can tap. Builds
  need a signing team and `-allowProvisioningUpdates`.
- **Default: known gotchas.** A phone lying flat reports no orientation, so set it before any gesture.
  "Automation mode" in an error means UI Automation is off; "Unlock … to Continue" means the phone
  locked mid-run. Some system gestures, such as a two-finger tap, never reach the app; use an in-app
  control instead.
- **Default: check the phone yourself rather than asking Andrew to look.** He expects Claude to see
  and use the device, as it does on his personal computer.
- **Default: do not use iPhone Mirroring.** Andrew does not use it, and it means taking over the Mac's
  screen.
