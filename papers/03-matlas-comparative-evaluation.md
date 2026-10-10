# Matlas — Comparative Evaluation of Mars Location and Addressing Architectures

*An operating-requirements comparison of scientific coordinates, named features, spatial indexes, local addressing and Matlas*

**Initial Public Issue 1.0 · October 2026 · Author-approved text · Publication subject to separate release authorization**  
**Creator:** Jonathan Bullock  
**Publication edition:** Initial Public Issue 1.0 · October 2026  
**Approved public-issue licence:** CC BY 4.0 for the author's original text

## Executive assessment

Mars already has scientific coordinates, remotely sensed maps, recognized named features and mission-specific operational practices. Matlas does not aim to displace them. Instead, it asks whether a future populated Mars would also benefit from a stable, planet-wide **civil operating geography** and precise **machine-address identity** that remain available before local road, property and settlement naming systems are built.

This paper compares the roles of existing system families and Matlas against the ten design requirements MR1–MR10 set out in Chapter 5 of *Matlas: An Operational Map of Human Mars*. It is a **qualitative architectural evaluation based on the author's stated requirements**, not a controlled benchmark, cost study, independent preference survey or universal ranking of technical standards.

## 1. Evaluation frame: ten requirements

The manuscript's requirements are: **MR1 Be anchored**, **MR2 Cover everywhere**, **MR3 Scale coherently**, **MR4 Stay put**, **MR5 Take no sides**, **MR6 Accept overlays**, **MR7 Be operationally useful**, **MR8 Work for people**, **MR9 Work for machines**, and **MR10 Remain open**. They deliberately straddle geodesy, governance, software, operations and public communication.

No single existing system is necessarily deficient because it was built for a different purpose. A planetocentric frame may serve measurement excellently while doing little for residents' regional vocabulary; a local street address may be an ideal everyday destination inside a city while having no global equivalent for unsettled terrain. These are differences of *function*, not necessarily failures.

## 2. What the competing approaches are for

| System family | Primary strength | Interface distinction / limit relevant to Matlas |
|---|---|---|
| Scientific coordinates and reference frames | Numeric geographic/physical position and traceable measurement | Not inherently a persistent nested civil-area name or population-scale address |
| IAU-recognized planetary nomenclature | Stable names for recognized natural features | Does not itself partition all terrain into operational civil areas |
| GIS / DGGS / analytical spatial indexes | Powerful spatial computation, overlays and aggregation | Often optimized for analytic resolution rather than a small legible civil geography |
| Local streets, estates and development addresses | Strong human usability within a built settlement | Depend upon local schemes and do not uniquely cover all uninhabited land |
| Survey/parcel/legal boundary systems | Precise defined legal or jurisdictional objects | Presuppose authority, datum and policy; should not be imposed globally by Matlas |
| Asset and equipment registries | Identify particular machines, facilities or objects | Object identity can persist while its *location* changes |
| Matlas MGRID + BAR | Nested geographic identity and exact machine place address | Needs independently verified external frame integration before physical certification |
| Candidate Triplet / M3B | Potential concise human communication of a BAR place | Production dictionary, reversible global allocation and speech safety remain unverified |

This matrix is a framework for complementary use, not a declaration that Matlas supersedes the other technologies or that alternative DGGS/addressing proposals have been exhaustively surveyed.

## 3. MGRID versus coordinates and grids

Matlas assigns canonical Mars area labels from the top-level Quad through the Zand, Province, Sector and Tile to Click. The deliberate civil hierarchy is designed for recurring operations: route planning by region, grouping infrastructure, emergency dispatch, practical records and conversation about places. It is complementary to scientific coordinates, which remain necessary for geometric position and measurement.

The angular rules and the ±72° polar transition are explicit. Polar rows have variable longitudinal branching based on the actual parent geometry, so the identifier logic does not assume a uniform Cartesian rectangle at the poles. **26 Quads, 624 Zands and 193,557,552 Clicks** are defined within the stipulated model. This supports a broad, persistent reference structure, but it does not yet prove ease of learning, social acceptance or geodetic transformation accuracy for actual spacecraft data.

A suitable future evaluation would contrast Matlas with representative DGGS and geographic indexing systems on exact boundary ownership, area distortion, adjacency operations, ID length, hierarchy intuitiveness, version migration, spatial query cost and independent interoperation. The handoff offers source-local results for Matlas, not a measured head-to-head comparison against a selected external system.

## 4. BAR versus local addresses and object IDs

