# Accuracy and human review

Back to [the research index](README.md).

Errors occur at every stage. The design question is where they surface and who
resolves them.

## Error sources

### Transcription

Whisper class models approach human accuracy on clean general domain English,
with reported WER around 5% on standard benchmarks. Performance degrades
systematically on domain specific terminology, proper nouns, non native accents,
and noisy acoustics. A specialist evaluation on dense proper noun commentary
reported WER of 0.217, roughly four times the general domain figure.

**This corpus sits in the degraded regime.** Scholar names, Sanskrit and Punjabi
terminology, institutional references, remote interview audio, and speakers
across Canadian and Indian English. Assuming benchmark WER here would be
unsound.

Speaker attribution is a separate failure. Base Whisper does not diarise;
diarisation requires an extension such as WhisperX with pyannote. In a two
speaker interview, misattribution assigns a claim to the wrong scholar, which is
the most damaging error the system can make.

### Structuring

Topic boundary placement is a judgment call with no ground truth. Salience
selection embeds a model's priors about what matters, which in a corpus about
marginalisation is not a neutral operation.

### Extraction

Entity extraction benchmarks at F1 above 0.95 on expert annotated written text.
Relation extraction is materially weaker, frequently above 0.75. Both figures
derive from written source text and do not account for propagated ASR error.

**Errors compound rather than remaining independent.** A misheard term produces
an incorrect topic, which attracts incorrect evidence, which produces incorrect
edges.

## Mitigations in the design

| Error | Mitigation |
| --- | --- |
| Timestamp drift | Per chunk duration probing rather than nominal accumulation |
| Fabricated citation | Timestamps copied from transcript segments, never generated |
| Vocabulary fragmentation | Existing graph supplied as context, search before create |
| Weak relation typing | Closed four label vocabulary |
| Silent corruption | Every stage writes an inspectable artefact |
| Irreversible error | Idempotent writes, safe reprocessing |

## Rationale for human review

The validation literature is consistent: LLMs are a complement to validation
rather than a replacement, and human oversight is the established mechanism for
ensuring generated claims are grounded in legitimate evidence.

For this corpus the argument is stronger than general practice. The material is
scholars' positions on caste, race, and marginalisation, attributed by name, on a
public academic site. An extraction error is a misattribution of a political and
professional position to a named academic. The acceptable error rate for
unreviewed publication is therefore approximately zero, regardless of benchmark
performance.

## Review design

Review must cost less than authoring, or the system offers no advantage over
curatorial indexing. Three properties support this:

**Review the proposal, not the transcript.** The reviewer sees a topic, its
summary, and its evidence segments. Verification is a seek and a listen, not a
read of eight thousand words.

**Provenance to the second.** Every proposed assertion carries a deep link to
the audio that produced it, so checking is bounded by the length of the passage.

**Correction propagates.** Merging two topics or detaching a segment updates the
graph directly, because the publisher owns it.

This is the CleanGraph position: review is an interface problem, and the cost of
validation is a property of the surface rather than of the task.

## Implementation status

The review surface specific to ingestion is **designed, not built**. The graph is
editable through the admin portal today, so correction is possible but not
purpose built. Until that surface exists, the human in the loop claim is
architectural intent rather than a demonstrated property, and
[comparison-matrix](comparison-matrix.md) marks it accordingly.

## Related

[prior-art-llm-kg](prior-art-llm-kg.md) · [our-architecture](our-architecture.md) · [evaluation-plan](evaluation-plan.md)
