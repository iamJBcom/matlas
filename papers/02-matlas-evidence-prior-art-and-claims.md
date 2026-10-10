# Matlas — Evidence, Prior Art & Claims

*Distinguishing defined geography, tested addressing mathematics, provisional physical reference frames and historical originality claims*

**Initial Public Issue 1.0 · October 2026 · Author-approved text · Publication subject to separate release authorization**  
**Creator:** Jonathan Bullock  
**Publication edition:** Initial Public Issue 1.0 · October 2026  
**Approved public-issue licence:** CC BY 4.0 for the author's original text

## Purpose

Matlas is deliberately published first as a **proposed architecture** that future researchers, settlements and software developers can independently assess. Its claims do not all have the same evidentiary basis. Some are *definitions* established by the design; others follow by *exact arithmetic*; others have *local executable test evidence*; and some depend upon reference data or independent field tests that are not yet available.

This evidence paper identifies those distinctions and positions the work alongside pre-existing Mars scientific cartography, feature naming, spatial indexing and addressing systems. It is **not** an exhaustive novelty search, a formal certification statement or proof that no earlier thinker proposed a comparable integrated architecture.

## 1. What Matlas specifically contributes

The authorial contribution being disclosed is the **combination** of three layers:

1. **MGRID:1:MARS** — an unbroken, canonical Mars-wide nested operating-area hierarchy, including deterministic equatorial and polar boundary ownership and Click ordinal numbering.
2. **BAR:1:MARS** — a binary, locally reversible Court/Cell addressing layer attached to the exact MGRID Click identity, with contextual machine transport and explicit rejection of invalid encodings.
3. **Triplet / M3B** — a prospective human-friendly lexical view on BAR identity, intended to use semantic families, pronunciation/familiarity checks and lexical exclusivity to reduce errors without changing the machine address.

The architecture distinguishes *where* a site lies from what it is called, who owns it, or which object currently occupies it. This is an integration and design claim, not an assertion that coordinate systems, spatial hierarchies, compact integer encodings, word addresses or polar subdivision were individually invented here.

## 2. Source and approval hierarchy

The private handoff identifies author-ratified decisions **I1-A–I1-C and R1–R5** in source-pinned MGRID and BAR documents. The ratified scope covers hierarchy and boundary semantics, polar P1 branching, Click ordinals, Court36/Cell44, tagged frames and the BAR-JSON:1 transport. Normative-style SHALL statements inside those checkpoint documents convey *author-approved design intent*; they do not make the full Matlas system an externally certified public normative v1.0 release.

The companion source indexes point to frozen evidence checks and author-approval receipts. The M9 receiving audit independently verified 277/277 handoff-file hashes and checked 26 BAR machine cases, but those are **receiving/local integrity checks**, not an independent replication of a complete physical Mars reference model. The historical source chain should be available to future validators through versioned hashes; this paper does not fabricate missing third-party certifications.

## 3. Claims ledger

| ID | Statement | Supported status |
|---|---|---|
| MAT-01 | Matlas defines an operating hierarchy from Quad to Click | **DEFINED / author-ratified design** |
| MAT-02 | The hierarchy contains 26 Quads, 624 Zands and 193,557,552 Clicks | **EXACT enumeration within the stipulated model** |
| MAT-03 | Longitude/latitude seam rules and unique polar apex lineages are mathematically specified | **DEFINED; local algorithm evidence** |
| MAT-04 | BAR supplies 256 Courts and 65,536 Cells in each Click | **MATHEMATICALLY DERIVED** |
| MAT-05 | All valid BAR Cells have a 44-bit canonical payload and reversible local ordinal fields | **DEFINED; locally tested in checkpoint scope** |
| MAT-06 | BAR therefore has 12,684,987,727,872 possible Cell positions | **EXACT arithmetic; not surveyed ground truth** |
| MAT-07 | The private checkpoint records 4,601 matching Python/JS comparisons | **LOCAL COMPARISON EVIDENCE; not independent certification** |
| MAT-08 | All modern spacecraft coordinates have verified, accurate conversion into MRR-1 | **NOT ESTABLISHED** |
| MAT-09 | The required original NAIF file has been authenticated and genuine CSPICE parity passed | **NOT ESTABLISHED** |
| MAT-10 | The complete MB3-EN1 dictionary and reversible word allocator have been released | **NOT ESTABLISHED** |
| MAT-11 | Matlas supersedes IAU naming, scientific GIS/DGGS systems or future law | **NOT CLAIMED; outside design scope** |
| MAT-12 | The integrated hierarchy/address/Triplet proposal is attributable to the published author | **DEFINED IN THESE DISCLOSURES; absolute historical priority unproven** |

## 4. Mathematics and local conformance

MGRID makes exact choices about boundary ownership: internal east-positive longitude edges belong to the eastward child, nonapex latitude edges to the poleward child, the equator to the northern side, and each exact pole to one designated apex lineage. Polar geometry uses a row-specific variable eastward branch count rather than pretending that uniform rectangular longitude widths survive at 90° latitude. These rules enable a deterministic partition given a stipulated coordinate and mathematical realisation.

