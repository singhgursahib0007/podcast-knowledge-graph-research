# Prior art: consumer podcast intelligence

Back to [the research index](README.md).

Applications that expose episode interiors to individual listeners. Sources in
[bibliography](bibliography.md).

## Snipd

Swiss application positioning itself for "knowledge seekers". Transcribes
episodes, generates chapter structure automatically, and lets a listener capture
a moment by triple tapping headphone controls, which stores the surrounding
transcript and an AI summary. Transcript search returns excerpts with
timestamps. Exports to Notion and Readwise.

**Architecture inferred:** ASR, then per episode segmentation, then summarisation
over a captured window. Highlight generation is applied selectively to popular
shows, indicating per episode processing cost is non trivial at catalogue scale.

**Limit:** the unit of persistence is the snip, a listener's private excerpt.
Structure accrues to the individual, not to the corpus. A second listener starts
from zero.

## Airr and Fathom

Airr established the pattern of quoted audio excerpts with attached notes.
Fathom indexes full audio for natural language search, auto generates
transcripts, chapters, and highlights, and supports clipping. Fathom's stack is
built on commercial ASR.

**Limit:** retrieval is episode scoped. Both answer "where in this show" well.
Neither constructs persistent relations between concepts across a corpus.

## Dexa

The closest prior art, and the one this work must engage directly. Dexa indexes
podcasts for natural language question answering. Its retrieval is reported to
combine several indexing techniques with **a knowledge graph mapping people,
episodes, and shows**, and to resolve context and synonymy rather than exact
keyword match. Catalogue in the low hundreds of shows.

**Convergence:** Dexa validates both the premise and the mechanism. A graph over
podcast content is not a novel proposal.

**Divergence, and where the difference is real:**

| Dimension | Dexa | This work |
| --- | --- | --- |
| Graph vertices | People, episodes, shows | Topics and concepts |
| Primary output | Answer synthesised from sources | Navigable map, answer is secondary |
| Corpus | Many shows, shallow | One show, exhaustive |
| Correction path | None exposed to publisher | Publisher edits the graph |
| Ontology ownership | Vendor | Publisher |

The vertex distinction is the substantive one. A graph of people and shows
answers "who said what about X". A graph of topics answers "what does this
corpus think about X, and how do those positions relate", which is the question
a scholarly interview series is constructed to address.

## Podscribe and transcript vendors

Transcription and advertising verification. Transcripts as compliance and SEO
artefacts rather than navigation surfaces. Included for completeness; not
competitors on access.

## Summary

All four optimise for **consumption**: helping one listener extract value from
one episode in one session. None optimise for **curation**: helping a publisher
accumulate a durable, correctable, citable structure over their own corpus. That
distinction organises [gap-analysis](gap-analysis.md).

## Related

[prior-art-platforms](prior-art-platforms.md) · [prior-art-archives](prior-art-archives.md) · [comparison-matrix](comparison-matrix.md) · [gap-analysis](gap-analysis.md)