BAR supplies a global geometric *place* identifier beneath every MGRID Click. Its 16×16 Courts and 16×16 Cells yield 65,536 Cells per Click, with an unsigned 44-bit canonical Cell payload after Click and Court fields. The 12.68-trillion-cell capacity is a mathematical property of the design, not a registry of real settlements or a guarantee of practical positional accuracy.

This is useful precisely where roads and postal-style names do not yet exist: exploratory terrain, an unmanned depot, an isolated utility or a developing settlement. Conversely, inside a mature city, a named building, public street address and locally regulated parcel reference may be more natural. BAR should be an interoperable *underlay*, not a mandate to abolish those systems.

A BAR Cell is not a parcel, a property right, a height coordinate or an asset identity. Cell ownership on a mathematical boundary and the exact machine byte framing are defined; survey-quality physical transformation remains a different certification problem. The current 26-case private receiving smoke test and prior local code comparisons do not measure emergency-dispatch reliability or rover navigation accuracy.

## 5. Triplet versus direct binary and human labels

Most people will not communicate `Cell44` integers in ordinary speech. Triplet proposes to overlay three words while leaving the underlying BAR identity unaltered. The semantic design distinguishes W1/W2 classes and W3 roles, aiming to help people notice implausible or misheard combinations instead of relying only on opaque random labels. Future lexical versions can then evolve without changing already issued machine locations.

The trade-off is substantial engineering responsibility. Spoken safety needs more than a large list of attractive words: eligibility, frequency, homophones, accent robustness, locality and Court exclusivity must be proven over a complete allocation. No finished MB3-EN1 vocabulary or production encoder was supplied in the October handoff. The present comparison therefore treats Triplet's potential usability as a *hypothesis to test*, not an established performance advantage.

## 6. Use-case assessment

For **scientific measurement** and precise spacecraft operations, published scientific reference frames and proven instrumentation remain primary; Matlas is an additional label and must not be used to bypass frame verification. For **global logistical records** or **regional operational planning**, a stable hierarchical civil index offers an intuitively useful organising layer if its reference remains reproducible. For **settlement administration**, MGRID can coexist with later political divisions and names rather than imposing them. For **emergency communications**, a future Triplet may become easier to speak than numeric IDs, but production safety must be established experimentally.

The book enumerates twelve operating jobs ranging from rendezvous and maintenance to land-use records and shared geographical vocabulary. These are *intended use cases*, not twelve operational trials already completed. Their value is to define questions that implementers can test independently.

## 7. Risks, alternatives and governance

Matlas imposes choices: a frozen area hierarchy, a versioned reference realization, canonical boundary ownership, and a distinctive vocabulary of Quad/Zand/Province/Sector/Tile/Click. An independent team might instead prefer a standard scientific DGGS with a locally branded naming layer, or local addresses backed by common coordinates. Both are legitimate directions to evaluate. Matlas's claimed attraction is the particular integrated *civil + machine + optional language* interface, not inevitability or demonstrated universal preference.

Stability creates a governance duty. New reference models must not silently move historical locations. New words must not reinterpret existing binary Cells. A global operating grid must remain neutral about sovereignty, property and cultural naming. Evidence of third-party integration, cost, independent accessibility and error rates should ultimately decide whether its additional layer earns adoption.

## 8. Qualified conclusion

Matlas is a coherent proposal for an operating geography whose **conceptual distinctions are clear and locally testable**, not an already independently certified global address service. It should be examined alongside rather than substituted for mature scientific systems. Its strongest current contribution is a complete architectural disclosure: hierarchical area identities, exact binary place-address semantics and a separated human language aspiration. The most urgent outstanding evaluations concern MRR-1 physical reference authenticity, external BAR/geodetic conformance and Triplet production vocabulary and speech safety.

The author has deliberately left those engineering gates open. This comparative paper does not announce their closure, issue a standalone normative protocol or state that another Mars indexing or addressing architecture is objectively inferior.

## Publication boundary and source basis

This companion's original author prose is approved for issue under CC BY 4.0, separate from the copyrighted book and 97 website images, upon separate publication authorization. It incorporates no external system's proprietary datasets or unapproved lexical corpora. The existing MGRID September Zenodo record remains subject to distinct verification and is not republished here.

**Private frozen sources:** *Matlas* Chapter 4 (twelve operating jobs), Chapter 5 (MR1–MR10), Chapters 9–17, Appendices E–I; `docs/architecture/comparison.md`, `requirements.md`, `overview.md`, `status-and-gates.md`, and the pinned MGRID/BAR/Triplet source documents. A systematic externally sourced prior-art survey and quantitative third-party benchmarking remain separate future work.
