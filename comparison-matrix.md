# Comparison matrix

Back to [the research index](README.md).

Systems from [prior-art-consumer-apps](prior-art-consumer-apps.md), [prior-art-platforms](prior-art-platforms.md) and
[prior-art-archives](prior-art-archives.md) scored against criteria defined before the comparison, so
the axes are not selected to favour the conclusion.

## Criteria

| # | Criterion | Test |
| --- | --- | --- |
| C1 | Segment citation | Does a result resolve to a timestamp in the recording |
| C2 | Cross episode structure | Does a concept exist as an object spanning episodes |
| C3 | Semantic retrieval | Does search match concepts, not only strings |
| C4 | Publisher ownership | Does the publisher hold and control the structure |
| C5 | Correctability | Can an authoritative human edit the derived index |
| C6 | Marginal cost | Cost of processing one additional hour |
| C7 | Cumulative value | Does the corpus become more useful as it grows |

## Matrix

Full, partial, absent.

| System | C1 | C2 | C3 | C4 | C5 | C6 | C7 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Linear player, show notes | absent | absent | absent | full | full | nil | absent |
| Platform transcripts and chapters | full | absent | partial | absent | partial | nil | absent |
| Snipd | full | absent | full | absent | absent | low | partial |
| Airr, Fathom | full | absent | full | absent | absent | low | absent |
| Dexa | full | partial | full | absent | absent | low | partial |
| OHMS | full | absent | partial | full | full | high | partial |
| This work | full | full | full | full | full | low | full |

## Observations

**C1 is solved across the field.** Every system beyond the baseline resolves to
a timestamp. OHMS provided this in 2014, so it is not a differentiator.

**C2 separates the systems.** Only Dexa constructs cross episode structure,
and over people, episodes, and shows rather than over topics. No examined system
treats a *concept* as a durable vertex with an evidence set attached.

**C4 and C5 separate the archival tradition from the AI tradition, cleanly.**
Archives own and correct their indexes and pay full human cost. AI applications
achieve low marginal cost and return nothing the publisher owns or can fix. This
is the central trade the field has not resolved.

**C6 is where OHMS is vulnerable.** Curatorial indexing scales linearly with
duration in trained staff hours. This is why excellent archival practice has not
propagated to working podcasts.

**C7 follows from C2.** Without cross episode structure, episode seventeen adds
an hour of audio. With it, episode seventeen enriches existing concepts and
tightens the graph.

## Status of the final row

The final row is a specification, not a measurement. Its C1, C2, C3 and C4
entries are observable in the running system. C5 is partially built: the graph
is editable through the admin portal, and the review surface specific to
ingestion is designed but not yet implemented. C6 is estimated from token
pricing. C7 is structural rather than measured, since the corpus has not yet
grown under the system.

[evaluation-plan](evaluation-plan.md) specifies what would turn these entries into measurements.

## Where other systems perform better

Recorded explicitly, because each case is verifiable and bounds the claim.

- **Catalogue breadth.** Dexa retrieves across many shows. This retrieves across
  one. For "which podcast discussed X", Dexa wins outright.
- **Zero setup.** Platform automation requires nothing of the publisher. This
  requires a pipeline run and review.
- **Conversational answering.** Dexa synthesises a direct answer. This returns a
  map and evidence, which is the right output for scholarship and the wrong one
  for a quick factual question.

## Related

[gap-analysis](gap-analysis.md) · [evaluation-plan](evaluation-plan.md) · [paper-framing](paper-framing.md)
