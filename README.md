<!-- SPDX-License-Identifier: MIT -->

# Humanizer for ChatGPT

Reusable editing instructions for clearer, more natural prose in **English** and **Brazilian Portuguese**, with attention to the writer's meaning and voice.

This is an independently maintained adaptation of **[Humanizer 3.1.0](https://github.com/blader/humanizer/tree/0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0)** by **[Siqi Chen (`blader`)](https://github.com/blader)**. It retains the original 26-pattern framework and adapts the workflow, examples, and language guidance for ChatGPT. See [credits and attribution](NOTICE.md), the [MIT license](LICENSE), and [changes from upstream](docs/CHANGES_FROM_UPSTREAM.md).

## Start with a prompt file

Choose the instruction language you prefer:

| Edition | Complete prompt | Skill folder |
| --- | --- | --- |
| English | [Humanizer_ChatGPT_EN.txt](prompts/Humanizer_ChatGPT_EN.txt) | [humanizer-chatgpt-en](skills/humanizer-chatgpt-en/) |
| Brazilian Portuguese | [Humanizer_ChatGPT_PT-BR.txt](prompts/Humanizer_ChatGPT_PT-BR.txt) | [humanizer-chatgpt](skills/humanizer-chatgpt/) |

Each prompt is self-contained: it includes the editing workflow, all 26 patterns, examples, output modes, a compact version, and the original license. Choosing an edition changes the language of the instructions. The editor keeps the language of your text unless you ask for translation.

Download a prompt file, attach it to a ChatGPT conversation, and send:

```text
Use the instructions in Humanizer_ChatGPT_EN.txt to revise the text below.
Preserve its facts, conditions, quotations, and my writing style.
Keep the original degree of certainty. Return only the final version.

Text:
[paste your text here]
```

For the Portuguese edition, refer to `Humanizer_ChatGPT_PT-BR.txt`. You can also paste the complete instruction block from either file before the text you want edited.

For a closer match to your voice, supply two or three paragraphs you wrote yourself and label them as a writing sample. The instructions use the sample's style without borrowing its facts or personal experiences.

See the [usage guide](docs/USAGE.md) for projects, custom instructions, file editing, and skill-compatible environments.

## What the adaptation does

The workflow reads the whole text, revises its structure and phrasing, compares the result with the original, and delivers the requested output. It covers 26 patterns in six groups:

| Group | Patterns | Focus |
| --- | --- | --- |
| A | 1–5 | Staged openings, empty contrasts, dramatic closers, and invented objections |
| B | 6–11 | Formulaic rhythm, forced triads, repeated openings, and mechanical punctuation |
| C | 12–18 | Inflated claims, vague relationships, promotional filler, and borrowed authority |
| D | 19–21 | Decorative emphasis, headings, and inconsistent quotation marks |
| E | 22–25 | Chatbot wrappers, unsupported guesses, repeated headings, and unnecessary process narration |
| F | 26 | Repeating context the reader already knows |

The full guides are available in [English](skills/humanizer-chatgpt-en/references/patterns-en.md) and [Portuguese](skills/humanizer-chatgpt/references/padroes-pt-br.md).

The instructions require preservation of facts, numbers, dates, conditions, uncertainty, attribution, causal relationships, event order, and simultaneous actions. They protect code, commands, paths, placeholders, data, and link targets during prose edits. Meaningful contrasts, useful lists, technical vocabulary, and deliberate stylistic choices can stay.

## Output modes

| Ask for | Output |
| --- | --- |
| “Humanize this text.” | Final revised text, the default |
| “Revise it and explain the changes.” | Final text with brief editorial comments |
| “Run a full editorial audit.” | An initial revision, remaining editorial problems, and a final version |
| “Only tell me what needs improvement.” | Specific observations without replacing the text |

When editing a file, the instructions call for a final edited file and a brief summary if the host provides suitable file tools. A material unresolved problem may require a short note even in final-text mode.

## Illustrative example

**Before**

> We're thrilled to unveil a truly transformative update! Starting Thursday, the calendar will be available on the Team plan at no additional cost. It lets users filter appointments by date. Simple as that.

**After**

> Starting Thursday, the calendar will be available on the Team plan at no additional cost. It lets users filter appointments by date.

The revision preserves the date, plan, cost condition, and feature. The details in this example are fictional premises, not product claims.

## Skill-compatible environments

For a host that supports `SKILL.md` packages, copy the **entire** selected skill folder into the skill location documented by that host. Keep its references, metadata, assets, and license together. Then use the host's skill discovery and invocation mechanism.

Availability and installation differ between products and interfaces. A repository ZIP or an attachment in an ordinary conversation does not itself register an installed skill. The portable prompt files provide a direct way to use the instructions without skill installation. See the official [ChatGPT and Codex skills documentation](https://learn.chatgpt.com/docs/build-skills) for supported environments and invocation methods.

## Relationship to upstream

This project derives from Humanizer's written instructions and pattern framework. Its main changes are:

- Final-text output by default, with comments and audits available on request.
- Stronger checks for preservation of meaning, certainty, and attribution.
- New illustrative examples that retain the information supplied in each original passage.
- Language-specific handling of grammar and punctuation, including English spelling conventions and Brazilian Portuguese usage.
- Voice matching that preserves the author's supplied views and experiences.
- Portable ChatGPT prompt files alongside the skill packages.

The upstream source and license are preserved under [`upstream/humanizer-3.1.0/`](upstream/humanizer-3.1.0/). Detailed changes are recorded in [CHANGES_FROM_UPSTREAM.md](docs/CHANGES_FROM_UPSTREAM.md).

This is a community adaptation maintained separately from Humanizer. It is not an official OpenAI project or an endorsed release from the upstream maintainer.

## Scope and limitations

The repository supplies editing instructions and reference material. A language model follows those instructions in your chosen host. Results can vary with the model, context, and source text, so review significant facts and quotations before using a revision.

The patterns are editorial guidance. They do not establish authorship, measure how “human” a text is, or promise a result from an AI detector. A style edit also does not verify the truth of supplied claims; request fact-checking separately when you need it.

## License and credits

Distributed under the [MIT license](LICENSE). The original Humanizer copyright notice, **Copyright (c) 2025 Siqi Chen**, is retained. Follow [NOTICE.md](NOTICE.md) for attribution, adaptation credits, and upstream references when redistributing this material.
