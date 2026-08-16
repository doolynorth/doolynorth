<div align="center">

<img src="https://raw.githubusercontent.com/doolynorth/doolynorth/main/assets/doolynorth-x-logo.png" alt="doolynorth Logo" width="220"/>

# doolynorth

**High-Performance Content Delivery Network**

[![Website](https://img.shields.io/badge/🌐_Live_Platform-doolynorth.online-F0A202?style=for-the-badge&logoColor=white)](https://doolynorth.online)
[![Status](https://img.shields.io/badge/Status-Live-22C55E?style=for-the-badge)](https://doolynorth.online)
[![License](https://img.shields.io/badge/License-MIT-3B82F6?style=for-the-badge)](LICENSE)

[![Stars](https://img.shields.io/github/stars/doolynorth/doolynorth?style=flat-square&color=F0A202&label=⭐%20Stars)](https://github.com/doolynorth/doolynorth/stargazers)
[![Forks](https://img.shields.io/github/forks/doolynorth/doolynorth?style=flat-square&color=F0A202&label=🍴%20Forks)](https://github.com/doolynorth/doolynorth/network)
[![Watchers](https://img.shields.io/github/watchers/doolynorth/doolynorth?style=flat-square&color=F0A202&label=👁️%20Watchers)](https://github.com/doolynorth/doolynorth/watchers)

<br/>

> **Deliver content at the speed of light — globally distributed, infinitely scalable, always-on.**

<br/>

**[🚀 Try the Platform](https://doolynorth.online)** &nbsp;·&nbsp;
**[📖 Documentation](#-documentation)** &nbsp;·&nbsp;
**[⚙️ How It Works](#️-how-it-works)** &nbsp;·&nbsp;
**[🤝 Contributing](#-contributing)**

</div>

---

## 🌍 What is doolynorth?

**doolynorth** is a next-generation Content Delivery Network built for the modern web. Like a beehive — where every cell works in perfect coordination — doolynorth distributes your content across a global network of nodes, ensuring **sub-millisecond delivery** anywhere in the world.

Whether you're streaming video, serving assets, or powering a global SaaS application, doolynorth handles the complexity so you don't have to.

```
User in Tokyo ──► doolynorth Edge Node (Asia) ──► Your Content in <10ms
User in Berlin ──► doolynorth Edge Node (EU) ──► Your Content in <8ms
User in NYC ──► doolynorth Edge Node (US-East) ──► Your Content in <5ms
```

---

## ✨ Features

| Feature | Description |
|---|---|
| ⚡ **Ultra-Low Latency** | Edge nodes on 6 continents, avg. response < 15ms |
| 🌐 **Global Distribution** | 100+ PoPs (Points of Presence) worldwide |
| 🔒 **DDoS Protection** | Built-in traffic scrubbing & rate limiting |
| 🔥 **Smart Caching** | AI-driven cache warming and invalidation |
| 📊 **Real-Time Analytics** | Live bandwidth, cache hit ratio, and request metrics |
| 🚀 **Auto-Scaling** | Traffic spikes handled automatically — zero config |
| 🛡️ **SSL/TLS** | Free managed certificates with auto-renewal |
| 🔗 **HTTP/3 & QUIC** | Latest protocols for maximum performance |

---

## 🎬 Demo

<div align="center">

### ▶️ [Watch Live Demo → doolynorth.online](https://doolynorth.online)

</div>

Experience doolynorth in action — configure your delivery settings, see real-time latency maps, and watch requests route to the nearest edge node live on the platform.

---

## ⚙️ How It Works

```
                         ┌─────────────────────────────────┐
                         │         Your Origin Server       │
                         └────────────────┬────────────────┘
                                          │
                         ┌────────────────▼────────────────┐
                         │        doolynorth Backbone          │
                         │   (Anycast routing + BGP mesh)   │
                         └──┬──────────┬──────────┬────────┘
                            │          │          │
               ┌────────────▼──┐  ┌────▼──────┐  ┌▼───────────────┐
               │  Edge (US)    │  │ Edge (EU) │  │  Edge (APAC)   │
               │  PoP: 32 nodes│  │ PoP: 28   │  │  PoP: 24 nodes │
               └───────┬───────┘  └────┬──────┘  └───────┬────────┘
                       │               │                  │
               ┌───────▼───────────────▼──────────────────▼────────┐
               │              End Users — Worldwide                 │
               └────────────────────────────────────────────────────┘
```

1. **Request arrives** — user's DNS resolves to the nearest doolynorth PoP via Anycast
2. **Cache check** — edge node serves cached content instantly if available
3. **Origin fetch** — on cache miss, content is pulled from origin and cached at edge
4. **Smart warming** — ML model predicts popular content and pre-caches it proactively
5. **Metrics stream** — every request logged in real-time to analytics pipeline

---

## 📦 Integration

### Quick Setup — 3 Steps

**Step 1 — Point your DNS**
```dns
; Replace your A record / CNAME with doolynorth's entry point
your-domain.com.    CNAME    cdn.doolynorth.online.
```

**Step 2 — Configure your origin**
```yaml
# doolynorth.yml
origin:
  url: https://your-origin-server.com
  timeout: 30s

cache:
  ttl: 86400          # 24 hours
  stale_while_revalidate: 3600

rules:
  - path: /static/**
    cache: true
    ttl: 604800       # 7 days
  - path: /api/**
    cache: false
    pass_headers: [Authorization, X-User-ID]
```

**Step 3 — Go live**
```bash
curl -X POST https://api.doolynorth.online/v1/deploy \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"config": "doolynorth.yml"}'
```

### SDKs

| Language | Package | Status |
|----------|---------|--------|
| JavaScript / Node.js | `npm install doolynorth` | ✅ Stable |
| Python | `pip install doolynorth` | ✅ Stable |
| Go | `go get github.com/doolynorth/doolynorth-go` | ✅ Stable |
| Scala / JVM | `io.doolynorth:client:1.0` | ✅ Stable |
| Rust | `cargo add doolynorth` | 🔄 Beta |

---

## 📊 Performance

<div align="center">

| Region | Avg. Latency | Cache Hit Rate | Uptime (30d) |
|--------|-------------|----------------|--------------|
| 🇺🇸 North America | **4.2ms** | 97.3% | 99.99% |
| 🇪🇺 Europe | **6.1ms** | 96.8% | 99.99% |
| 🇯🇵 Asia Pacific | **8.4ms** | 95.9% | 99.98% |
| 🇧🇷 South America | **11.2ms** | 94.1% | 99.97% |
| 🌍 Africa / ME | **14.8ms** | 92.3% | 99.96% |

</div>

---

## 🏗️ Architecture

doolynorth is built on a **distributed systems** foundation:

- **Routing layer** — BGP Anycast across 100+ PoPs for geo-steering
- **Cache layer** — Multi-tier LRU/LFU cache with Bloom filters for negative caching
- **Analytics layer** — Apache Presto + Apache Kudu for real-time query over streaming telemetry
- **Control plane** — Distributed config propagation via RAFT consensus (<500ms globally)
- **Data plane** — Custom eBPF-based packet processing for DDoS scrubbing at line rate

---

## 📖 Documentation

| Resource | Link |
|----------|------|
| 🌐 Platform | [doolynorth.online](https://doolynorth.online) |
| 📘 API Reference | [doolynorth.online/docs/api](https://doolynorth.online/docs/api) |
| 🚀 Quick Start | [doolynorth.online/docs/quickstart](https://doolynorth.online/docs/quickstart) |
| 🔧 Configuration | [doolynorth.online/docs/config](https://doolynorth.online/docs/config) |
| 📊 Status Page | [status.doolynorth.online](http://status.doolynorth.online) |

---

## 🤝 Contributing

We welcome contributions of all kinds — bug fixes, features, docs, and performance improvements.

```bash
# Fork → clone → branch
git clone https://github.com/doolynorth/doolynorth.git
cd doolynorth
git checkout -b feature/my-improvement

# Make changes, then
git commit -m "feat: add my improvement"
git push origin feature/my-improvement
# Open a Pull Request ↑
```

Please follow [Conventional Commits](https://www.conventionalcommits.org/) and read our [Contributing Guide](CONTRIBUTING.md).

---

## 🛡️ Security

Found a vulnerability? Please disclose responsibly:

📧 **security@doolynorth.online**

We follow a 90-day responsible disclosure policy and acknowledge all valid reports within 24 hours.

---

<div align="center">

<img src="https://raw.githubusercontent.com/doolynorth/doolynorth/main/assets/doolynorth-x-logo.png" width="48" alt="doolynorth"/>

**Built by the [doolynorth](https://doolynorth.online) engineering team**

[🌐 doolynorth.online](https://doolynorth.online) &nbsp;·&nbsp; [⭐ Star this repo](https://github.com/doolynorth/doolynorth/stargazers) &nbsp;·&nbsp; [🐛 Report a Bug](https://github.com/doolynorth/doolynorth/issues)

<br/>

*"Fast as a bee, strong as a hive."*

</div>
