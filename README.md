### Full-stack developer. I build, ship and run my own mobile apps, end to end.

Product, mobile, backend, infrastructure and the AI features, all of it in production, with real users and paying
subscribers. The apps' code is private (it is the business), so the repos pinned below are pieces of it, extracted
and generalised so they run on their own, with tests.

#### Apps in production

| App | What it is | Notable engineering |
|---|---|---|
| **Wallstudio – Live Wallpapers** · [App Store](https://apps.apple.com/app/id6757434029) · [Google Play](https://play.google.com/store/apps/details?id=com.wallpics.nova) | Live and static wallpapers, home and lock screen widgets, charging animations, an AI wallpaper studio | Own native plugins (Swift / Kotlin) for wallpapers, widgets and charging. AI images on Flux, charged from a **server-side credit wallet**. The catalog is translated automatically with Claude |
| **Rein: App Blocker** · [App Store](https://apps.apple.com/app/id6828685068) | Screen-time and app blocking | Native Screen Time extensions alongside a Vue / Capacitor UI. Maintenance mode never locks the user inside a block |
| **Selah** *(in development)* | Guided audio prayer, the Bible and an AI companion | A **Claude agent** with Bible search and in-app actions that quotes only real text, never from memory; narrated prayers from the **narration pipeline** |

All of them run on **one backend I built and operate**: Laravel 12 + Firestore + Cloud Storage on a Google Cloud
VM, with an admin panel (Vue 3 + Vuetify) for every app's content, settings, push notifications, community moderation,
and growth dashboards (RevenueCat + Meta Ads).

#### Pinned: code you can read

- [**streaming-tool-agent**](https://github.com/superdev150/streaming-tool-agent): a tool-using Claude agent in PHP
  with grounded answers, UI actions validated on the server, NDJSON streaming and prompt caching; tested offline against
  a scripted model
- [**credit-wallet**](https://github.com/superdev150/credit-wallet): a virtual-currency wallet with an append-only
  ledger and one-time claims. Races are tested with an in-memory store that has Firestore's transaction semantics
- [**narration-pipeline**](https://github.com/superdev150/narration-pipeline): markdown to TTS with exact
  per-sentence timestamps for any provider, EBU R128 loudness, and a music mix of identical length
- [**firebase-id-token-verifier**](https://github.com/superdev150/firebase-id-token-verifier): spec-complete Firebase
  token verification and an admin gate (verified e-mail, trusted provider)
- [**zero-downtime-deploy**](https://github.com/superdev150/zero-downtime-deploy): build off-box, ship over one SSH
  connection through IAP to a key that can only deploy, and swap atomically; tested with 29 checks

#### Stack

**Mobile:** Vue 3 · Ionic · Capacitor · Swift / WidgetKit · Kotlin · RevenueCat · AdMob · FCM
**Backend:** PHP 8 / Laravel · Firestore · Cloud Storage · Node.js · ffmpeg
**AI:** Claude API (agents, tool use, caching) · OpenAI · fal.ai (Flux, audio models) · Google Cloud TTS
**Ops:** Google Cloud (Compute, IAP, IAM) · nginx · GitHub Actions (self-hosted runners)

I'm happy to walk through the private code on a call.
