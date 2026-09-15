# Balott Founder Source-Use Authorization

**Recorded:** 2026-09-15  
**Status:** founder/user permission assertion for Balott planning and implementation eligibility

## Authorization statement

The founder/user has explicitly stated that Balott has permission to copy, use, and adapt the source code of the external source-code projects discussed for Balott and listed in `docs/provenance/SOURCES.md` as of this planning package.

Permitted engineering postures are eligible to include:

```text
REFERENCE | COPY | ADAPT | DEPEND | VENDOR
```

This authorization is a permission input, not automatic technical adoption authority.

## Adoption law

> **Permission makes reuse eligible. Exact source + exact revision + exact path + controlling terms/permission basis + Balott reason + Balott tests make reuse adoptable.**

Before direct code incorporation, record:

- source name and canonical repository URL;
- immutable commit/tag;
- exact copied/adapted paths or dependency package/version;
- public license/notices;
- separate founder permission basis when relied upon beyond public terms;
- embedded third-party code;
- model/data/font/media/asset rights separately;
- destination paths;
- adoption mode;
- modifications;
- why reuse beats a smaller native implementation;
- security review;
- maintenance/update ownership;
- Balott-owned behavior tests.

## What this authorization does not mean

It does not mean:

- every listed source should be copied;
- a proprietary product has source bytes available merely because permission was asserted;
- trademarks/brand assets may be reused without separate scope review;
- third-party dependencies/models/assets inside a donor are automatically covered;
- public license/NOTICE obligations disappear;
- security review can be skipped;
- a source may override Balott's canonical gameplay/trust architecture;
- copied code is accepted without exact-revision testing and review.

For proprietary/source-unavailable behavioral references, Balott may study observed behavior. Direct code provenance may be claimed only when source material is actually available and can be pinned.

## Scope boundary

This record covers the source-code projects in `SOURCES.md` at the planning snapshot represented by the commit containing this file. Later sources added to the registry require either:

1. a compatible public license sufficient for the intended use; or
2. an updated founder permission record covering the added source.

Do not silently extend this authorization to unrelated future sources.
