# Matlas — Open Technical Overview

*An operating geography for Mars: persistent areas, deterministic machine addresses, and an optional human language interface*

**Initial Public Issue 1.0 · October 2026 · Author-approved text · Publication subject to separate release authorization**  
**Creator:** Jonathan Bullock (book byline: JB Bullock)  
**Publication edition:** Initial Public Issue 1.0 · October 2026  
**Approved public-issue licence:** Creative Commons Attribution 4.0 International (CC BY 4.0), for the author's original text only

## Executive overview

Matlas is a proposed operating geography for the surface of Mars. It addresses a problem that scientific maps and coordinates do not solve alone: how people, institutions and machines might refer persistently to regions, working areas and a precise location over decades of settlement, without confusing a place with whoever owns it or the object presently occupying it. The associated book is *Matlas: An Operational Map of Human Mars*, by JB Bullock.

Matlas has three separable parts. **MGRID** supplies a stable, nested global area hierarchy. **BAR** (Binary Address Reference) divides each MGRID Click into Court and Cell positions and expresses their identity as exact integers and canonical machine messages. **Triplet / M3B** is a proposed three-word human interface layered over that numerical identity. Scientific latitude and longitude remain authoritative measurements beneath these civil operating labels; locally chosen names, roads, property systems and governmental boundaries remain independent overlays above them.

This paper describes the *architecture and ratified design decisions*, not a completed globally certified geodetic system, production Triplet dictionary or independently accredited normative release. MRR-1 physical-reference authentication and genuine CSPICE parity, external BAR geodetic checks, and MB3-EN1 vocabulary compilation remain outstanding.

## 1. The hierarchy that Matlas adds

The canonical MGRID identifier is `MGRID:1:MARS`. It progresses from **Quad → Zand → Province → Sector → Tile → Click**. Four regular latitude Belts, each partitioned into six longitude columns, and two polar Quads give **26 Quads**. Twenty-four 15° longitude Zones cross 24 regular Bands, producing 576 regular Zands; 24 Zone wedges in each polar cap add 48 more. The total is **624 Zands**.

Regular Zands subdivide by fixed grids, whereas the polar hierarchy varies eastward branching with latitude and the actual containing parent. It does not pretend that longitude lines are equally spaced at the poles. The approved mathematical ownership rules give exact edge destinations: longitude boundaries belong to the eastward child, nonapex latitude boundaries to the poleward child, and each pole to a unique apex lineage. The equator is assigned to the northern hemisphere. These are design rules for deterministic partitioning, not empirical land claims.

The present mathematical MGRID partition contains **193,557,552 Clicks**. A Click carries a canonical zero-based global ordinal whose **28-bit** representation is used by BAR. Click ordinals come from a specific recursive walk of the actual hierarchy; they are not a simple flattening of latitude and longitude or a rectangular substitute for the polar geometry. The detailed reference is the author-ratified `MGRID-1-MARS.md`, and the book's MGRID chapters and Appendix E explain its use and limits.

## 2. BAR: the machine-address layer

MGRID stops at Click. BAR subdivides *each* Click into **16 × 16 Courts**, and each Court into **16 × 16 Cells**, making **65,536 Cell positions per Click**. Court and Cell row and column indices are zero-based (`0–15`). Rows progress equatorward to poleward, columns west to east, following the parent Click's angular geometry even near the poles.

The exact integer design is:

```text
CourtCode = (CourtRow << 4) | CourtCol
CellCode  = (CellRow  << 4) | CellCol
Court36   = (Click28 << 8) | CourtCode
Cell44    = (Click28 << 16) | (CourtCode << 8) | CellCode
```

A fixed-width **Click28, Court36 or Cell44** is an address *payload*, with reserved values rejected. Their compact wire representations have distinct kind tags and use 4, 5 or 6 bytes. The machine transport `BAR-JSON:1` adds explicit world, MGRID version, reference realisation and wire identity: the bare tagged frame is not, by itself, a globally complete context-aware location record. Mathematical capacity is **12,684,987,727,872 Cells**; that is a count of possible address positions, *not* surveyed assets, inhabited plots or generated word triplets.

Exact angular boundaries identify an area in the stipulated `MRR-1` reference. They are not a promise of surveyed ground accuracy, terrain elevation, centimetre guidance or valid conversion from an arbitrary spacecraft coordinate system. Those require separately verified reference transformations.

## 3. Triplet: a proposed human interface, not the machine record

