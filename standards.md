# Standards & API Reference

> Project: Legal Research Assistant · Generated: 2026-05-06

## Industry Standards & Specifications

### Document & Citation Standards

**OASIS LegalDocML / Akoma Ntoso v1.0**
- Official URL: https://www.oasis-open.org/standard/akn-v1-0/
- Adopted as an OASIS standard in August 2018. XML vocabulary for representing legislation, regulations, and judicial decisions in a machine-readable, structured format. Adopted by the UN, EU Parliament, and multiple national parliaments. Directly relevant for structuring legal documents in any corpus ingestion pipeline. The US Legislative Markup (USLM) schema used for the United States Code was designed to be consistent with Akoma Ntoso.

**Bluebook Citation Standard (21st Edition)**
- Official URL: https://www.legalbluebook.com/
- The dominant US legal citation format. Any AI-generated legal research output must produce Bluebook-compliant citations to be accepted by attorneys and courts. Covers citations to cases, statutes, regulations, secondary sources, and international materials.

**ALWD Guide to Legal Citation (7th Edition)**
- Official URL: https://www.alwdguide.com/
- Alternative citation standard used by many law schools and some courts. Relevant for any brief drafting or legal memo output feature. Complements rather than replaces Bluebook coverage.

**OSCOLA (Oxford Standard for Citation of Legal Authorities)**
- Official URL: https://www.law.ox.ac.uk/research-subject-groups/publications/oscola
- Dominant citation standard in UK and Commonwealth jurisdictions. Required for any international expansion targeting UK, Australian, or Canadian legal markets.

### Legal Identifier Standards

**European Case Law Identifier (ECLI)**
- Official URL: https://e-justice.europa.eu/topics/legislation-and-case-law/european-case-law-identifier-ecli_en
- EU Council standard providing a uniform, machine-readable identifier for court decisions across EU member states. Format: `ECLI:[country]:[court]:[year]:[identifier]`. Enables interoperable citation and linking across national and EU databases. Uses Dublin Core metadata and RDF/JSON-LD serialisation. Mandatory for any EU or international jurisdiction coverage.

**European Legislation Identifier (ELI)**
- Official URL: https://eur-lex.europa.eu/content/help/eurlex-content/eli.html
- EU standard providing persistent URIs for legislation and an RDF ontology (ELI Ontology v1.5, 2024) for describing legislative metadata in a machine-readable form. Published as JSON-LD or RDFa embedded in official EU legislative webpages. Critical for any regulatory monitoring agent targeting EU law.

**Uniform Electronic Legal Material Act (UELMA)**
- Official URL: https://www.aallnet.org/advocacy/government-relations/state-issues/uelma-resources/
- US model act (Uniform Law Commission, 2011) establishing technology-neutral standards for authentication, preservation, and permanent public accessibility of official electronic legal materials. Adopted by numerous US states. Relevant for any feature that presents or cites official state legal materials — authentication assertions must comply with UELMA-implementing states' requirements.

### Data & Metadata Standards

**Legal Knowledge Interchange Format (LKIF-Core)**
- Official URL: https://github.com/RinkeHoekstra/lkif-core
- OWL ontology defining basic legal concepts (norms, agents, documents, time) and their relationships. Foundation for many legal knowledge systems and relevant for a knowledge graph layer over a legal research corpus.

**Dublin Core Metadata Initiative (DCMI)**
- Official URL: https://www.dublincore.org/
- De-facto metadata standard for describing legal information resources. Both ELI and ECLI use Dublin Core terms as the base vocabulary. Relevant for structured metadata on ingested legal documents.

**Schema.org LegalDocument types**
- Official URL: https://schema.org/LegalDocument
- W3C-backed vocabulary for marking up legal documents on the web in JSON-LD or RDFa. Supports document type, jurisdiction, date, and authority metadata. Used by search engines and Linked Data pipelines to index publicly accessible legal materials.

### API & Interoperability Standards

**OpenAPI Specification 3.1**
- Official URL: https://spec.openapis.org/oas/v3.1.0
- The industry standard for describing REST APIs in a machine-readable YAML/JSON format. Any legal research API surface (citation lookup, case search, regulatory monitor) should be published with an OpenAPI 3.1 spec for client generation, documentation, and validation.

