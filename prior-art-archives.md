# Prior art: archival and scholarly indexing

Back to [the research index](README.md).

The tradition that established segment level citation for recorded speech, three
decades before the current generation of AI tooling. Sources in [bibliography](bibliography.md).

## OHMS

The Oral History Metadata Synchronizer, developed at the Louie B. Nunn Center
for Oral History, University of Kentucky Libraries, and released publicly in
2014. Open source and web based.

Two components. The **application** is where a curator uploads a transcript,
time synchronises it against the recording, and builds a time coded index. The
**viewer** renders the result, providing word level search and a time correlated
transcript that connects a search term to the corresponding moment in the
recording. Output is XML, interfacing with the institution's own content
management system.

**This is the design this work inherits.** The central affordance, search a term
and arrive at the second of audio where it occurs, was specified and shipped by
archivists. Any claim to novelty on that affordance alone would be false.

OHMS is deployed widely across university oral history programmes and is
documented in library guides at Oberlin, UNC Asheville, and the SUNY system.

**Limit:** the index is produced by human labour. A curator listens, segments,
titles, and keywords each passage. Quality is high and cost scales linearly with
duration. Nunn Center documentation treats indexing as a deliberate archival
activity with staff time attached. At that cost, a working podcast does not get
indexed.

**Second limit:** the unit of organisation is the interview. OHMS produces an
excellent index *of a recording*. It does not produce a structure *across a
collection* in which a theme is a first class object.

## Audiovisual archives in the humanities

The Maison des Sciences de l'Homme in Paris launched an audiovisual archive
programme in 2001 providing an indexing and annotation environment in which
users extract segments, classify them into personal archives, and reuse them in
academic and educational work.

Notable because segment extraction and reuse were treated as scholarly
activities requiring infrastructure, anticipating what consumer applications
later rebuilt as private highlights.

## Podcasting as digital scholarship

Digital Humanities Quarterly documents podcasts as a form of digital
scholarship. Penn Libraries and the Humanities Podcast Network provide
institutional guidance for scholarly podcasting.

The recurring finding is instructive: difficulties archiving audio and the
absence of tooling for research and writing in audio have constrained the use of
sound in digital scholarship. The constraint identified is **infrastructural**,
not a lack of scholarly interest.

HiPSTAS applied machine learning to large audio collections, establishing that
computational analysis of scholarly audio is a recognised method.

## Contributions adopted in this work

Three things this work takes directly:

1. **Segment level citation as the correct primitive.** Not the episode, not the
   chapter, but the passage, addressable by time.
2. **The index is an editorial artefact.** It encodes curatorial judgment and
   therefore must be correctable by the curator. This motivates the human review
   requirement in [accuracy-and-review](accuracy-and-review.md).
3. **Institutional ownership of the structure.** OHMS exports XML into the
   institution's own system. The index belongs to the archive.

The open question this work addresses is whether the interpretive labour OHMS
assigns to a curator can be substantially automated without surrendering the
curator's authority over the result.

## Related

[prior-art-llm-kg](prior-art-llm-kg.md) · [gap-analysis](gap-analysis.md) · [accuracy-and-review](accuracy-and-review.md) · [our-architecture](our-architecture.md)
