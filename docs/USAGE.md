<!-- SPDX-License-Identifier: MIT -->

# Usage guide

This guide covers the English and Brazilian Portuguese editions of Humanizer for ChatGPT. Both derive from [Humanizer 3.1.0 by Siqi Chen](https://github.com/blader/humanizer/tree/0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0); see the repository's [credits](../NOTICE.md) and [MIT license](../LICENSE).

## Choose an edition and format

| Need | Use |
| --- | --- |
| English instructions in a regular conversation | [English prompt file](../prompts/Humanizer_ChatGPT_EN.txt) |
| Brazilian Portuguese instructions in a regular conversation | [Portuguese prompt file](../prompts/Humanizer_ChatGPT_PT-BR.txt) |
| English instructions in a compatible skill host | [English skill folder](../skills/humanizer-chatgpt-en/) |
| Brazilian Portuguese instructions in a compatible skill host | [Portuguese skill folder](../skills/humanizer-chatgpt/) |

The two editions share the same editorial approach. Their examples and grammar guidance are localized. The instruction language does not force translation: both editions preserve the language of the text being edited unless you request a translation.

## Use a prompt in a conversation

1. Download the selected `.txt` file.
2. Attach it to the conversation, or paste its complete instruction block.
3. Identify the text to edit and request the output you want.

For the English edition:

```text
Use the instructions in Humanizer_ChatGPT_EN.txt to revise the text below.
Preserve the facts, numbers, dates, conditions, quotations, and my writing style.
Keep the original degree of certainty. Return only the final version.

Text:
[paste your text here]
```

For the Portuguese edition:

```text
Use as instruções do arquivo Humanizer_ChatGPT_PT-BR.txt para revisar
o texto abaixo. Preserve os fatos, números, datas, condições, citações
e meu jeito de escrever. Mantenha o grau de certeza das afirmações.
Entregue apenas a versão final.

Texto:
[cole seu texto aqui]
```

Give the audience, purpose, and desired tone when they affect the result. For example, “This is a support email to an existing customer; keep it warm and professional.” You do not need to fill out a long template for a simple edit.

## Match your writing style

Supply two or three paragraphs you wrote yourself. Clearly separate the sample from the text to revise:

```text
Use this sample as a reference for my writing style. Match its rhythm,
word choice, punctuation, and level of formality. Do not borrow its facts,
opinions, or personal experiences.

Writing sample:
[your own writing]

Text to revise:
[the text you want edited]
```

Without a sample, the workflow follows the source text and its genre. Personal writing may retain humor and uncertainty; technical writing should retain precise terminology. Naturalness does not require slang, mistakes, or an informal tone.

## Select an output mode

| Mode | Example request | What to expect |
| --- | --- | --- |
| Final text | “Humanize this text.” | The finished revision, ready to copy |
| Annotated revision | “Revise this and briefly explain the changes.” | The final text followed by concise editorial observations |
| Full editorial audit | “Show an initial revision, remaining editorial issues, and the final version.” | Two versions with an observable editorial critique between them |
| Diagnosis | “Only point out what needs improvement.” | Specific passages and suggested changes, without a full rewrite |

The default is final-text mode. The editor may add a brief note when a material issue prevents a faithful revision, such as contradictory dates or an attribution that needs clarification. An audit describes the text and edits; it does not require private reasoning.

## Reuse the instructions in a project

Add one prompt file to the project's sources, then put a short instruction in the project's instructions field:

```text
When I ask you to revise or humanize a text, follow Humanizer_ChatGPT_EN.txt.
Preserve its information and the writer's voice. Return only the final version
unless I ask for comments or an audit. Apply the edit to the text identified
in my request.
```

For the Portuguese edition, substitute `Humanizer_ChatGPT_PT-BR.txt`. Start related conversations inside that project to use its shared sources and instructions. See the official [projects documentation](https://learn.chatgpt.com/docs/projects) for current project behavior and available interfaces.

Keep the instruction limited to editing requests if other conversations in the project involve research, coding, or planning.

## Use the compact preference

Each portable file includes an optional compact section:

- English: `OPTIONAL COMPACT VERSION`.
- Portuguese: `VERSÃO CURTA OPCIONAL`.

Use that paragraph for a general writing preference in ChatGPT's personalization settings when you want it to apply across conversations. Use the complete prompt in a conversation or project when you need all 26 patterns, examples, and exceptions.

The compact preference summarizes the approach. It does not contain the full reference guide. See the official [prompting and personalization guidance](https://learn.chatgpt.com/docs/prompting) for current settings.

## Use a skill-compatible host

Choose one complete folder:

| Edition | Folder | Skill name |
| --- | --- | --- |
| English | `skills/humanizer-chatgpt-en/` | `humanizer-chatgpt-en` |
| Brazilian Portuguese | `skills/humanizer-chatgpt/` | `humanizer-chatgpt` |

Copy that folder into the skill location documented by your host. Keep `SKILL.md`, `references/`, `agents/`, any supplied assets, and `LICENSE` together. Copying only `SKILL.md` leaves its reference links incomplete.

Use your host's selection or invocation mechanism. Where ChatGPT offers skill selection, its documented mechanism is `@`; Codex CLI and IDE environments document `$` mentions or their skill selector. Availability differs across interfaces and accounts, so consult the official [skills documentation](https://learn.chatgpt.com/docs/build-skills).

Uploading a ZIP to an ordinary conversation supplies a file for the model to read. It does not, by itself, install a reusable skill. If skill discovery is unavailable in your environment, use the complete `.txt` prompt instead.

## Edit a document or technical file

Identify the file and the prose that may change. For example:

```text
Apply Humanizer to the prose in the attached document and return a revised copy.
Keep its headings, tables, citations, and substantive information.
Do not change code blocks, inline code, commands, paths, placeholders,
YAML metadata, data, formulas, or link targets.
Include a short summary of the editorial changes.
```

The host needs appropriate file tools to return an edited document. When those tools are unavailable, request the revised text for the affected sections. An attachment does not grant access to an original file on your computer.

For long documents, identify sections and preserve their order. Check that the returned file contains every requested section and that numbers, citations, and conditions still match the original.

## Preserve meaning during a revision

The instructions distinguish editing from summarizing and fact-checking. They require the model to preserve:

- Facts, names, prices, dates, quantities, units, and rankings.
- Negations, conditions, exceptions, and degree of certainty.
- Direct quotations, attribution, causal relationships, sequence, and simultaneous actions.
- The writer's supplied opinions, humor, reservations, and experiences.
- Technical content and formatting that perform a necessary function.

If you want a shorter summary, a translation, or additional research, request it explicitly. Keep unsupported facts out of the revision by supplying missing information or asking the editor to flag the gap.

When reviewing the result, check changes in certainty especially closely. “Could reduce waiting time” and “reduces waiting time” make different claims. Also check reorganized lists: three real payment options should remain three options even when the workflow is removing forced triads elsewhere.

## Common adjustments

| Result | Follow-up request |
| --- | --- |
| Too formal or too casual | Specify the intended reader and provide a short voice sample. |
| Too short | Ask for a faithful edit at the original level of detail and identify any omitted information. |
| Too many comments | Request final-text mode explicitly. |
| A quotation or technical token changed | Point to the original and request that it be restored exactly. |
| The style sample influenced the facts | Ask the editor to use the sample only for style and restore the original content. |
| A claim needs verification | Request fact-checking separately and specify acceptable sources. |

Results depend on the model and context. Review consequential facts before publishing. These are editorial tools; they do not classify authorship or guarantee an outcome from an AI detector.

## Sources and attribution

- [Humanizer 3.1.0, pinned upstream source](https://github.com/blader/humanizer/tree/0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0).
- [Preserved upstream files](../upstream/humanizer-3.1.0/).
- [Changes from upstream](CHANGES_FROM_UPSTREAM.md).
- [Credits and attribution](../NOTICE.md).
- [MIT license](../LICENSE).