Triplet / M3B proposes a human-friendly three-token way to communicate a BAR location while keeping the numerical BAR Cell identity canonical. The conceptual structure separates lexical functions across **W1, W2 and W3** and uses semantic families and safety constraints as aids to detect mistakes in spoken or transcribed addresses. A vocabulary profile, such as the proposed **MB3-EN1** US-English profile, would need a release-specific word inventory, encoding/decoding rules, exclusivity, pronunciation/familiarity checks, and independent safety testing.

Those outstanding tasks are substantial. Neither the book nor this paper claims that a globally complete reversible Triplet dictionary, allocation ledger, final speech-safety proof or production decoder is already issued. A human label cannot silently redefine the underlying Cell44 identity, and unapproved candidate words must not be treated as a usable public address service.

## 4. How layers interoperate

A typical conceptual workflow is **measured planetary position → declared Mars reference → MGRID containing Click → BAR Court/Cell identity → optional Triplet presentation**. The transformation at each boundary is explicit. Existing scientific maps, IAU-recognized feature names, geological/hazard datasets, future utility plans, rights and governance overlays remain distinct. A named crater does not become an MGRID Quad; an MGRID Cell does not confer ownership; and a BAR address does not uniquely identify a movable person or object.

This distinction makes Matlas an *operating* layer, not a replacement for maps or settlement choices. The book proposes ten design requirements (MR1–MR10) spanning reference anchoring, total surface coverage, nesting, persistence, neutrality, overlays, operational utility, human legibility, machine determinism and openness. Those are design goals, not proof that every imaginable future use case has passed an operational trial.

## 5. What has been tested—and what has not

The source technical checkpoint records author ratification of MGRID hierarchy decisions **I1-A–I1-C** and machine decisions **R1–R5**. Local numerical evidence includes exact polar-branch calculations, checkpoint regression suites, and **4,601 matching Python/JavaScript local comparisons** in the cited T3.2g scope. The private handoff's receiving audit also executed **26 BAR machine smoke checks** successfully. These strengthen confidence in the *stipulated* mathematical/encoding model.

They do **not** establish independently verified physical Mars coordinates. Specifically, the original NAIF `pck00011.tpc` source bytes and their hash have not been authenticated in the handoff, a genuine N0067+ CSPICE `pxform` comparison remains unexecuted, and third-party gold vectors are not furnished as independent certification. Triplet lexical safety and end-to-end language allocation remain in development. The proposed `MRR-1` frame realisation is consequently a technical hold, not an externally authenticated datum release.

## 6. Release scope, versions and provenance

Matlas can publish a detailed, inspectable architecture while separately gating engineering profiles. The MGRID/BAR mathematical definitions, candidate code, human language proposal and physical-coordinate realisation should have *different* version and certification records. Any future redefinition of a previously issued cell's meaning must be deliberate and versioned, never a silent correction. Local labels and future Martian administrative choices must be allowed to change without rewriting canonical geometric identities.

A prior **MGRID:1:MARS v1.0** Zenodo publication is reported in the private handoff as DOI `10.5281/zenodo.22695710` (10 September 2026). Its remote record and deposited bytes **have not yet been independently reconciled** in this publication-preparation stage. This paper does not mint a new MGRID normative DOI or imply the earlier deposit certifies BAR, MRR-1 or Triplet.

## 7. Publication and rights boundary

The separately copyrighted book *Matlas: An Operational Map of Human Mars* and its original illustrations remain **all rights reserved**, despite free web reading. This informative companion's original author text is approved for CC BY 4.0 **upon its separately authorized public issue**. Original code, author-owned datasets and third-party assets have different file-level licence conditions and are not automatically included in this paper.

**In one sentence:** Matlas proposes a persistent Mars-wide geography, a precise numeric place address beneath it, and a possible human word interface above it—with explicit boundaries between mathematical definitions, physical verification and unfinished lexical implementation.

## Source basis (private frozen M9 handoff)

- Approved book, Chapters 4–17 and Appendices E–I; canonical public title approved 10 October 2026.
- `MGRID-1-MARS.md` (I1-A–I1-C, R1–R3), `BAR-1-MARS.md` (R4–R5), `TRIPLET-M3B-INTERFACE-DRAFT.md` (candidate).
- Technical source documents `docs/architecture/overview.md`, `requirements.md`, `status-and-gates.md`, `docs/research/provenance.md` and approval-scope evidence.
- M9a private freeze and author rights/publication decisions; no unaudited claim of external certification or new DOI.
