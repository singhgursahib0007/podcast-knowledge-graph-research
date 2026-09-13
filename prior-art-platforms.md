# Prior art: platform automatic metadata

Back to [the research index](README.md).

What the distribution platforms generate without publisher effort. Sources in
[bibliography](bibliography.md).

## Current state

Apple Podcasts and Spotify for Creators both ship automatic transcripts and
automatic chapters. Apple derives chapters from the episode transcript, labels
them "Automatically Created", allows publisher editing, and permits opt out.
Apple additionally detects references to other shows and renders them as links
inline in the transcript. Chapters are supported by Spotify, YouTube, and most
third party clients.

YouTube generates automatic captions and supports both creator authored and
automatic chapters.

## Assessment

Platform automation solves the transcription problem at zero marginal cost to
the publisher and should be treated as solved infrastructure rather than as a
differentiator.

Three limits are material to this work.

**Coverage is inconsistent.** Spotify's transcript rollout has been documented as
uneven, with creator dashboards reporting episodes ineligible for transcripts
despite platform announcements to the contrary. Automatic chapters launched
English only. A publisher cannot assume uniform coverage of their own back
catalogue.

**Chapters are intra episode.** A chapter list is a table of contents for one
recording. It creates no object that persists across episodes, so it cannot
express that a theme in episode two recurs in episode eight.

**The artefact is not portable.** Transcripts and chapters live inside the
platform's player. They are not queryable by the publisher, not exportable as
structure, and not addressable from the publisher's own site. Apple's inline
show linking demonstrates the platforms will build graph like features, but over
their own entities, for their own surfaces.

## Implication

Platform metadata is a **substrate**, not a solution. It reduces the cost of the
first pipeline stage and it raises the floor for casual listeners. It does not
produce publisher owned structure, which is the object this work targets.

A publisher who wants a durable index of their own corpus must build it, because
the platform builds an index of its catalogue, not of your argument.

## Related

[prior-art-consumer-apps](prior-art-consumer-apps.md) · [gap-analysis](gap-analysis.md) · [our-architecture](our-architecture.md)
