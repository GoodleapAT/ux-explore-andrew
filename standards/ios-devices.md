# iOS devices

**Scope:** any work that builds, runs or checks an iOS app, in any project.

**Surfaces:** Claude Code on a Mac with Xcode. Other surfaces can skip this file.

**How hard to hold this.** The first rule is **Always**. The rest are **Default**. Markers mean: **Always**, breaking it is a defect and you say so first. **Default**, do it unless you have a reason and say the reason. **Prefer**, a leaning.

**Learned from:** 15 Nov 2026, Field Copilot hackathon. A session told Andrew twice that it could not see or tap his real iPhone, first because the simulator tool is simulator only, then because "something else" must do the tapping on his personal computer. Both were wrong. Xcode itself provides both, with nothing extra installed.

---

## The rules

- **Always: check Xcode's own tools before saying a real iPhone cannot be seen or controlled.** Xcode
  27 ships an MCP server that reaches a physical device. The desktop app's iOS Simulator tool does not,
  and its limits are not the machine's limits.
- **Default: drive a physical phone through Xcode's MCP server.** It is `xcrun mcpbridge`, registered
  once per Mac at user scope with `claude mcp add --scope user xcode -- xcrun mcpbridge`. Its
  `DeviceInteractionStartSession` and `DeviceInteractionSynthesize` tools tap, swipe and type on the
  phone and return a screenshot; `DeviceInteractionInstallAndRun` builds and launches on it. Xcode must
  be open, and Xcode may ask Andrew to approve the agent the first time. A session only loads the tools
  when it starts, so a session that registered it hands device work to a new one.
- **Default: a screenshot alone needs nothing set up.** `xcrun devicectl list devices` finds the phone,
  and `xcrun devicectl device capture screenshot --device <id> --destination <file>.png` takes the
  screen. Use it to look before asking Andrew what is on the phone.
- **Default: check the phone yourself rather than asking Andrew to look.** He expects Claude to see
  and use the device, as it does on his personal computer.
- **Default: do not use iPhone Mirroring.** Andrew does not use it, and it means taking over the Mac's
  screen.
