# Evaluation plan

Back to [the research index](README.md).

What would substantiate the claim in [the index](README.md), and what would
falsify it. Written before measurement so the protocol is not fitted to the
result.

## Dimensions

Following the decomposition established in the KG construction literature:
extraction accuracy, semantic consistency, structural robustness. Extended with
two access measures, since the object under evaluation is a retrieval system.

## E1, transcription accuracy on this corpus

**Why.** Benchmark WER is not transferable to this audio ([accuracy-and-review](accuracy-and-review.md)).

**Protocol.** Human transcribe six ten minute passages sampled across both
series and both speaker populations. Compute WER overall and on a held out list
of proper nouns and specialist terms.

**Reported.** Overall WER, proper noun error rate, and the gap between them.
The gap is the number that matters, because it predicts downstream extraction
error.

## E2, timestamp fidelity

**Why.** Every citation the system makes depends on it.

**Protocol.** Sample sixty segment boundaries. Measure offset between the claimed
timestamp and the audible start of the passage.

**Threshold.** Median absolute offset under two seconds, ninety fifth percentile
under five. Beyond five seconds a listener lands mid sentence and the citation
loses credibility.

## E3, extraction precision and recall

**Protocol.** A domain reader independently indexes three full episodes,
producing a reference set of topics and segment attachments. Compare against
system output.

**Reported.** Precision and recall on topics, precision and recall on segment
attachments, and a separate figure for relation typing, which the literature
predicts will be the weaker number.

**Falsification.** Topic precision below 0.80 would mean review costs approach
authoring cost, and the economic argument in [our-architecture](our-architecture.md) fails.

## E4, ontology stability

**Why.** The failure mode the design most guards against is vocabulary
fragmentation.

**Protocol.** Ingest episodes sequentially. After each, record new topics created
versus existing topics reused. Independently audit the final graph for
near duplicate pairs.

**Expected signature.** New topic creation decays as the corpus grows, since a
mature graph should mostly attract evidence rather than spawn vertices. A flat
or rising curve indicates the reuse constraint is not binding.

## E5, retrieval task performance

**Why.** The user facing claim is about finding things.

**Protocol.** Twelve retrieval tasks of the form "find where X is discussed",
drawn from the corpus by a domain reader. Two conditions: the graph interface,
and the baseline of platform transcripts plus episode scrubbing. Within subject,
counterbalanced.

**Reported.** Time to first correct passage, and task success within five
minutes.

**Falsification.** No significant improvement over baseline would defeat the
central claim regardless of every other measurement.

## E6, review cost

**Why.** The economic argument depends on validation being cheaper than
authoring.

**Protocol.** Measure reviewer minutes per episode hour to bring system output to
publishable quality. Compare against the archival baseline for curatorial
indexing.

**Threshold.** Review must run below roughly one third of the authoring baseline
to justify the pipeline over established archival practice.

## Threats to validity

**Single corpus.** All measurements come from one sixteen episode series in one
subject area with a consistent interview format. Generalisation is unsupported
without replication.

**Author as evaluator.** E3 and E5 require a domain reader who is not the system
author. Self evaluation on these would be uninformative.

**Model drift.** Figures are tied to specific model versions and will not be
reproducible as those change. Versions and dates must be recorded with every
measurement.

**Corpus scale.** E4's interesting behaviour appears as a graph matures. Sixteen
episodes may be too few to observe the decay curve.

## Related

[comparison-matrix](comparison-matrix.md) · [accuracy-and-review](accuracy-and-review.md) · [paper-framing](paper-framing.md)
