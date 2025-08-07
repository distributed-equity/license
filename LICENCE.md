<!-- {{DEL:quotable trainable percent=100}} -->

# Distributed Equity License (DEL) v1.0

**License**: This license text is itself licensed under the Distributed Equity License v1.0.

**Author**: Kevin Ryan, Founder, [DistributedEquity.org](https://distributedequity.org)

**Version**: 1.0

**Attribution Required**: Yes

**Content Hash**: {{to be computed}}

------

## 1. Preamble and Purpose

This **Distributed Equity License** (“License”) is a legally binding copyright license that allows authors and rights holders (“Licensors”) to declare how their works may be used by others, particularly by automated systems. It is designed to be enforceable internationally under the Berne Convention for the Protection of Literary and Artistic Works, which grants authors exclusive rights to authorize reproduction, adaptation, broadcasting, and other uses of their works. The license combines human‑readable instructions with machine‑readable tags so that both people and artificial intelligence (“AI”) systems can understand and comply with the permissions and restrictions.

By embedding DEL tags into a work, the Licensor grants the public certain rights in the work subject to the terms of this License. **By exercising any rights to a work bearing DEL tags, You accept and agree to be bound by this License.** To the extent this License is interpreted as a contract, the Licensor grants You the rights described herein in consideration of the benefits the Licensor receives from making the work available. The rights granted under this License are irrevocable except as set forth under Section 9 (Termination).

## 2. Definitions

- **“DEL Tags”** means inline markers formatted as `{{DEL:flag1 flag2}}` … `{{/DEL:flag1}}`, with metadata between the opening and closing tags, used to delineate the scope of rights granted and reserved. The term “flag” refers to a permission or restriction defined in Section 5.
- **“Licensed Work”** means any literary, artistic, audiovisual, or other creative work to which the Licensor has attached DEL tags and applied this License.
- **“Licensor”** means the natural or legal person who owns or controls copyright or similar rights in the Licensed Work and who grants the rights under this License.
- **“You”** means the individual or entity exercising rights under this License. “Your” has a corresponding meaning.
- **“Licensed Rights”** means the rights granted to You by the Licensor subject to the terms and conditions of this License. These rights are limited to those copyright and similar rights in the Licensed Work that the Licensor has authority to license under the Berne Convention.
- **“Metadata”** means the information within DEL tags (YAML or JSON) specifying `license_flags`, author details, wallet addresses, content hashes, and other optional fields (as described in Section 4).

## 3. Governing Law and Jurisdiction

This License shall be governed by and construed in accordance with the laws of **Ireland** without regard to its conflict of law provisions, recognizing that the Berne Convention provides for national treatment and cross‑border enforcement of copyright. Any dispute arising out of or relating to this License shall be subject to the exclusive jurisdiction of the courts located in **Dublin, Ireland**, unless the Licensor designates a different jurisdiction in the metadata. Nothing herein shall deprive any party of the benefits of mandatory provisions of the law of the country in which the Licensed Work is used.

## 4. Scope of License and Metadata

### 4.1 Rights Granted

Subject to the terms of this License, the Licensor grants You a **non‑exclusive, worldwide, non‑sublicensable license** to exercise the rights specified by the applicable DEL flags in the Licensed Work. The license is royalty‑free except where the `micropay` flag (Section 5.9) requires payment. The rights granted may include permission to reproduce, adapt, summarize, translate, quote, or train AI models using the Licensed Work, as further described in Section 5.

### 4.2 Rights Reserved

The Licensor reserves all rights in the Licensed Work not expressly granted under this License. Without appropriate flags, You have **no right** to use the Licensed Work for AI training, summarization, translation, quotation, adaptation, public display, performance, distribution, or any other use beyond what is permitted by law (e.g., fair use or other exceptions). The Licensor retains moral rights, including the right of attribution and integrity, and reserves rights to equitable remuneration where applicable.

### 4.3 Metadata Requirements

The Licensor must include a metadata block within each DEL tag specifying at least:

- `license_flags`: a list of active flags (Section 5);
- `author`: the name or pseudonym of the Licensor;
- `license_uri`: a URI referencing this License version;
- Optional fields such as `wallet` (for micropayments), `content_hash`, `mint_uri`, `registry_id`, `timestamp`, and any additional fields the Licensor chooses.

If a field such as `wallet` is required to enforce a flag (e.g., `micropay`), failure to provide it may affect enforceability of that flag. Unrecognized metadata fields are reserved for future versions and do not affect the terms of this License.

## 5. License Flags and Permissions

### 5.1 General Principles

The Licensor may specify one or more **license flags** in the opening DEL tag to grant or withhold specific permissions. Flags are case‑insensitive. **Inner tags override outer tags**; if a portion of a Licensed Work contains nested tags, the innermost tag’s flags control that portion.

### 5.2 Default Status – All Rights Reserved

If no DEL tags or flags are present, **all rights are reserved**. Use of the work beyond statutory exceptions requires separate permission.

### 5.3 `trainable`

The `trainable` flag grants You permission to use the enclosed content for training, fine‑tuning, or otherwise improving AI or machine‑learning models. This includes copying the content into datasets and using it to generate derivative models, subject to compliance with this License and any micropayment obligations. **No waiver of moral rights** is implied.

### 5.4 `notrain`

The `notrain` flag expressly withholds permission to use the enclosed content for AI training or model improvement. This flag overrides any outer `trainable` flag. You may not ingest or incorporate the content into any AI model or training dataset.

### 5.5 `summarizable`

The `summarizable` flag grants permission to create automated summaries, translations, or paraphrases of the enclosed content. Summaries must retain the author’s attribution and may not misrepresent the original meaning. This flag does not permit AI training unless `trainable` is also present.

### 5.6 `nosummarize`

The `nosummarize` flag prohibits automated summarization, translation, or paraphrasing of the enclosed content. It overrides `summarizable`.

### 5.7 `quotable`

The `quotable` flag permits the reproduction of short excerpts from the licensed content with proper attribution.

- **Default limit**: up to **250 words or 10% of the total content**, whichever is less.
- **AI training** is **not permitted** under `quotable` unless the `trainable` flag is also declared.
- **Extensive reproduction, adaptation, or summarization** are **not** permitted under this flag alone.

#### Embedded Tag Attribute: `percent`

Authors may optionally override the default **10%** limit by specifying a `percent` attribute within the inline tag. This enables fine‑grained control over how much of the work may be reused in quotes.

Example:

```css
{{DEL:quotable percent=5}}
This section is licensed to be quoted up to 5% of its length.
{{/DEL:quotable}}
```

If the `percent` attribute is used, the numerical value takes precedence over the default 10% rule—but the **absolute limit of 250 words** still applies unless explicitly overridden by an additional `maxwords` tag.

Authors wishing to completely disable quoting should omit the `quotable` flag or use `noai` and `noreuse` together.

### 5.8 `noquote`

The `noquote` flag prohibits reproducing any portion of the enclosed content in AI outputs or human publications. It overrides `quotable`.

### 5.9 `micropay`

The `micropay` flag requires You to pay a specified micropayment for any use permitted by the other flags (e.g., training or summarization). The metadata must include a `wallet` address and may specify `micropayment_rate` (e.g., per‑kilobyte or per‑token). Failure to pay constitutes a breach of this License (see Section 9). If the `wallet` field is absent, You must contact the Licensor to arrange payment before using the content.

### 5.10 `noai`

The `noai` flag functions as a shorthand for `notrain`, `nosummarize`, and `noquote`. It prohibits any AI ingestion, training, summarization, or quotation of the enclosed content.

### 5.11 `publicdomain`

The `publicdomain` flag irrevocably dedicates the enclosed content to the public domain worldwide. The Licensor waives all rights to control or monetize the content. This flag overrides all other flags and cannot be revoked.

## 6. Inline Tag Specification

### 6.1 Syntax

A valid DEL tag is structured as follows:

```css
{{DEL:flag1 flag2}}
metadata (YAML or JSON)
{{/DEL:flag1}}
```

- **Opening Tag**: `{{DEL:flag1 flag2}}` lists the applicable flags. Flags must be separated by spaces.
- **Metadata Block**: Immediately after the opening tag, include a YAML or JSON block with key–value pairs (Section 4.3). If no metadata is necessary, the block may be empty.
- **Closing Tag**: `{{/DEL:flag1}}` must repeat the first flag used in the opening tag to ensure proper nesting.
- **Nested Tags**: Tags may be nested within other tags. Each closing tag must match its corresponding opening tag, and inner tags override outer tags.

### 6.2 Parsing

1. **Recognition**: Automated systems should identify the string `{{DEL:` to locate the start of a tag and `{{/DEL:` to locate the end.
2. **Metadata Interpretation**: The metadata block must be parsed as YAML or JSON. If a parser cannot interpret the metadata, it must treat the content as **all rights reserved**.
3. **Conflict Resolution**: If conflicting flags are present within the same tag (e.g., `trainable noai`), the most restrictive interpretation prevails (no AI use).
4. **Unknown Flags**: Unknown flags are reserved for future versions and have no legal effect. Systems must not assume they grant permission.
5. **Malformed Tags**: If tags are improperly nested or missing closing tags, the rights in the affected content are not granted. Use at Your own risk.

## 7. Attribution and Wallet Provisions

### 7.1 Attribution Requirements

When You use the Licensed Work in any manner permitted by this License, You must:

1. Provide the **author’s name** (or pseudonym) as specified in the metadata;
2. Identify the title of the work or a description if available;
3. State that the work is licensed under the “Distributed Equity License v1.0” and provide a link to the license text or include the license URI;
4. Include the **wallet address** if the `micropay` flag applies and payment is required; and
5. Keep intact all copyright notices and metadata provided by the Licensor.

Attribution must be provided in a reasonable manner based on the medium (e.g., footnotes, captions, metadata fields, or near the excerpt). Automated systems may include attribution in logs or model documentation if direct display is impractical.

### 7.2 Micropayment Obligations

If the `micropay` flag applies:

- You must track the amount of content used (e.g., bytes, tokens) and calculate micropayments using the `micropayment_rate` specified in the metadata or, if unspecified, the default rate published at the license URI.
- Payment must be made to the wallet address in the metadata at the time of use or within thirty (30) days of use. Failure to pay is a material breach and triggers termination (Section 9).
- If the wallet address is missing or invalid, You must contact the Licensor using available contact information to arrange payment before using the content.

## 8. Warranties and Disclaimers

### 8.1 No Warranties

Except as expressly provided in this License, the Licensed Work is provided “as is” and without warranties of any kind, express or implied. The Licensor disclaims all warranties including, but not limited to, implied warranties of merchantability, fitness for a particular purpose, non‑infringement, and the absence of errors. The Licensor does not warrant that the Licensed Work is free of viruses or other harmful components.

### 8.2 Limitation of Liability

To the fullest extent permitted by applicable law, in no event shall the Licensor be liable to You for any direct, indirect, incidental, special, punitive, or consequential damages arising out of Your exercise of the rights granted by this License, even if the Licensor has been advised of the possibility of such damages. This limitation shall not apply to liability for death or personal injury resulting from negligence.

## 9. Termination and Remedies

### 9.1 Automatic Termination

This License and the Licensed Rights terminate automatically if You fail to comply with its terms (including failure to pay required micropayments, or violation of `noai`, `notrain`, `nosummarize`, or `noquote` flags). Upon termination, You must immediately cease using the Licensed Work and destroy all copies in Your possession.

### 9.2 Reinstatement

If Your rights have terminated under Section 9.1, Your rights automatically reinstate as of the date You cure the violation, provided the cure occurs within thirty (30) days of Your discovery of the violation. Otherwise, reinstatement requires express permission from the Licensor. Nothing in this section limits the Licensor’s right to seek monetary damages or injunctive relief for Your violations.

### 9.3 Additional Remedies

The Licensor retains all rights to pursue legal remedies under applicable law for breach of this License. Such remedies may include injunctive relief, damages, accountings of profits, and statutory penalties, subject to the governing law.

### 9.4 Survival

Sections pertaining to definitions, warranties, limitations of liability, governing law, attribution, and remedies survive termination of this License).

