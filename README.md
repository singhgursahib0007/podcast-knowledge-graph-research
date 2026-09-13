# Research: topic-based navigation for podcast archives

Root index. Pages are wiki linked: a name in double square brackets opens
another document, and every page links back here.

**Read the formatted version: <https://singhgursahib0007.github.io/podcast-knowledge-graph-research/>**

## Abstract

Long form audio scholarship is effectively unindexed. A sixteen episode
interview series carries roughly sixteen hours of argument, and the dominant
access method remains linear playback. This research examines how existing
systems expose the interior of recorded conversation, identifies where each
class of system stops, and specifies a pipeline that converts recorded speech
into a navigable topic graph in which every assertion resolves to a timestamped
source segment.

The contribution is not a new model. It is the composition: speech recognition
with segment level timestamps, an LLM structuring pass that yields a
timestamped document rather than prose summary, an agentic ingestion step
constrained to reuse an existing ontology, and a review surface that keeps a
human authoritative over the resulting graph.

## Navigation

### Problem and prior art

| Page | Scope |
| --- | --- |
| [problem-statement](problem-statement.md) | Why spoken scholarship resists retrieval |
| [prior-art-consumer-apps](prior-art-consumer-apps.md) | Snipd, Airr, Fathom, Dexa, Podscribe |
| [prior-art-platforms](prior-art-platforms.md) | Apple, Spotify, YouTube automatic metadata |
| [prior-art-archives](prior-art-archives.md) | OHMS, oral history indexing, digital humanities |
| [prior-art-llm-kg](prior-art-llm-kg.md) | LLM driven knowledge graph construction literature |

### Analysis

| Page | Scope |
| --- | --- |
| [comparison-matrix](comparison-matrix.md) | Systems scored against seven access criteria |
| [gap-analysis](gap-analysis.md) | The four capabilities no examined system combines |

### Our system

| Page | Scope |
| --- | --- |
| [our-architecture](our-architecture.md) | The pipeline, stage by stage, with design rationale |
| [accuracy-and-review](accuracy-and-review.md) | Error sources, mitigations, human in the loop design |
| [evaluation-plan](evaluation-plan.md) | Metrics and protocol for substantiating the claims |

### Output

| Page | Scope |
| --- | --- |
| [paper-framing](paper-framing.md) | Argument structure, claims, venue, threats to validity |
| [pipeline-visualisation](pipeline-visualisation.md) | How the pipeline is depicted for readers |
| [bibliography](bibliography.md) | Sources |

## Scope of the claim

The claim defended here is bounded. This architecture is not superior for every
purpose. Breadth oriented services index thousands of shows and will retrieve
across a corpus this system never sees. The claim is narrower and testable:

> For a single bounded corpus of scholarly long form audio, where provenance and
> correctability matter more than catalogue size, a topic graph with segment
> level citation and human review dominates both linear playback and
> summary oriented AI tooling on retrieval precision, verifiability, and
> cumulative value.

[gap-analysis](gap-analysis.md) sets out the evidence. [evaluation-plan](evaluation-plan.md) sets out what would
falsify it.
