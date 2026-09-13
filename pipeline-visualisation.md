# Pipeline visualisation

Back to [the research index](README.md).

How the pipeline is depicted so a reader grasps it without reading
[our-architecture](our-architecture.md) in full.

## Diagram requirements

A reader should take four things from one look.

1. **Linearity.** Five stages, one direction.
2. **Artefacts.** Each stage emits something inspectable. This is the claim that
   the pipeline is auditable rather than a black box.
3. **The transformation.** Audio to text to structure to graph. The state change
   at each arrow is the substance.
4. **Where the human is.** Review is a stage, not a footnote.

## Rendered asset

The primary diagram is rendered at `assets/pipeline-diagram.webp`, 1640 by 529,
and is the figure used in the showcase. It follows the specification below, with
the stages laid out horizontally rather than vertically because the rendered
version carries its labels inside each stage rather than in a separate column.

The source render is 1672 by 941 with large empty margins; the published crop is
measured from the content bounds rather than eyeballed, and encoded as WebP at
46 KB against 632 KB for the equivalent PNG, at 41.3 dB PSNR.

## Primary diagram: stage ladder

Vertical, left aligned, one row per stage. Each row carries stage number, verb,
mechanism, and the artefact produced. The artefact column is the point: it turns
an abstract pipeline into a sequence of files a reader could open.

```
S1  EXTRACT      FFmpeg                      16 kHz mono MP3
S2  TRANSCRIBE   ASR, 20 min chunks          transcript with segment times
S3  STRUCTURE    LLM, single pass            markdown, [MM:SS] headings
S4  INGEST       constrained agent           topics, evidence, edges
S5  REVIEW       human                       authoritative graph
```

Vertical rather than horizontal because stage names and artefact names do not fit
side by side at readable type, and a horizontal pipeline on a phone becomes a
scroll.

## Second diagram: cost and ownership

The argument in [gap-analysis](gap-analysis.md) is spatial and should be drawn as such. Two
axes, marginal cost against ownership, existing systems plotted, the empty
quadrant visible before the label is read.

This carries the thesis more efficiently than the matrix, which is why it
precedes the matrix in the HTML showcase and follows it in the paper, where the
reader has already absorbed the criteria.

## Third diagram: navigation comparison

Two small panels side by side.

**Before.** An episode list, a seek bar, an arrow labelled "scan".
**After.** A topic, an evidence list, arrows labelled with timestamps landing in
different episodes.

This communicates the user facing benefit faster than prose. It is the only
diagram a non technical reader needs.

## Rendering rules

Inline SVG, no diagramming dependency, matching the site design system.

| Property | Value |
| --- | --- |
| Stage rails and arrows | ink at low opacity |
| Artefact labels | muted, monospace, smaller |
| The single highlighted element | lime |
| Human stage | lime border, to mark the change of actor |
| Type | Manrope for labels, DM Sans for description |

**One accent per diagram.** Lime marks the single element the reader should
notice: the review stage in the first, the unoccupied quadrant in the second, the
timestamp links in the third. Additional accents reduce the emphasis of each.

Every diagram must survive being read at 360px wide and printed in greyscale,
which means it cannot depend on colour to carry meaning. Colour marks emphasis;
position and label carry information.

## Related

[our-architecture](our-architecture.md) · [gap-analysis](gap-analysis.md) · [paper-framing](paper-framing.md)
