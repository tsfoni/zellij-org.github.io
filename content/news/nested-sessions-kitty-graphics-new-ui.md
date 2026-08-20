---
author: "Aram Drevekenin"
authorlink: "https://hachyderm.io/@imsnif"
date: 2026-08-19
linktitle: "Zellij 0.45.0: nested sessions, Kitty graphics, a fresh UI"
type:
- post
- posts
title: "Zellij 0.45.0: nested sessions, Kitty graphics, a fresh UI"
images: ["/img/version-45-social-preview.png"]
description: "Zellij inside Zellij is now a first-class experience, images render inside panes with the Kitty graphics protocol, the interface gets a redesign, the web client goes mobile and more..."
alttext: "A screenshot of a nested Zellij session, showing the options offered when starting Zellij inside another Zellij session"
tags: ["release", "feature", "nested-sessions"]
weight: 10

---

{{<video-left-aligned "/video/version-045-intro.mp4">}}

Zellij 0.45.0 has just been released! [Check it out!](https://github.com/zellij-org/zellij/releases/tag/v0.45.0)

Some highlights:

- [Nested Sessions](#nested-sessions)
- [Kitty Graphics Protocol](#kitty-graphics-protocol)
- [Mobile Web UI](#mobile-web-ui)
- [New UI](#new-ui)
- [Per-Client Tab Sizes](#per-client-tab-sizes)
- [Focus Last Pane and Fullscreen Floating Panes](#focus-last-pane-and-fullscreen-floating-panes)
- [Release Notes That Update Your Keybindings](#release-notes-that-update-your-keybindings)
- [ADDENDUM: we're building Zellij.online!](#were-building-zellijonline)
- [Please Support the Zellij Developer](#please-support-the-zellij-developer-) ❤️

## Nested Sessions
{{<figure src="/img/nested-sessions-demo.gif" width="900px;" alt="An animated gif demonstrating nested sessions">}}

Running Zellij inside Zellij has often been an awkward experience: doubled status bars, keybindings going to the wrong session and a lock mode dance to get anything done. With remote sessions becoming more prominent (eg. when attaching to a remote machine over HTTPS), this happens more and more often.

This release adds dedicated handling of nested sessions. Zellij now detects when it is started inside another Zellij session and offers a choice:

1. **Zoom in and control the nested session** - the nested session takes up the whole screen and can be toggled on and off, essentially becoming your main session until you decide otherwise. Toggling can be done with: `Ctrl o` + `f` (or by clicking the parent session name in the UI breadcrumbs on the tab bar).
2. **Control the nested session on focus** - whenever the pane containing the nested session gains focus, keybindings are sent directly to it. You can then ascend back to the outer session with `Ctrl o` + `]`, or descend into it again with `Ctrl o` + `[`.

## Kitty Graphics Protocol
{{<figure src="/img/kitty-graphics-demo.png" width="900px;" alt="A screenshot of images rendered inside Zellij panes using the Kitty graphics protocol">}}
Zellij now implements the [Kitty graphics protocol](https://sw.kovidgoyal.net/kitty/graphics-protocol/) in addition to the existing Sixel support. Images displayed by image viewers, plotting libraries and documentation tools are rendered inside panes - and keep working when those panes are scrolled, moved, resized or stacked.

The host terminal needs to support the protocol as well. A personal recommendation for those interested in this feature is [WezTerm](https://github.com/wezterm/wezterm).

## Mobile Web UI
{{<figure src="/img/mobile-ui-demo.png" width="900px;" alt="A screenshot of the Zellij web client running on a phone, showing the dedicated mobile interface">}}
The built-in web client now has a dedicated mobile interface. It provides touch controls and a layout adapted to small screens, making sessions truly usable from a phone or a tablet. Sessions and panes can be switched directly from this interface.

The web client can now also be installed as a standalone app (PWA) directly from the browser - which can be a nice trick to add desktop shortcuts to specific sessions.

*Check out the [web-client screencast](/tutorials/web-client) if you'd like to learn more.*

## New UI
{{<figure src="/img/stacked-lists-demo.gif" width="900px;" alt="An animated gif demonstrating the new stacked lists feature, where pane titles in a stack appear fixed above the stack rather than split above and below.">}}
The default Zellij interface has been redesigned.

**Title frames:** pane frames are now off by default, leaving only the title line if there is more than one pane in a tab. For a single pane, the tab's title will be the pane's title. The result is a cleaner look and more room for your terminals. If you prefer the classic look, opt out with:

```javascript
pane_frame_style "full"
```

**Stacked lists:** pane stacks have been redesigned to appear as a compact list above the whole stack, allowing the full list of panes to be seen in one place rather than both above and below the expanded pane. To go back to the previous behavior:

```javascript
stacked_pane_list false
```

*For more info about how to better use stackes, check out the [Stacked Resize Screencast/Tutorial](/tutorials/stacked-resize/)*

## Per-Client Tab Sizes
Tabs can now have different sizes for different clients. When several clients are attached to the same session and are focused on different tabs, each tab is sized to its own client. Previously, all tabs shared the size of the smallest client - meaning one person attaching from a laptop would shrink everyone's screen. Now tabs are only shrunk when clients are actually focused on the same tab.

## Focus Last Pane and Fullscreen Floating Panes
A new action returns focus to the pane that was focused before the current one, so that two panes can be alternated with a single keypress. By default: `Ctrl p` + `;` (or `Ctrl g` + `p` + `;` for "unlock-first").

In addition, floating panes can now be made fullscreen, just like tiled panes. The focused floating pane expands over the whole viewport, or over the entire screen when hiding the UI.

## Release Notes That Update Your Keybindings
Some of the features above come with new keybindings that will not be present in existing config files. Rather than asking everyone to edit their config by hand, the release notes screen that pops up after an update now detects which of these keybindings are missing and offers to add them to your config file with a single keypress.

## We're building Zellij.online!
For the past few months, some of the maintainers have been working on [Zellij.online](https://zellij.online). An online terminal sharing and streaming service, currently in closed beta. Check it out if you find the idea interesting. You can also [read more](/zellij-online) about its relationship to the Zellij project now and in the future.

## Please Support the Zellij Developer ❤️
Zellij is a labor of love and is provided free and open-source to anyone who wishes to use it.

Zellij will never display ads or collect your data.

To help sustain the project, please consider a recurring donation so that the developer can pay their bills: https://github.com/sponsors/imsnif