**RFC 9727 — api-catalog Well-Known URI**
- Official URL: https://datatracker.ietf.org/doc/rfc9700/
- June 2025 RFC defining a `/.well-known/api-catalog` well-known URI and link relation to facilitate automated discovery and usage of published APIs. Useful for exposing and discovering legal data APIs in a standardised way.

**Model Context Protocol (MCP) — November 2025 Specification**
- Official URL: https://modelcontextprotocol.io/specification/2025-11-25
- Anthropic-originated open standard (donated to the Linux Foundation / Agentic AI Foundation in December 2025) defining how LLM agents interact with external tools and data sources. The US Government Publishing Office (GPO) launched a public-preview GovInfo MCP server (January 2026) providing official LLM access to federal legislative and regulatory content. MCP is directly applicable as the integration layer between an LLM-based legal research assistant and legal data sources (CourtListener, GovInfo, Federal Register).

### Security & Compliance Standards

**OAuth 2.0 (RFC 6749) and RFC 9700 Security BCP**
- Official URL: https://oauth.net/2/ · https://datatracker.ietf.org/doc/rfc9700/
- Industry-standard authorisation framework for API access. RFC 9700 (Best Current Practice for OAuth 2.0 Security, January 2025) provides current security guidance. All legal research API endpoints should use OAuth 2.0 with short-lived tokens and PKCE for user-facing flows.

**OpenID Connect (OIDC)**
- Official URL: https://openid.net/developers/how-connect-works/
- Identity layer on top of OAuth 2.0. Mandatory for any multi-tenant legal research SaaS where firm-level or user-level access control and SSO integration are required.

**ISO/IEC 27001:2022 — Information Security Management**
- Official URL: https://www.iso.org/standard/82875.html
- International standard for information security management systems. Legal AI tools processing confidential client matter data (attorney-client privileged documents) require ISO 27001 certification or equivalent to satisfy enterprise law firm procurement requirements.

**SOC 2 Type II**
- Official URL: https://www.aicpa-cima.com/resources/landing/system-and-organization-controls-soc-suite-of-services
- AICPA attestation standard for trust service criteria (security, availability, processing integrity, confidentiality, privacy). Enterprise law firm procurement universally requires SOC 2 Type II reports. Critical for any hosted legal research service handling client data.

**EU AI Act (Regulation EU 2024/1689) — High-Risk AI System Obligations**
- Official URL: https://artificialintelligenceact.eu/
- The EU AI Act explicitly lists "assistance in legal interpretation and application of the law" as a high-risk AI use case, requiring registration in an EU database and compliance obligations including: data governance for training datasets, technical documentation, automatic event logging, human oversight design, and downstream deployer instructions. GPAI model obligations became effective August 2025. Applies to any legal research assistant deployed in the EU or used by EU-based lawyers for EU client matters.

**GDPR (Regulation EU 2016/679)**
- Official URL: https://gdpr.eu/
- Applies to personal data of EU data subjects processed within legal research queries. Law firms are data controllers; legal research AI providers are processors. Requirements include: a Data Processing Agreement (DPA), documented lawful basis for processing, data minimisation, records of processing activities, and a DPIA before high-risk AI processing of personal data. Attorney-client privileged content routed through third-party AI infrastructure may constitute voluntary disclosure unless the vendor operates under a DPA with appropriate access restrictions.

**ABA Model Rule 1.1 Comment 8 (Competence — Technology)**
- Official URL: https://www.americanbar.org/groups/professional_responsibility/publications/model_rules_of_professional_conduct/rule_1_1_competence/
- Requires attorneys to understand the benefits and risks of technology relevant to their practice. Specifically requires understanding AI tool limitations and maintaining client confidentiality when using AI. Any legal research assistant must display an attorney verification disclosure and provide clear documentation of citation accuracy methodology to support attorney competence obligations.

---

## Similar Products — Developer Documentation & APIs

### CourtListener / Free Law Project
- **Description:** Open-source legal case database indexing tens of millions of US federal and state court opinions. The primary free, openly licensed legal data infrastructure in the US; the foundational data source for any OSS legal research assistant.
- **API Documentation:** https://www.courtlistener.com/help/api/rest/ (REST API v4.4)
- **Specific Endpoints:**
  - Case Law APIs: https://www.courtlistener.com/help/api/rest/case-law/
  - Legal Search API: https://www.courtlistener.com/help/api/rest/search/
  - Citation Lookup & Verification API: https://www.courtlistener.com/help/api/rest/citation-lookup/
  - Legal Citation APIs: https://www.courtlistener.com/help/api/rest/citations/
  - PACER Data APIs: https://www.courtlistener.com/help/api/rest/pacer/
  - Bulk Data Downloads: https://www.courtlistener.com/help/api/bulk-data/
