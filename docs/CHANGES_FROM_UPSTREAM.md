# Changes from upstream Humanizer

This comparison describes Humanizer for ChatGPT 1.0.0 against Humanizer 3.1.0 at commit [`0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0`](https://github.com/blader/humanizer/tree/0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0). Source credit and license details are in [NOTICE.md](../NOTICE.md).

## What is retained

Both editions keep the 26 numbered patterns, their six groups, the read–revise–compare–deliver workflow, attention to the writer's voice, and protection of technical content. The original reference remains available in each skill for comparison. This is an adaptation of those ideas and instructions.

## Editorial changes

| Area | Upstream behavior | This adaptation |
| --- | --- | --- |
| Default output for pasted text | Draft, remaining-pattern critique, and final revision | Final text only; comments, diagnosis, or a full audit on request |
| Language | Primarily English guidance | English and Brazilian Portuguese editions with localized examples |
| Meaning preservation | General instruction to retain supported claims | Explicit checks for conditions, uncertainty, attribution, rankings, event order, distinct list items, and simultaneous actions |
| Worked examples | Some examples introduce more specific facts or remove distinct details | New illustrative pairs designed to preserve the substantive information |
| Voice | Allows a reaction when the voice calls for it | Preserve supplied opinions and experiences; do not invent them or transplant facts from a voice sample |
| Dashes | General ban in the final revision unless the writer's sample uses them | Review excessive generic connectors; keep purposeful punctuation, quotations, ranges, mathematical signs, and the supplied voice |
| Hyphens and grammar | English-oriented compound rules | Follow each language's grammar and established spelling; retain appropriate US or UK English |
| Common vocabulary | Several words treated as tells wherever they occur | Evaluate context and repetition; retain accurate technical terms |
| Attribution | Remove unsupported appeals to authority | Preserve who made a claim; distinguish a report quoting an opinion from endorsing it |
| Authorship | Includes a publication-date rule | No authorship inference from a phrase, punctuation mark, or publication date |
| Advertising | Remove generic sales language | Preserve the requested persuasive purpose and call to action through supplied concrete benefits |
| Distribution | Upstream agent package and platform-specific manifests | Two self-contained skill folders and two portable ChatGPT prompt files, with English public documentation |

## Scope of the software

The package consists of text instructions, reference material, examples, and interface metadata. It does not contain a model, a translation engine, a rewriting API, or a modified upstream executable program. The host language model performs the revision when given the instructions.

## Review performed

The English and PT-BR editions were checked for all 26 patterns, reference integrity, preserved license text, and consistency of factual-preservation instructions. Sample revisions retained prices, dates, uncertainty, direct quotations, meaningful lists, and command syntax. These checks are limited examples, not a benchmark or a guarantee for every future output.

## Version 1.0.0

Initial public release, November 6, 2026: English and PT-BR editions, portable prompts, source attribution, preserved upstream references, and usage documentation.
