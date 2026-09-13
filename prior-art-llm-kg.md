# Prior art: LLM driven knowledge graph construction

Back to [the research index](README.md).

Whether the interpretive step can be automated, and at what measured accuracy.
Sources in [bibliography](bibliography.md).

## Reported performance

Knowledge graph construction from unstructured text using LLMs is an active area
with 2025 results across several domains.

| Task | Reported figures |
| --- | --- |
| Entity extraction, expert annotated corpus | precision 98.82%, recall 93.18%, F1 95.92% |
| Relation extraction, same class of work | precision frequently above 75% |
| Course knowledge graph entity extraction | accuracy up to 87.92% |
| Academic KG, manual sampling of 100 papers | entity 0.94, inter paper relation 0.93 |

Two observations govern how these numbers should be read.

**Entity extraction outperforms relation extraction consistently.** Identifying
that a concept is present is materially easier than characterising how two
concepts relate. Systems that depend on precise relation typing inherit the
weaker number.

**The figures derive from written source text.** Applying them to ASR output
compounds two error distributions. Transcription error propagates into extraction
error, which is not reflected in any of the benchmarks above. See
[accuracy-and-review](accuracy-and-review.md).

## Evaluation practice

The literature converges on three dimensions: extraction accuracy, semantic
consistency, and structural robustness. Surveys of LLM empowered KG construction
formalise this decomposition. [evaluation-plan](evaluation-plan.md) adopts it.

## Validation and human in the loop

A distinct body of work addresses knowledge graph validation, defined as
ensuring accuracy and reliability of graph contents. Recent work integrates LLMs
with human in the loop validation and concludes that LLMs are a valuable
**complement** for generating high quality graphs at scale, rather than a
replacement for validation.

CleanGraph formalises human in the loop refinement and completion as an
interface problem, which is the correct framing: the question is not whether
review is needed but what review surface makes it cheap.

In the adjacent citation trust literature, human oversight is described as
verification that generated claims are grounded in legitimate evidence, with
hallucination identified as the principal threat.

## Retrieval over spoken corpora

The multimodal retrieval pattern for podcasts combines transcript embeddings with
audio embeddings, retrieving on concept rather than keyword. This is the
mechanism underlying the semantic search offered by the applications in
[prior-art-consumer-apps](prior-art-consumer-apps.md).

Embedding retrieval and graph structure are complementary rather than
competing. Embeddings answer "what resembles this query". A graph answers "what
is this connected to, and where is the evidence". The systems examined here
mostly implement the first.

## Design implications

The literature supports three design commitments:

1. Automated extraction is accurate enough to be useful and not accurate enough
   to be authoritative. It must be treated as a proposal.
2. Relation extraction is the weaker operation, so relation typing should be
   constrained to a small closed vocabulary rather than left open.
3. Human validation is the established remedy, and its cost is an interface
   problem.

These become the constraints in [our-architecture](our-architecture.md).

## Related

[prior-art-archives](prior-art-archives.md) · [accuracy-and-review](accuracy-and-review.md) · [evaluation-plan](evaluation-plan.md) · [our-architecture](our-architecture.md)