- **SDKs/Libraries:** Juriscraper (Python, BSD licence, court scraping); Eyecite (Python, BSD licence, citation extraction — https://github.com/freelawproject/eyecite); eyecite on PyPI: https://pypi.org/project/eyecite/
- **Rate Limits:** 5,000 queries/hour for authenticated users
- **Standards:** REST/JSON; public domain data (US court opinions are government works under 17 U.S.C. § 105)
- **Authentication:** Token-based API authentication for rate-limited access; unauthenticated access available at lower rates

### GovInfo (US Government Publishing Office)
- **Description:** Official US government portal providing authoritative access to federal legislative and regulatory content including the Code of Federal Regulations (CFR), Federal Register, United States Code (USC), and congressional documents. The authoritative source for US regulatory monitoring.
- **API Documentation:** https://www.govinfo.gov/developers · https://github.com/usgpo/api
- **Federal Register REST API:** https://www.federalregister.gov/reader-aids/developer-resources/rest-api
- **Bulk Data:** https://www.federalregister.gov/reader-aids/developer-resources/bulk-data (CFR XML from 1996 to present; Federal Register XML)
- **MCP Server:** GovInfo MCP public preview launched January 2026 — https://www.govinfo.gov/features/mcp-public-preview — enabling LLM agents to access GovInfo content and metadata directly via Model Context Protocol
- **Authentication:** api.data.gov key (free registration)
- **Standards:** REST/JSON; XML bulk data; MCP (November 2025 spec)

### LexisNexis Developer Portal (Lexis APIs)
- **Description:** Enterprise legal research and data enrichment APIs including the Cognitive APIs (entity recognition, document classification) and Protégé API (AI-powered legal research powered by Harvey AI). Provides programmatic access to LexisNexis's database of case law, secondary sources, and regulatory content.
- **API Documentation:** https://dev.lexisnexis.com/ · https://www.lexisnexis.com/en-us/products/lexis-api.page
- **Developer Portal:** https://dev.lexisnexis.com/overview
- **Getting Started Guide:** https://dev.lexisnexis.com/gettingStarted
- **SDKs/Libraries:** Available through the developer portal post-approval (sandbox environment provided)
- **Standards:** REST/JSON; enterprise entitlement management
- **Authentication:** Enterprise-grade OAuth 2.0 with entitlement management; credentials provisioned after vendor approval

### Thomson Reuters Developer Portal (Westlaw APIs)
- **Description:** Over 100 APIs covering legal, tax, risk, and fraud data. Key legal APIs include: Westlaw Litigation Analytics API (judge and court analytics), Dockets API (structured court docket data), Practical Law Data API (expert-authored practice guides), and SEC Filings API. Commercial access required.
- **API Documentation:** https://tr.com/legal-api (Developer Portal launched May 2024)
- **Dockets API:** https://www.legaltechnologyhub.com/vendors/dockets-api-from-westlaw-edge-by-thomson-reuters/
- **Practical Law Data API:** https://www.legaltechnologyhub.com/vendors/practical-law-data-api-by-thomson-reuters/
- **Standards:** REST/JSON; commercial licensing required
- **Authentication:** OAuth 2.0; enterprise agreements required for access

### Harvey AI Developer API
- **Description:** Enterprise legal AI platform API providing legal reasoning, drafting, document analysis, and agentic research capabilities. Exposes Harvey's legal LLM as "legal intelligence as a service" with enterprise governance controls.
- **API Documentation:** https://developers.harvey.ai/guides/introduction
- **Core API Capabilities:**
  - Assistant completion (legal reasoning, drafting, analysis, Q&A)
  - Vault APIs (document upload and knowledge base management)
  - RAG grounding via Vault (retrieve and cite internal documents)
  - Audit logs and history exports for compliance
  - Client matters alignment with billing codes
- **Integration:** iManage (document management); NetDocuments; Microsoft 365
- **Standards:** REST/JSON; enterprise audit logging
- **Authentication:** Enterprise API key; contract required (20-seat minimum); documentation at developers.harvey.ai

### Clio Developer Hub (including vLex)
- **Description:** Practice management platform API (Clio Manage and Clio Grow) with integration points for legal research following the Clio acquisition of vLex for $1B in 2025. The vLex Developer Portal provides separate API access to the global legal database (1B+ documents, 3M+ subscribers).
- **Clio API Documentation:** https://docs.developers.clio.com/
- **Clio API V4 Reference:** https://docs.developers.clio.com/api-reference/
- **vLex Developer Portal:** https://developer.vlex.com/
- **vLex APIs List:** https://developer.vlex.com/apis
- **Standards:** REST/JSON; OpenAPI
- **Authentication:** OAuth 2.0 (Clio); API key (vLex developer access)

### Fastcase Legal Data API (now vLex-owned)
- **Description:** Legal research data API providing access to 400+ million documents and docket sheets from federal courts, agencies, and state/county courts. As of May 2025, Fastcase is no longer available as a separately purchased product outside bar association memberships; the Legal Data API continues as a commercial data feed product under vLex ownership.
- **API Documentation:** https://www.fastcase.com/solutions/legal-data-api/
- **Standards:** REST/JSON; live data feeds and consulting services available
- **Authentication:** Commercial data licensing agreement required

### EUR-Lex (Official EU Law Portal)
- **Description:** Official portal for European Union law covering all legislation, case law, treaties, and regulatory publications in 24 languages. Supports bulk download and API access for programmatic retrieval of EU legal materials. Essential for EU regulatory monitoring agent functionality.
- **API Documentation:** https://eur-lex.europa.eu/content/help/faq/reuse-contents-eurlex-details.html
- **ECLI Search Engine:** https://e-justice.europa.eu/topics/legislation-and-case-law/european-case-law-identifier-ecli-search-engine_en
- **Standards:** REST/JSON; RDF/JSON-LD (ELI ontology); ECLI identifiers; SPARQL endpoint available
- **Authentication:** Open access (no authentication required for basic retrieval)

### CanLII (Canadian Legal Information Institute)
- **Description:** Pan-Canadian repository of case law and legislation across all Canadian federal, provincial, and territorial jurisdictions. Provides an API for developers requiring programmatic access to Canadian primary legal materials — particularly relevant for any international coverage expansion.
- **API Documentation:** API key required; apply via https://www.canlii.org/en/
- **Standards:** REST/JSON
- **Authentication:** API key (free for non-commercial research; commercial licensing for embedded use)

---

## Notes

**Open Legal Data Ecosystem**
The open legal data layer in the US is more mature than any other jurisdiction: CourtListener (case law), GovInfo (federal legislation and regulations), and the Federal Register API together provide comprehensive programmatic access to US primary law at no cost. The GovInfo MCP server (January 2026) is a significant development — GPO's official endorsement of Model Context Protocol means an OSS legal research assistant can use MCP as the authoritative integration protocol for US federal law.

**International Coverage Gap**
No single open API provides cross-jurisdictional case law comparable to CourtListener for non-US jurisdictions. BAILII (UK/Ireland) and AustLII (Australia) do not offer public APIs at the time of research; CanLII and EUR-Lex do. This is a meaningful constraint for any international expansion feature.

**Commercial API Access Barriers**
Westlaw, Lexis, and Harvey APIs all require commercial agreements and are not suitable as open-source project dependencies. Any OSS legal research assistant must build exclusively on open data sources (CourtListener, GovInfo, Federal Register, EUR-Lex, CanLII) for its retrieval layer; commercial API access may be offered as optional enterprise add-ons.

**EU AI Act Classification Risk**
"Assistance in legal interpretation and application of the law" is explicitly classified as high-risk under the EU AI Act. Any legal research assistant deployed in or for EU markets (including SaaS accessed by EU-based lawyers) must comply with high-risk AI system obligations effective from August 2025 (GPAI) and August 2026 (full high-risk application). This includes technical documentation, logging, human oversight design, and conformity assessment obligations.

**MCP as Emerging Integration Standard**
The Model Context Protocol (MCP) is emerging as the standard integration protocol between LLM agents and external data sources. GovInfo's public preview MCP server (January 2026) establishes official federal government support. An OSS legal research assistant should expose its capabilities as an MCP server to enable integration with Claude, GPT-based agents, and other MCP-compatible orchestration frameworks — maximising ecosystem reach without requiring bespoke integrations.