## 10. Miscellaneous

### 10.1 Severability

If any provision of this License is deemed unenforceable, it shall be automatically reformed to the minimum extent necessary to make it enforceable. If it cannot be reformed, it shall be severed from this License, and the remaining provisions shall remain in full force and effect).

### 10.2 No Waiver

No term or condition of this License will be waived and no failure to comply consented to unless expressly agreed to by the Licensor.

### 10.3 No Endorsement

Nothing in this License constitutes or may be interpreted as a limitation upon or waiver of any privileges and immunities of the Licensor or of any rights of third parties. Use of the Licensed Work does not imply endorsement by the Licensor.

### 10.4 Entire Agreement

This License constitutes the entire agreement between the parties concerning the Licensed Work. Any additional or different terms communicated by You are not binding unless agreed to in writing by the Licensor.

### 10.5 Modification of the License

The Licensor may publish new versions of the DEL license. New versions will be similar in spirit but may differ in detail. Unless a Licensor indicates otherwise in the metadata, the License granted here is for the version indicated in the `license_uri` and does not extend to later versions. You may choose to accept a new version by continuing to use the Licensed Work under that version.

### 10.6 Assignment

You may not assign or transfer Your rights under this License without the Licensor’s prior written consent. The Licensor may assign its rights and obligations under this License without notice.

### 10.7 Interpretation

To the extent possible, this License shall not be interpreted to reduce, limit, or restrict any use that may lawfully be made of the Licensed Work without permission under this License.

## 11. Signature Block

```yaml

Signed on behalf of DistributedEquity.org (Block #0000000001):
Kevin Ryan  
Founder, DistributedEquity.org  
Date: 6 August 2025 (UTC+02:00, Europe/Paris)
```

------

**End of License**

<!-- {{/DEL:quotable}} -->

