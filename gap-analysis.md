# Gap analysis

Back to [the research index](README.md).

## Cost and ownership trade-off

[comparison-matrix](comparison-matrix.md) exposes one structural division.

```
                 high marginal cost
                         │
                 OHMS    │
            (owned,      │
             correctable,│
             curated)    │
                         │
   publisher owned ──────┼────── vendor owned
                         │
                         │   Snipd, Fathom, Dexa
                         │   (automated, cheap,
                         │    opaque, uncorrectable)
                         │
                 low marginal cost
```

Archival practice delivers ownership and correctability at human cost. AI
applications deliver automation at the cost of both. No examined system occupies
the remaining quadrant: **automated, low cost, publisher owned, and correctable.**

## Capabilities not combined in existing systems

**1. Topics as first class vertices.** Dexa graphs people, episodes, and shows.
Chapters organise within an episode. Snips are private. Nothing makes "caste
privilege in academia" an object that exists independently of any one recording
and accumulates evidence from all of them.

**2. Evidence sets rather than answers.** Retrieval systems return a passage or a
synthesised answer. A concept in this design carries every segment across the
corpus where it is discussed, which supports the comparative question a scholarly
interview series exists to pose: how do eight scholars position themselves on
this.

**3. Correction as a first class operation.** ASR error and extraction error are
certain, not hypothetical ([accuracy-and-review](accuracy-and-review.md)). The validation literature
treats human review as the established remedy. No consumer application exposes
the derived structure for correction at all.

**4. Structure the publisher owns.** OHMS exports XML into the institution's
system. Every AI application in [prior-art-consumer-apps](prior-art-consumer-apps.md) retains the
structure. A publisher who changes tools loses their index.

## Statement of contribution

Not that any component is novel. Every component has prior art:

| Component | Prior art |
| --- | --- |
| Segment level citation | OHMS, 2014 |
| Automatic transcription | Platform automation, commercial ASR |
| Semantic retrieval over podcasts | Fathom, Dexa, multimodal RAG |
| Graph over podcast content | Dexa |
| LLM extraction into a graph | 2025 KG construction literature |
| Human in the loop validation | KG validation literature, CleanGraph |

The claim is about **composition**: that assembling these into a single pipeline
where the output is a publisher owned topic graph, every vertex carries
timestamped evidence, and a human remains authoritative, produces a system that
no examined alternative matches on the criteria in [comparison-matrix](comparison-matrix.md), for
the bounded case defined in [the index](README.md).

## Why this combination has not been built

Two reasons it has not simply been done.

**Incentive.** Consumer applications monetise listener engagement across a
catalogue. Depth on one show is worth little to them and ownership of structure
is contrary to their retention model. The publisher has the opposite incentive
and, until recently, not the tooling.

**Cost.** The composition only became viable when structuring an hour of speech
fell to roughly a cent. Inference pricing crossed that threshold recently;
figures in [our-architecture](our-architecture.md).

## Related

[our-architecture](our-architecture.md) · [evaluation-plan](evaluation-plan.md) · [paper-framing](paper-framing.md) · [comparison-matrix](comparison-matrix.md)
