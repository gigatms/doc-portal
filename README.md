# GIGA-TMS Document Portal

Static GitHub Pages website for the future `doc.gigatms.com.tw` document portal. The visual system follows the dark product-security style used by `security.gigatms.com.tw`.

## Two-phase document architecture

### Phase 1 — RED-DA Doc

The first phase provides a single A–Z model index, approved document metadata, signed and approved PDF downloads, and immutable historical archive URLs. Product family information such as RFID, 125 kHz and GP series remains metadata; it is not used to create separate catalogue sections under `/doc/red-da/`.

### Phase 2 — CRA Doc

CRA Doc is reserved for Phase 2 with the planning publication milestone **2027/12/11**. CRA is not an active download area in Phase 1. A future `/doc/cra/` area can be added after the relevant assessment, product-family documentation and public approval are complete.

## Public routes

- `/` — two-phase document portal homepage
- `/doc/red-da/` — Phase 1 RED-DA A–Z model index
- `/doc/red-da/archive/` — RED-DA immutable public archive
- `/security-advisories/` — product security update register and link to `https://security.gigatms.com.tw`

## Document URL rules

Current model alias:

```text
/doc/red-da/<model>.pdf
```

Immutable historical version:

```text
/doc/red-da/archive/<model>-v<version>-<yyyy-mm-dd>.pdf
```

Future CRA routes:

```text
/doc/cra/<model>.pdf
/doc/cra/archive/<model>-v<version>-<yyyy-mm-dd>.pdf
```

## GitHub Pages deployment

This repository is intended to be published through GitHub Pages using `.github/workflows/pages.yml`. The root `CNAME` reserves the future custom domain:

```text
doc.gigatms.com.tw
```

The default GitHub Pages URL is expected to be:

```text
https://gigatms.github.io/doc-portal/
```

The custom domain will require DNS records at the domain provider and the final custom-domain setting in GitHub Pages. No DNS change is performed by this repository deployment.

## Public / internal boundary

Only signed and approved RED-DA Doc or future CRA Doc records belong in the public portal. Technical files, SBOMs, security assessments, threat models, test reports, vulnerability details and OEM-confidential documents remain in controlled internal systems.

## Current status

This repository contains the planning website and placeholder document index. No official DoC PDF has been published. Before adding a PDF, complete document approval, product-model verification, version/date review, public-release approval and SHA-256 recording.

## Official links

- Company website: <https://www.gigatms.com.tw>
- Security reporting: <https://security.gigatms.com.tw>
- Future document portal: <https://doc.gigatms.com.tw>
