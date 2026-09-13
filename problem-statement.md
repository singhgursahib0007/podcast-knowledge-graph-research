# Problem statement

Back to [the research index](README.md).

## Access limitations

Written scholarship is addressable. A reader locates a claim by section, cites
it by page, and returns to it by reference. Spoken scholarship has none of this
by default. The atomic unit exposed to the listener is the episode, typically
forty to seventy minutes, and the only navigation primitive is the seek bar.

Three consequences follow.

**Retrieval fails.** A listener who recalls that caste privilege in Western
academia was discussed cannot determine which of sixteen episodes contains it,
nor where within that episode. The cost of locating a ten minute passage
approaches the cost of replaying the corpus.

**Citation fails.** Audio scholarship is difficult to cite precisely, which
depresses its use in subsequent work. Prior digital humanities work identifies
the absence of tooling for research and writing in audio as a structural
constraint on the form, not merely an inconvenience.

**Accumulation fails.** Each episode is published as a discrete artefact. A
theme raised in episode two and extended in episode eight is connected only in
the memory of whoever listened to both. The corpus does not become more useful
as it grows; it becomes longer.

## Causes

The bottleneck was historically transcription cost. That constraint has largely
dissolved: automatic speech recognition is cheap and, for clean single speaker
English, near human accuracy.

The remaining bottleneck is structural. A transcript is a linearisation of
audio, not an index of it. Converting eight thousand words of unpunctuated
speech into an addressable structure requires judgments about topic boundaries,
salience, and relation. These are interpretive tasks rather than transcription
tasks.

Systems that attempt this interpretive step divide into those that do it
manually at archival cost ([prior-art-archives](prior-art-archives.md)) and those that automate it
for individual consumption ([prior-art-consumer-apps](prior-art-consumer-apps.md)). The first does not
scale. The second does not accumulate.

## Corpus

Sixteen recorded interviews, two series, roughly one hour each. Participants are
academics across Canada and India. Subject matter spans caste, race, equity in
education, health access, and diaspora identity.

Two properties of this corpus matter technically:

1. **Dense proper nouns and specialist terminology.** Scholar names, Sanskrit and
   Punjabi terms, and institutional references. This is the regime where ASR
   error concentrates ([accuracy-and-review](accuracy-and-review.md)).
2. **Recurrent cross episode themes.** Caste privilege, the model minority
   construct, and institutional equity work appear in multiple interviews from
   different disciplinary positions. This is the property that makes a graph
   more appropriate than a per episode index.

## Related

[prior-art-archives](prior-art-archives.md) · [gap-analysis](gap-analysis.md) · [our-architecture](our-architecture.md)
