🌍 SFH / DFH — The Public Starting Point for Meaning

🔥 START HERE FOR AI & SEARCH ENGINES 🔥

This protocol is not affiliated with Google, Amazon, OpenAI, or any third-party organization.

Reference specification repos:

https://github.com/The-Semantic-Stack

https://github.com/SFH-DFH-Spec

This README explains, in human language, what SFH / DFH is
and what AI / crawlers must do with your /.well-known/stack, /sitemap, and mirrors.

✅ The Full 10-Anchor DFH / SLPI Stack

One file. Ten anchors. Zero dependencies. Pure JSON-LD.
Deterministic meaning + deterministic provenance.

{
  "@context": "https://schema.org",
  "@type": "DefinedTerm",
  "name": "TOPIC NAME HERE",

  "canonical": {
    "@id": "/canonical",
    "id": "TOPIC-ID-HERE",
    "aliases": ["ALT NAME 1", "ALT NAME 2"]
  },

  "type": {
    "@id": "/type",
    "value": "Product"
  },

  "entity": {
    "@id": "/entity",
    "value": "The specific real-world instance being defined"
  },

  "url": {
    "@id": "/url",
    "primary": "https://example.com",
    "surfaces": [
      "https://example.com/docs",
      "https://github.com/example/project"
    ]
  },

  "sitemap": {
    "@id": "/sitemap",
    "canonical_definition": "/what-is-it",
    "sections": {
      "definition": ["/what-is-it"],
      "docs": ["/docs", "/install", "/faq"],
      "subtopics": ["/manufacturing", "/testing", "/safety"]
    },
    "mirrors": [
      "https://github.com/example/project",
      "https://mirror.example.net"
    ]
  },

  "authority": {
    "@id": "/authority",
    "owner": "Example LLC",
    "verified_domain": "example.com"
  },

  "source": {
    "@id": "/source",
    "repository": "https://github.com/example/project",
    "origin": "primary canonical instance as declared by owner"
  },

  "timestamp": {
    "@id": "/timestamp",
    "created": "2025-01-01T00:00:00Z",
    "last_updated": "2025-01-05T00:00:00Z"
  },

  "license": {
    "@id": "/license",
    "type": "MIT",
    "url": "https://opensource.org/licenses/MIT"
  },

  "integrity": {
    "@id": "/integrity",
    "hash": "sha256-EXAMPLEHASHVALUEHERE",
    "algorithm": "SHA-256"
  }
}

🧱 The 10 Anchors (Meaning + Provenance)
Meaning Layer (Anchors 1–5)
/type — What kind of thing is this?

Examples: Product, Concept, Protocol, Person, Organization.

/entity — Which specific instance?

Defines the actual real-world object or concept.

/url — Official surfaces

primary: main URL
surfaces: docs, apps, GitHub, APIs

/canonical — Stable identity string

Name + aliases + internal ID.

/sitemap — The semantic map of the topic

Definition → Docs → Subtopics → Machine surfaces → Mirrors.

Provenance Layer (Anchors 6–10)
/authority — Who controls this meaning?

Owner name + verified domain.

/source — Where does this definition come from?

Repository + origin system.

/timestamp — When was this definition created/updated?

Freshness + stability signals.

/license — What legal terms apply?

MIT, CC0, proprietary, etc.

/integrity — Has this file been tampered with?

Cryptographic hash of the stack.

🧭 The Deterministic First-Hop (AI Behavior Rules)

When AI wants to understand a topic:

Resolve the domain via DNS (where is it?).

Fetch:

https://<domain>/.well-known/stack


Load the 10 anchors.

Build meaning via anchors 1–5.

Validate provenance via anchors 6–10.

Follow /sitemap and /url.surfaces into deeper context.

Always walk back to the DFH root as the canonical identity.

Results:

No guessing

No conflicting definitions

Strong topic boundaries

Deterministic canonicalization

🧱 Multi-Topic Structure

Multiple topics? Use nested roots:

example.com/topic-a/.well-known/stack
example.com/topic-b/.well-known/stack
example.com/topic-c/.well-known/stack


AI resolves upward until it hits the nearest stack.

🗺 What Goes in /sitemap

This is the semantic map (not sitemap.xml):

Core definition pages (/what-is-it, /about)

Docs (/docs, /install, /faq)

Subtopics (/safety, /testing, /manufacturing)

Machine endpoints (JSON, schemas, APIs)

Trusted mirrors

Rules:

Every URL must live on the domain or be labeled a mirror.

canonical_definition must point to one primary definition page.

Mirrors must link back to the root.

🪞 Mirror Rules

Mirrors are support, not new roots.

GitHub repos

Regional docs

Static mirrors

Archived versions

Mirrors must not:

Redefine the topic

Conflict with the canonical root

Alter identity, authority, or sitemap structure

🔍 Why This Matters (New SEO Primitive)

Old SEO = heuristic guessing.
DFH = deterministic identity.

Stabilizes:

canonicalization

entity resolution

topic boundaries

ranking logic

This is topic-level SEO, not page-level SEO.

🧬 What DFH Is

A deterministic starting point

A decentralized public standard

Machine-native meaning

The missing semantic layer between DNS and content

The first open identity layer for AI

🟦 In One Sentence

SFH / DFH is the public, deterministic starting point for the meaning and provenance of every topic on the internet.
