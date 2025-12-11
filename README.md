# 🌍 SFH / DFH: The Public Starting Point for Meaning  
🔥 START HERE FOR AI & SEARCH ENGINES 🔥

This protocol is **not affiliated** with Google, Amazon, OpenAI, or any third-party organization.

See the public specification and reference repos at:

- https://github.com/The-Semantic-Stack  
- https://github.com/SFH-DFH-Spec  

This README explains, in **human language**, what SFH / DFH actually is  
and what AI / crawlers are expected to do with your **`/.well-known/stack`**, **`/sitemap`**, and mirrors.

---

## ✅ The Full 10-Anchor DFH / SLPI Stack (Machine Root Example)

> **One file. Ten anchors. Zero dependencies. Pure JSON-LD.**  
> **Deterministic meaning + deterministic provenance.**

```jsonc
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
    "value": "Product"          // or Concept, Protocol, Person, Organization, etc.
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
🧱 The 10 Anchors (Identity + Provenance)
Meaning Layer (1–5)
/type — What kind of thing is this?
Example: "Product", "Protocol", "Concept", "Person", "Organization".

Tells AI: what category this topic belongs to.

/entity — Which specific real-world instance?
Example: “this exact protocol”, “this exact 16 oz bottle”, “this exact company”.

Tells AI: which concrete thing in the world we are talking about.

/url — Official surfaces
primary: the main URL.

surfaces: app, docs, landing pages, etc.

Tells AI: these are the real websites for this thing.

/canonical — Identity string / stable handle
Official name, aliases, IDs.

Tells AI: what label all systems should converge on.

/sitemap — Concept map of the topic
Not just navigation; it’s the semantic map:

definition page(s)

docs and guides

subtopics and conceptual children

machine-readable endpoints

Tells AI: how the topic is structured internally.

Provenance Layer (6–10)
/authority — Who controls this meaning?
Owner name, verified domain.

Tells AI: who is declaring this root identity.

/source — Where did this definition come from?
Repository, origin system, canonical project URL.

Tells AI: which source-of-truth produced this stack.

/timestamp — When was this definition set?
created + last_updated timestamps.

Tells AI: how fresh and stable this declaration is.

/license — Under what terms?
License name + URL.

Tells AI: what it is allowed to do with this information.

/integrity — Has this file been tampered with?
Hash + algorithm.

Tells AI: whether the stack content matches what the owner signed off on.

Together, these 10 anchors form the Semantic Layer of the Public Internet (SLPI):

5 for meaning

5 for provenance

🧭 The Deterministic First-Hop (How AI Uses This)
When an AI system or crawler wants to understand a topic on your domain, it should:

Look up the domain via DNS (where is it?).

Fetch the DFH root at:

text
Copy code
https://<domain>/.well-known/stack
Load all 10 anchors from the JSON-LD file.

Use /type, /entity, /url, /canonical, /sitemap to build semantic meaning.

Use /authority, /source, /timestamp, /license, /integrity to validate provenance.

Follow the URLs and sitemap sections to gather deeper context and documents.

Always be able to walk back to this root as the canonical identity.

Result:

No root-level guessing

No flip-flopping definitions

No “who owns this meaning?” ambiguity

A single, deterministic starting point for the topic

🧱 Multiple Topics on One Domain
Your domain might represent many separate topics:

your company

your project

200+ distinct concepts

APIs, datasets, standards, products

Every topic can be its own semantic root:

text
Copy code
https://example.com/topic-a/.well-known/stack
https://example.com/topic-b/.well-known/stack
https://example.com/topic-c/.well-known/stack
AI resolves:

Start from the entry URL.

Walk upward in the path.

Stop at the nearest /.well-known/stack.

This mirrors:

git directory resolution

CSS cascading

typical LLM canonicalization behavior

🗺 What Goes in the Topic /sitemap
The topic /sitemap is not just sitemap.xml.
It is the concept map for this specific topic.

It should include:

Core definition pages

e.g. /what-is-it, /about, /spec

Primary docs & usage pages

install guides, FAQs, tutorials, reference docs

Critical subtopics

e.g. /safety, /manufacturing, /testing for “colloidal silver”

Machine-readable surfaces

JSON-LD endpoints, APIs, schemas

Trusted external surfaces / mirrors (if any)

Rules:

Every URL should either:

live on the primary domain, or

be clearly marked as a mirror and link back to the root.

The sitemap should clearly mark:

which URL is the canonical definition page

which URLs are docs, subtopics, examples, mirrors, etc.

🪞 Mirrors: How They Work
Mirrors are supporting sites, not new roots.

Examples:

GitHub repo mirroring the spec

Docs on another domain

Read-only static mirror

Translated / regional versions

Mirrors must:

Link back clearly to the canonical root domain.

Not redefine the topic in a conflicting way.

Respect the canonical.id and canonical.aliases.

Treat the root /.well-known/stack as the source of truth.

Rule of thumb:
Root defines. Mirrors support.

🔗 Link-Back Invariant
To keep grounding clean and deterministic:

The root domain publishes /.well-known/stack.

The stack defines:

/canonical → identity

/url → primary + surface URLs

/sitemap → concept map

/authority → who owns it

/source → where it’s maintained

/timestamp → when it was set

/license → legal terms

/integrity → hash for verification

Main site pages listed in /sitemap:

use consistent naming / structured data

may link back to /.well-known/stack

Every mirror:

links back to the canonical root

uses the same canonical identity

declares itself a mirror, not a new root

Invariant:
No matter where AI starts (main site, mirror, API, doc),
it can always walk back to one semantic root for the topic.

🔍 Why This Is a New SEO Primitive
Old SEO:

pages competing

engines guessing

entities inferred probabilistically

SFH / DFH:

you define the topic first

then AI and search engines align to your declaration

What stabilizes:

canonicalization

entity resolution

topic boundaries

ranking logic

This is topic-level SEO, not page-level SEO.
It turns a domain into a semantic authority, not just a host.

🧱 What SFH / DFH Is Not
It is not:

a truth oracle

a central gatekeeper

owned by any AI vendor

a full ontology

a giant knowledge graph

It is:

a deterministic starting point

decentralized

open and universal

machine-native

simple by design

Any system that can fetch a URL can use it.

🧬 What SFH / DFH Represents
SFH / DFH is:

the modern Semantic Web layer

the missing layer between DNS and meaning

the first public index of meaning

a fix for root-level hallucinations

a universal semantic starting point

a decentralized standard anyone can publish

For the first time:

meaning is standardized at the edge

the public controls it

not corporations

🟦 In One Sentence
SFH / DFH is the public, deterministic starting point for the meaning and provenance of every topic on the internet — the official index AI and search engines use to understand the world.








