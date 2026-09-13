# Paper framing

Back to [the research index](README.md).

How the argument is assembled for publication.

## Positioning

**Not** a machine learning contribution. No new model, no new training method,
no benchmark result on a standard task. Framing it that way invites evaluation
against criteria it will fail.

**A systems and digital scholarship contribution.** The unit of contribution is
an architecture and its evaluation on a real corpus. The appropriate literature
is digital humanities, oral history infrastructure, and applied knowledge graph
construction.

## Thesis

> Indexing recorded interviews by topic has always needed a person to listen and
> annotate. Most of that work can now be automated by a constrained LLM pipeline,
> while keeping the two things that made manual indexing worth doing: the
> publisher owns the index, and a person decides what goes into it.

The thesis is about **preserving archival properties at automated cost**, not
about AI capability. This is the defensible version.

## Structure

| Section | Content | Source |
| --- | --- | --- |
| 1 Introduction | Retrieval, citation, accumulation all fail for spoken scholarship | [problem-statement](problem-statement.md) |
| 2 Related work | Archival indexing, platform automation, consumer AI, KG construction | the four prior art pages |
| 3 Gap | Criteria, matrix, the unresolved quadrant | [comparison-matrix](comparison-matrix.md), [gap-analysis](gap-analysis.md) |
| 4 System | Five stages, constraints, rationale | [our-architecture](our-architecture.md) |
| 5 Error and review | Error sources, mitigations, review as architecture | [accuracy-and-review](accuracy-and-review.md) |
| 6 Evaluation | Six measures, protocol, results | [evaluation-plan](evaluation-plan.md) |
| 7 Limitations | Stated, not buried | below |
| 8 Conclusion | Bounded claim, replication path | |

Related work must open with OHMS, not with LLMs. The segment citation affordance
is archival prior art and the paper is stronger for saying so first.

## Claims

Ordered by how well they can be defended.

| # | Claim | Support |
| --- | --- | --- |
| 1 | Composition is unmatched on the stated criteria | [comparison-matrix](comparison-matrix.md), defensible now |
| 2 | Topic vertices outperform episode vertices for comparative retrieval | E5, requires measurement |
| 3 | Constrained ingestion prevents vocabulary fragmentation | E4, requires measurement |
| 4 | Review costs materially less than authoring | E6, requires measurement and a built surface |

Claims 2 through 4 are unsupported until [evaluation-plan](evaluation-plan.md) executes. The paper
should not assert them earlier.

## Limitations

- One corpus, one subject area, one interview format.
- The ingestion review surface is designed, not built.
- Measurements bind to specific model versions.
- Breadth retrieval across many shows is out of scope and better served by
  existing services.
- Speaker diarisation is not yet integrated, so attribution depends on
  structural cues rather than acoustic speaker identity.

Each of these is verifiable by a reviewer, so stating them is more credible than
omitting them.

## Scope of the comparative claim

A general claim that this is the best available approach is unfalsifiable as
stated, and cases exist where other systems perform better.

The stronger move is to **define the criteria first, restrict the claim to a
bounded case, and concede the cases where other systems win**. Conceding these cases in advance removes them as
objections. This is why [comparison-matrix](comparison-matrix.md) carries a section on where other
systems perform better.

## Venues

| Venue | Fit |
| --- | --- |
| Digital Humanities Quarterly | Strong. Publishes podcast scholarship and infrastructure |
| Digital Scholarship in the Humanities | Strong. Method and tooling |
| Oral History Review | Good for the OHMS lineage argument |
| Journal of Equity and Social Justice in Education | Aligned with the corpus, weaker on systems contribution |
| Code4Lib Journal | Good for the implementation report variant |

## Related

[evaluation-plan](evaluation-plan.md) · [gap-analysis](gap-analysis.md) · [pipeline-visualisation](pipeline-visualisation.md) · [bibliography](bibliography.md)
