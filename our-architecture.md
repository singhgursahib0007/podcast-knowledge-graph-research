# System architecture

Back to [the research index](README.md).

Four stages, each with an inspectable artefact. Implementation detail lives in
the engineering docs; this page records the rationale.

## Pipeline

```
  video                                            artefact
    │
    ▼  S1  EXTRACT        FFmpeg                    16 kHz mono MP3
    │                     strip video, normalise
    │
    ▼  S2  TRANSCRIBE     ASR, chunked              transcript + segment times
    │                     20 min segments
    │
    ▼  S3  STRUCTURE      LLM, single pass          markdown, [MM:SS] headings
    │                     sections and subsections
    │
    ▼  S4  INGEST         constrained agent         graph writes
    │                     reuse before create
    │
    ▼  S5  REVIEW         human                     authoritative graph
```

## S1, extraction

FFmpeg to 16 kHz mono at 64 kbps. Speech recognition gains nothing from stereo
or from bandwidth above the speech band, and the reduction lowers transfer cost
by roughly an order of magnitude against source audio.

## S2, transcription

Chunked at twenty minutes to stay within upload limits. Chunks are cut with
stream copy, so boundaries land on frame boundaries rather than exact marks.
Offsets are therefore recomputed per chunk by probing actual duration rather
than assumed duration. Naive accumulation of nominal chunk length introduces
drift that compounds across an hour, which would corrupt every downstream
citation.

**Timestamps are the load bearing output of this stage**, not the text. Every
claim the system later makes resolves through them.

## S3, structuring

One LLM pass converting transcript to a markdown document with sections and
subsections, each carrying a timestamp range.

The output is deliberately **a document, not a summary**. A summary discards the
mapping back to source. A timestamped document preserves it, and remains
human readable, diffable, and reviewable before anything enters the graph.

Design constraints from [prior-art-llm-kg](prior-art-llm-kg.md):

- Timestamps are copied from transcript segments, never generated. A generated
  timestamp is an unverifiable citation.
- Output is an intermediate artefact on disk. Stages cache, so re running a later
  stage never re pays for an earlier one.

## S4, ingestion

A constrained agent with four operations:

```
find_topic(query)                       search before creating
create_topic(slug, title, summary, kind, group)
attach_segment(slug, episode, start, end, heading, summary, relevance)
link_topics(a, b, relation)             closed vocabulary
```

Three constraints carry most of the quality.

**The current graph is supplied as context.** The agent receives every existing
topic and its summary before acting. Without it, each episode grows a parallel
vocabulary and "casteism" and "caste discrimination" become separate vertices,
halving the evidence attached to each. This follows the vault ingestion pattern
that motivated the design.

**Relations are a closed vocabulary.** `relates_to`, `contrasts_with`,
`builds_on`, `example_of`. Relation extraction is the weaker operation in the
literature, so the task is reduced from open relation generation to
classification over four labels.

**Writes are idempotent.** Segments key on episode and start time, attachment on
topic and segment. Re ingestion converges rather than duplicating, which is what
makes correction and reprocessing safe.

Edges arise from two sources: asserted by the agent, and computed from
co-occurrence when two topics share a segment. Co-occurrence requires a fan out
cap, since a segment touching eight topics otherwise emits twenty eight edges.

## S5, review

The graph is publisher owned and editable. Ingestion produces proposals; a human
reviewer accepts, edits, or rejects them. Rationale and design in
[accuracy-and-review](accuracy-and-review.md).

## Access surface

The reader sees a force directed topic map. Node size encodes a composite of
airtime and connectivity, so structurally central ideas are visually central.
Selecting a topic opens its evidence set: every segment across every episode,
each resolving to a deep link that starts playback at that second.

The interaction inverts the default. Rather than choosing an episode and
scanning for an idea, the reader chooses an idea and receives every place it
occurs.

## Cost

At current inference pricing for a low cost reasoning model, structuring one
hour of speech is well under one cent; ingestion is a small number of tool calls.
Both stages across sixteen episodes fall in the low tens of cents. Transcription
dominates, and platform automation is progressively driving that toward zero
([prior-art-platforms](prior-art-platforms.md)).

The economic claim: **the interpretive labour OHMS assigns to a curator now
costs approximately one cent per hour to propose, leaving the curator to
validate rather than to author.**

## Related

[accuracy-and-review](accuracy-and-review.md) · [gap-analysis](gap-analysis.md) · [pipeline-visualisation](pipeline-visualisation.md) · [evaluation-plan](evaluation-plan.md)
