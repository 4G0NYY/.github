<div align="center">

# heya, i'm Raymond (4G0NYY) | hi hi :3

### *just a guy who's far too bored, building things the world didn't ask for* ♡

`Zürich, Switzerland` · `Cloud-Native Engineer` · [`agony.ch`](https://www.agony.ch) · [`discord`](https://discord.gg/gpt4k7jBbv)

![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![Python](https://img.shields.io/badge/Python-2b2b2b?style=for-the-badge&logo=python&logoColor=ffd343)
![TypeScript](https://img.shields.io/badge/TypeScript-2b2b2b?style=for-the-badge&logo=typescript&logoColor=3178c6)
![Go](https://img.shields.io/badge/Go-2b2b2b?style=for-the-badge&logo=go&logoColor=00add8)
![React](https://img.shields.io/badge/React-2b2b2b?style=for-the-badge&logo=react&logoColor=61dafb)
![Docker](https://img.shields.io/badge/Docker-2b2b2b?style=for-the-badge&logo=docker&logoColor=2496ed)

</div>

---

## `> whoami` ( ˶ ˆ ᗜ ˆ ˶ )

so basically i build stuff when i'm bored, which is like… all the time T.T i'm probably a *tad* too arrogant and *definitely* too weird for polite company, but i've made my peace with that. **be cringe, be free** >w<

i don't really do "the accepted way" of doing things. if a convention stands between me and the thing i actually want, i will politely walk around it, through it, or occasionally *reimplement it from scratch just to prove i can*. perfection isn't a feature request, it's a vibe, and i chase it way too hard for someone who started every one of these projects out of pure boredom :P

i self-host most of my nonsense on my **own DNS server, on my own domains**, because why would i let someone else hold the keys ( ˘ ³˘) currently grinding through an **HF Cloud-Native Engineer** program, which is a fancy way of saying i get graded on things i was going to overbuild anyway ehe.

---

## 🩸 the crimson haven saga — *my magnum opus of boredom*

okay so this is the big one. [**crimsonhaven.to**](https://github.com/crimsonhaven-to) is a full distributed anime-streaming *framework* i built basically because i was bored one evening and it just… never stopped >.< it's not one repo, it's a whole **ecosystem of seven**, and the architecture is genuinely the thing i'm proudest of because it does something clever:

> **the whole trick:** move the scraping, the resolving, *and the video bytes* **off the backend and into the viewer's own browser** — so hosting cost scales with your *library size*, not your *watch-hours*. bandwidth is expensive and hard to scale, so… i just refused to pay for it. ( • ̀ω•́ )✧

| repo | what it is | the flex |
|---|---|---|
| 🧠 **crimson-backend** | `FastAPI` · `PostgreSQL` · `psycopg3` · async `HTTPX` | native **TMDB ↔ AniList** metadata mapping, progressive **NDJSON `/watch`** stream (fastest source plays first), **Ed25519 mnemonic** *and* invite-gated email auth behind a site-wide login wall |
| 🏰 **crimson-client** | `React 19` · `Vite 8` · `Tailwind 4` | 12-word **seed-phrase accounts** (ed25519 + bip39) so there's no central password to steal, in-memory stream caching, and a persona-driven 404 page bc of course |
| ⚙️ **crimson-sources** | from-scratch `TypeScript` scrape/resolve engine | runs **in the browser**, emits the *exact same* NDJSON line shape the backend does so it's indistinguishable — routes each source through the cheapest environment that can actually run it via capability flags (private repo for obvious reasons ;3) |
| 🛰️ **crimson-proxy** | signed, HLS-aware CORS relay (`Nitro`, edge) | **HMAC-signed only** so nobody can hijack my free-tier bandwidth, rewrites every `.m3u8` variant/segment/key back through itself, lives on Netlify / Cloudflare Workers |
| 🦇 **crimson-extension** | Chromium MV3 companion | injects the **forbidden headers** a page can never set itself (`Referer`, `Origin`, `Cookie`, `Sec-Fetch-*`), plus hidden-tab capture for hosters that fight back. one red button. that's the whole UI :3 |
| 📖 **crimson-docs** | `Astro` | the Royal Archives, explained by Lumi herself |
| 📡 **crimson-status** | `Go` agent + `FastAPI` + `React` | agent-based infra monitoring built to **not share fate** with the things it watches, fronted by a Cloudflare Tunnel |

yes there's a recurring vampire-queen OC named **Luminas Crimsonveil** ("Lumi") narrating half of it. no i will not be explaining myself. ( ^ . ^ )

---

## 🌌 AbyssC — *because i didn't trust anyone else's entropy coder (or some deep shit like that)*

[**AbyssC**](https://github.com/4G0NYY/AbyssC) is a performance-first, modular **compression engine written entirely in Rust**. eight codecs, four containers, one CLI, one GUI, *same core underneath both*. and then, because i apparently hate free time:

- ✍️ **my own from-scratch entropy coder** (`ans.rs`) — a block-based **rANS** that owes *nothing* to any external crate. four interleaved states per block, reciprocal-multiply encoding, single-lookup decode, folded across every core >w<
- 🔐 **sealed `.abyss` archives** — `Argon2id` → `ChaCha20-Poly1305` STREAM, authenticated end to end. "the surface cannot read what it cannot open" 🩸
- 🌊 **streaming by nature** — a 100 GB file costs the same RAM as a 100 KB one
- 📖 reads the surface's forms too (`.7z`, `.rar`, `.iso`, the whole zip family) even though it refuses to *create* them, because taste

adding a codec touches exactly one file and one detection table. the rest of the engine does not stir. i think about that sentence a normal amount. ( ˶ˆ ꒳ˆ˵ )

---

## 🐛 the little goblins (smaller things i made & love anyway)

- 🤖 **countdown-bot** — a Discord bot that parses natural-language reminders (*"tomorrow at 5pm"*, *"in 3 hours"*) into SQLite-backed countdowns
- 🧛 **lumi-welcome-bot** — yes, Lumi has her own welcomer bot with full vampire-queen personality
- 📰 **Auto-News** — pulls RSS, "refines" it through AI APIs, publishes to a site, hands-off
- 🎮 **genshin-dps-calc** — honestly i don't fully know what this is either, i just wanted something to host on my own DNS server :P
- ☁️ **AbyssEngine** — a from-scratch **push-to-deploy PaaS** (webhook → build → deploy → run), my (would-be) cloud-native semester project

---

## 🛠️ the toolbox i actually reach for

<div align="center">

**languages** → Rust · Python · TypeScript · JavaScript · Go · SQL (me no likey sql tho :< )
**backend** → FastAPI · PostgreSQL · Nitro · async everything
**frontend** → React 19 · Vite · Tailwind · Astro
**infra** → Docker · Compose/Swarm · Cloudflare (Workers + Tunnel) · Netlify · self-hosted DNS
**crypto i've actually shipped** → Ed25519 · BIP39 · HMAC signing · Argon2id · ChaCha20-Poly1305

</div>

i like the low levels (writing an entropy coder, injecting forbidden headers, minting signed edge links) and i like the high levels (making a UI that a mortal can actually use). the middle is where conventions live, and the middle is negotiable ehe~

---

<div align="center">

## `> where to find me`

[![Site](https://img.shields.io/badge/agony.ch-2b2b2b?style=for-the-badge&logo=firefox&logoColor=ff5555)](https://www.agony.ch)
[![Discord](https://img.shields.io/badge/discord-2b2b2b?style=for-the-badge&logo=discord&logoColor=5865f2)](https://discord.gg/gpt4k7jBbv)
[![Steam](https://img.shields.io/badge/steam:_hardtruth-2b2b2b?style=for-the-badge&logo=steam&logoColor=white)](https://steamcommunity.com/id/hardtruth)

*if you actually want a feature, open an issue describing it, or come bother me on Discord. i genuinely might build it.* ♡

**`be cringe. be free. build the thing anyway.`** ( ˶ ˆ ᗜ ˆ ˶ ) 🩸

</div>
