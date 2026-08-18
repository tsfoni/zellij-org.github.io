---
title: "Zellij.online - Hosted Session Sharing from the Zellij Maintainers"
description: "Zellij.online is a commercial hosted session sharing service run by the Zellij maintainers. Zellij itself remains free, open source and fully self-hostable."
---

## What is Zellij.online?

[Zellij.online](https://zellij.online) is an end-to-end encrypted terminal session sharing service. It lets you hand someone a link to your terminal session and have them join from their browser, their own terminal, or their phone, without setting up TLS certificates, opening ports, or configuring port-forwarding.

It is currently in closed beta.

## Who runs it, and is it commercial?

Yes, it is commercial, and it is run by the same people who maintain Zellij.

Zellij.online is operated by [Aram Drevekenin (@imsnif)](https://poor.dev), who develops and maintains Zellij full-time, as well as others from the Zellij team. It is a paid service with a free tier.

This page exists so that this is stated plainly rather than discovered later.

## What this does not change

- **Zellij stays free and open source.** Forever, under the same license. There is no "community edition" and no "pro edition".
- **No features are held back.** Nothing is removed from Zellij, or deliberately left unbuilt, in order to make the hosted service more attractive.
- **The built-in web client stays fully featured.** Session sharing over your own infrastructure remains a first-class, documented, supported path. See the [web client tutorial](/tutorials/web-client) and the [web client documentation](/documentation/web-client.html).
- **No ads, no telemetry, no data collection.** Unchanged, and not up for revision.
- **No account is required to use Zellij.** Zellij is free, standalone software. It will not require any sort of online presence.

## Why a paid service at all?

Zellij is developed full-time, and funded entirely by recurring donations and the savings of the maintainers. That funding model works, but it is fragile, and it scales poorly with the amount of work the project requires.

The realistic alternatives for funding an open source project at this size are advertising, venture capital, selling user data, or selling a service. Selling a service is the only one of those that does not degrade the project or its users, so that is the one being tried.

Zellij.online is not funded by venture capital or private equity. We believe such a funding model invariably prefers the interests of investors over the interests of the users and the community at large.

Revenue will go towards maintaining the service and sustaining full-time work on Zellij.

## I would rather host it myself

That is already possible, and it is not going to become second-class.

Zellij includes a built-in web-server with remote session attach through the browser or the terminal. You can run it on your own machine or your own server, with your own certificates, and share sessions without any third party involved:

- [The Zellij Web Client tutorial](/tutorials/web-client) walks through setup, HTTPS, and authentication tokens
- [Web client documentation](/documentation/web-client.html)
- [Remote session access](/features/#remote-session-access)

The hosted service exists for people who do not want to do that, not to discourage people who do.

## Other ways to support Zellij

If you want to support the project directly rather than through a service:

- [Become a sponsor on GitHub](https://github.com/sponsors/imsnif)

## Join the beta

Zellij.online is not generally available yet. If it sounds cool, you can put your name on the waiting list at [zellij.online](https://zellij.online).