BAR then assigns each Click a 28-bit ordinal and appends two 8-bit local codes: `Court36 = (Click28 << 8) | CourtCode` and `Cell44 = (Click28 << 16) | (CourtCode << 8) | CellCode`. The payload count is the product of the 193,557,552 assigned Click ordinals and 65,536 Cells per Click. The reserved portion of the wider 28-/36-/44-bit unsigned spaces is **invalid**, not an alternative naming space. The local `BAR-JSON:1` encoding adds `BAR:1:MARS`, `MGRID:1:MARS` and `MRR-1` context to avoid mistaking an unlabelled binary payload for a globally meaningful address.

These are compelling *formal* properties. Their local test results do not demonstrate that a survey-quality coordinate is already transformed into MRR-1 to known physical accuracy, or that the system can guide a rover to within the bounds of a particular rock or asset. BAR identifies a planar angular patch, not a surveyed vertical solid or an independent asset identity.

## 5. Physical-reference verification gap

The proposed reference realisation `MRR-1` requires the original relevant NAIF data file and an authenticated SHA-256 fingerprint, an identified CSPICE implementation, independent `pxform` checks and disclosed coordinate-transform vectors. The source checkpoint states that these gates are **OPEN**. A stipulated frame inside locally tested mathematics cannot be described as externally certified physical Mars accuracy merely because its encoded areas round-trip perfectly.

A future certification package should give explicit provenance and error bounds for physical transformations, test points at angular seams and poles, independent gold vectors, reference-model versioning and a failure path for uncertain or unsupported inputs. This work is beyond the October explanatory publication scope.

## 6. Triplet lexical work remains provisional

The optional Triplet/M3B design defines distinct roles for W1/W2/W3, structural semantic families and safety objectives. The vocabulary release process would need to freeze legally usable lexicons, pronunciation/familiarity checks, candidate allocation, Court exclusivity, capacity evidence and reversible machine mappings. The source handoff contains **draft contracts and compiler architecture**, not an approved, exhaustively allocated, independently tested English profile. It cannot support a claim that any three-word phrase already identifies a certified Mars Cell worldwide.

The machine identity would remain valid independently of human vocabulary evolution. This separation is central to the architecture and should not be confused with successful production of the entire lexical layer.

## 7. Prior art and non-substitution

Matlas operates amid mature systems, not in a geographic vacuum. **Planetocentric latitude/longitude and scientific reference frames** already define numeric locations. **IAU nomenclature** identifies recognized natural features. **GIS and discrete global grid systems (DGGS)** support analytical overlays, aggregation and computation. **Local street/survey/address systems** may work extremely well within particular settlements. **Asset identifiers** track objects, which can move independently of their current location.

Matlas proposes an operating-area hierarchy and a stable machine *place* address at a different interface boundary. This is a reason to compare and interoperate, **not** a proof that any established method is defective. Existing systems' priority, coverage, standards status, licensing and measured performance must be examined in their own right. The handoff's comparison matrix is expressly conceptual; this draft has not performed an exhaustive independent global prior-art review or an empirical superiority trial.

## 8. Existing MGRID publication and priority discipline

The private handoff reports a September 2026 *MGRID:1:MARS v1.0* Zenodo publication (record/DOI reported as `10.5281/zenodo.22695710`). The exact external record, payload and relation to the later consolidated Matlas sources **require independent verification** before making it a definitive citation or depositing a replacement. The October Matlas book and proposed informative papers should identify themselves as subsequent explanatory work, not silently issue a second copy of an unchanged earlier normative package.

Publishing a timestamped, attributable description supplies valuable evidence that the author disclosed specific ideas by that date. It does not prove absolute historical novelty, grant scientific endorsement or force later users to adopt the architecture. Independent discovery, earlier literature and implementation improvements remain possible.

## 9. Next evidentiary programme

The sensible sequence is to preserve the existing disclosed architecture, resolve MRR-1 source authentication and physical parity, commission independent machine-vector tests, and independently audit a proposed full Triplet lexical compiler. Only after those results should the author decide what scope merits a new standalone BAR/Triplet normative release. Claims about real-world navigation accuracy, universal safety or language completeness must remain absent until separately established.

## Rights and references

The author's original text of this proposed paper is intended for CC BY 4.0 **only upon explicit approval and issuance**. The separate illustrated book and images remain all-rights-reserved. Unowned third-party data and sources are not automatically relicensed. This is an informative technical audit, not an issued normative protocol or certification.

**Private frozen source basis:** the M9 handoff's `TRACEABILITY.md`, `status-and-gates.md`, `provenance.md`, original `MGRID-1-MARS.md`, `BAR-1-MARS.md`, `MRR-1-REFERENCE-REALISATION-DRAFT.md`, and Chapters 10–17 / Appendices E–I of the author-approved book.
