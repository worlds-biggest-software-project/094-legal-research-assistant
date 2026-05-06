# Legal Research Assistant

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An open-source, AI-native legal research assistant that delivers hallucination-resistant case law search, citation analysis, and brief drafting on top of public-domain legal data.

The Legal Research Assistant is a retrieval-augmented research platform built for attorneys, legal aid organisations, law students, and solo practitioners who are priced out of Westlaw, Lexis+, and Harvey. It combines openly licensed primary law sources (CourtListener, Public.Resource.Org, GPO) with grounded LLM reasoning to answer plain-English legal questions, validate every citation against the source corpus, and produce Bluebook-formatted research memos.

---

## Why Legal Research Assistant?

- **Incumbent pricing excludes most of the profession.** Harvey AI runs ~$1,200/lawyer/month with a 20-seat minimum; Westlaw + CoCounsel All Access reaches $500–$800/user/month; Lexis+ with Protégé runs $250–$475/user/month. Solo practitioners, legal aid organisations, and law students cannot access frontier legal AI at these prices.
- **Citation hallucination is still unsolved.** The Stanford CodeX 2024 study measured a 34% citation error rate in Westlaw AI-Assisted Research and 17% in Lexis+ AI — unacceptable for a domain governed by ABA Model Rule 1.1 (Competence).
- **The data layer is open; the application layer is not.** CourtListener, Juriscraper, and Eyecite (all BSD or public domain) provide tens of millions of indexed court opinions and citation extraction tooling, but no AI-native research assistant has been built on top of them as of 2026.
- **Closed databases create lock-in.** Thomson Reuters' acquisition of Casetext, Clio's $1B acquisition of vLex, and the LexisNexis–Harvey partnership concentrate legal AI inside proprietary ecosystems with opaque models and rising prices.
- **Underserved buyer segments exist.** Mid-market litigation firms, in-house legal teams, legal aid, and solo practitioners are explicitly the segments where incumbents either overprice or under-serve.

---

## Key Features

### Grounded Research and Citation Validation

- RAG-based legal research over CourtListener's case law corpus: natural-language question to retrieved cases to AI-synthesised answer with inline citations
- Post-generation citation validation: every cited authority is checked against the corpus to flag hallucinated or fabricated citations
- Basic citator: track whether a cited case has been overruled, distinguished, or criticised in subsequent decisions within the corpus
- Full-text and semantic (embedding-based) search across the case law corpus
- Bluebook and ALWD citation formatting in AI-generated output

### Jurisdiction-Aware Reasoning

- Jurisdiction filter constraining results to a specified federal circuit or state
- Authority hierarchy awareness: distinguishes binding from persuasive precedent and surfaces circuit splits
- Ranking of retrieved cases by binding-authority status in the user's jurisdiction
- Recency-aware prioritisation of controlling decisions

### Brief Drafting and Document Analysis

- Brief drafting assistant that generates argument sections with inline, page-referenced citations traceable to source documents
- Word-format export with Bluebook citation formatting
- Document upload and issue-spotting from briefs, contracts, or statutes
- Research history organised by matter or topic for client-linked workflows

### Regulatory Monitoring

- Configurable watch on Federal Register dockets and state regulatory sources
- AI-generated summaries of regulatory changes mapped to affected practice areas
- Continuous monitoring designed for in-house legal teams and corporate counsel

### Open Corpus and Extensibility

- Built on CourtListener (public domain US court opinions), Juriscraper (BSD), and Eyecite (BSD)
- Expandable corpus including Public.Resource.Org statutes, GPO Code of Federal Regulations, and openly available state codes
- Public REST API for programmatic access and embedding in matter management or CLM platforms

---

## AI-Native Advantage

The project is designed around hallucination elimination as its primary differentiator: a retrieval-augmented architecture grounds every answer in version-controlled primary sources, and a post-generation validator checks each citation against CourtListener before returning results. Beyond grounded retrieval, the assistant applies jurisdiction-aware reasoning — understanding controlling versus persuasive authority, circuit splits, and federal versus state hierarchy — and generates briefs with citation provenance traceable to specific pages and paragraphs of the cited source. A regulatory monitoring agent extends the same grounded approach to ongoing surveillance of the Federal Register and state dockets.

---

## Tech Stack & Deployment

The system is built on open legal data infrastructure: CourtListener's REST API and bulk data, Juriscraper for court website scraping, and Eyecite for citation extraction. RAG retrieval runs over a verified, version-controlled corpus with embedding-based semantic search and post-generation citation validation. Deployment targets include hosted SaaS for general use and on-premises / locally-hosted LLM deployment for firms and legal aid organisations with strict data residency, attorney-client privilege, or GDPR constraints. Outputs are formatted to Bluebook and ALWD citation standards; an API layer is planned to enable embedding in matter management, CLM, and document automation platforms.

---

## Market Context

The LegalTech AI market is $2.82B in 2025, projected to reach $3.7B in 2026 at 31.4% CAGR (The Business Research Company), with legal research the highest-revenue AI segment at 29.1% of legal AI software spend. Incumbent pricing ranges from ~$1,200/seat/month (Harvey AI) and $500–$800/seat/month (Westlaw + CoCounsel) at the high end, down to $99–$299/month (Paxton AI) and free–$195/month (Fastcase) at the accessible end. Primary buyers include BigLaw associates and partners, mid-market litigation firms, in-house legal teams, law students and legal aid organisations, and solo practitioners — with the latter three groups most underserved by current pricing.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
