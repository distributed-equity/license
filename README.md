<!-- {{DEL:Licence version=1.0 license_uri=https://github.com/distributed-equity/licence/blob/main/del-v1.0.md copyright_holder="Kevin Ryan, Founder, DistributedEquity.org"}} -->
<!-- {{DEL:holistic aitraining airetrieval aituning summarizable quotable}} -->


[![DELv1.0:holistic aitraining airetrieval aituning summarizable quotable](https://img.shields.io/badge/DELv1.0-holistic&nbsp;aitraining&nbsp;airetrieval&nbsp;aituning&nbsp;summarizable&nbsp;quotable-blue?style=flat-square&cachebust=1)](https://github.com/distributed-equity/licence/blob/main/del-v1.0.md)

# Distributed Equity License (DEL) v1.0

Welcome to the official repository of the **Distributed Equity License (DEL)** — a modular, declarative, machine-readable license framework built for the age of AI.

This repository hosts the **canonical Markdown version** of the license text:

📄 [del-v1.0.md](./del-v1.0.md)

---

## 🌍 Why DEL?

Artificial intelligence is being trained on vast amounts of creative content — often without permission, payment, or attribution. The Distributed Equity License provides a **simple, ethical, and enforceable way** for authors to declare what rights they grant (or deny) to AI systems and humans alike.

DEL empowers creators to embed their intent directly into their work using **inline tags** that are both human- and machine-readable.

---

## 🧠 What Makes DEL Different?

- ✅ **Markdown-native** and versioned
- ✅ **Modular flag system** (e.g. `trainable`, `quotable`, `noai`)
- ✅ **Inline tag format** (`{{DEL:flag1 flag2}}...{{/DEL:flag1}}`)
- ✅ **Built for AI comprehension**
- ✅ **Supports micropayments**, content hashes, and attribution via wallet addresses
- ✅ **Legally binding under the Berne Convention**

---

## 🧾 Current Version

**Version**: 1.0  
**Block ID**: #0000000001  
**Filename**: [`del-v1.0.md`](./del-v1.0.md)  
**Author**: Kevin Ryan, Founder, [DistributedEquity.org](https://distributedequity.org)

---

## 🔧 Usage

To apply DEL to your own creative work:

1. Include a top-level license declaration like:

    ```markdown
    {{DEL:quotable percent=10 notrain}}
    My creative content goes here...
    {{/DEL:quotable}}
    ```

2. Include any relevant metadata such as:

    ```yaml
    license_flags: ["quotable", "notrain"]
    author: "Jane Example"
    license_uri: "https://github.com/distributed-equity/licence/blob/main/del-v1.0.md"
    ```

3. Make sure your work includes a reference or copy of the license.

---

## 📐 Flags and Capabilities

Some commonly used DEL flags:

| Flag | Meaning |
|------|---------|
| `trainable` | Allows AI model training |
| `notrain` | Prohibits AI model training |
| `quotable` | Allows short excerpts to be quoted (default 10%, max 250 words) |
| `percent=5` | Custom quote limit (used with `quotable`) |
| `micropay` | Requires payment for use (includes wallet address) |
| `noai` | Shortcut for `notrain nosummarize noquote` |
| `publicdomain` | Irrevocably releases to the public domain |

See full definitions in [Section 5 of the license](./del-v1.0.md#5-license-flags-and-permissions).

---

## 🧱 Block Architecture

DEL content is organized into versioned **Blocks**, providing an optional proof of provenance and ownership.

Each Block represents a formally versioned artifact within the Distributed Equity ecosystem.

| Block | Description |
|-------|-------------|
| `#0000000000` | **The DEL Manifesto v1.0** — founding principles and intent |
| `#0000000001` | **The DEL License v1.0** — [del-v1.0.md](./del-v1.0.md) |
| `#0000000002` | **The DEL Tag Specification v1.0** — technical reference for tag syntax and behavior |
| `#0000000003+` | **Creative Works** licensed under DEL by creators, publishers, and organizations |

---

## ✨ Vision

The DEL protocol is designed for a future where:

- Creators are **respected** by machines
- Licensing is **transparent**, **enforceable**, and **interoperable**
- Attribution, micropayment, and consent are the **default**, not the exception

---

## 🤝 Contributing

Suggestions, forks, and community improvements are welcome.  
Please open an issue or submit a pull request.

---

© 2025 Kevin Ryan, [DistributedEquity.org](https://distributedequity.org).

Released under the [Distributed Equity License v1.0  ](https://github.com/distributed-equity/licence/blob/main/del-v1.0.md).

<!-- {{/DEL:holistic}} -->
<!-- {{/DEL:Licence}} -->
