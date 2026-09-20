# Insurance Compliance

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg)](LICENSE)

A curated list of standards, model laws, and tooling for **US insurance regulatory compliance and cybersecurity** — the state-by-state regulatory system built around the National Association of Insurance Commissioners (NAIC) and its model laws, rather than a single federal statute or certifiable framework.

**Scope:** Anything that materially helps a practitioner scope, implement, or examine against US insurance regulatory obligations — the NAIC's model cybersecurity law, solvency and enterprise-risk requirements, market conduct examination practice, and the accreditation system that holds the whole structure together. GLBA and NYDFS 500, which also apply to insurers, are covered in full by the companion finserv-compliance list and are only cross-referenced here (see Related Lists). NIST CSF, ISO/IEC 27001, and PCI-DSS sit outside this list's scope and are covered by the companion Security Frameworks list; COBIT, COSO, and SOX/ITGC by IT Audit & Controls.

**Why now:** NAIC's own Summer 2026 model-law tracking chart shows 26 states plus Puerto Rico have now adopted the Insurance Data Security Model Law (MDL-668) in substantially similar form, with Tennessee adopting portions of it — up from roughly 21 states as recently as mid-2024, and with fresh 2025-2026 enactments in jurisdictions including Missouri (2026), Utah (2026), and North Dakota (2025). That leaves a real, and shrinking, gap: large states including California, Massachusetts, New York (which runs its own 23 NYCRR Part 500 instead), and Texas still address insurer cybersecurity only through related-but-different statutes, so adoption status has to be checked state by state rather than assumed. The NAIC's ORSA Implementation Subgroup is also expected to update the ORSA Guidance Manual in 2026 to sharpen capital-transparency and filing-date guidance, and the 2026 editions of both the Market Regulation Handbook and Financial Condition Examiners Handbook are now current.

Contributions welcome.

---

## Contents

- [Why These Frameworks Matter](#why-these-frameworks-matter)
- [How to Approach Implementation](#how-to-approach-implementation)
- [NAIC Insurance Data Security Model Law (MDL-668)](#naic-insurance-data-security-model-law-mdl-668)
- [NAIC ORSA and Risk-Based Capital](#naic-orsa-and-risk-based-capital)
- [McCarran-Ferguson Act and Market Conduct Examinations](#mccarran-ferguson-act-and-market-conduct-examinations)
- [NAIC Accreditation and Model Law Adoption Tracking](#naic-accreditation-and-model-law-adoption-tracking)
- [Cross-Framework Mapping and GRC Platforms](#cross-framework-mapping-and-grc-platforms)
- [Assessment, Audit, and Risk Analysis Resources](#assessment-audit-and-risk-analysis-resources)
- [Certifications and Training](#certifications-and-training)
- [Government and Standards Bodies](#government-and-standards-bodies)
- [Learning Resources](#learning-resources)
- [Related Lists](#related-lists)

---

## Why These Frameworks Matter

Insurance is the one sector in this series of lists with no federal regulator at all. The McCarran-Ferguson Act of 1945 (15 U.S.C. §§ 1011-1015) declares that "the continued regulation and taxation by the several States of the business of insurance is in the public interest" and provides that federal statutes do not override state insurance law unless Congress says so explicitly. That single sentence is why there is no Office of the Comptroller of the Currency or SEC equivalent for insurance: each of the 50 states, DC, and five US territories writes and enforces its own insurance code, licenses its own insurers, and runs its own examinations.

The NAIC itself is not a regulator. It is a voluntary standard-setting association *of* the state insurance commissioners, and it has no statutory authority to bind anyone. What it does instead is draft **model laws** — the Insurance Data Security Model Law (MDL-668), the Risk Management and Own Risk and Solvency Assessment Model Act (#505), the Risk-Based Capital for Insurers Model Act (#312), and dozens of others — which individual state legislatures then adopt, amend, or ignore entirely. A model law only has legal force in a given state once that state's legislature enacts it, and states are free to adopt an older version, adopt only portions, or address the same subject through unrelated legislation. This is the single most important structural fact for a practitioner to internalise: "is my company compliant with MDL-668?" is not a yes/no question until you specify *which state*.

Two forces pull this patchwork back toward consistency. First, the NAIC's Financial Regulation Standards and Accreditation Program conditions a state's accreditation on adopting certain solvency-related model laws, which is what has kept RBC and ORSA close to uniform nationally even without federal law. Second, insurers are also directly subject to federal financial-services law that happens to reach insurance through broad statutory definitions: the Gramm-Leach-Bliley Act's Safeguards Rule and Privacy Rule apply to insurers as "financial institutions," and the New York Department of Financial Services' 23 NYCRR Part 500 applies directly to any insurer licensed in New York, not just to banks. Both are covered in full by the companion [finserv-compliance](https://github.com/garynair/finserv-compliance) list and are only cross-referenced here rather than re-documented. MDL-668, this list's load-bearing cybersecurity framework, was itself modelled closely on Part 500 — the NAIC built it a year after Part 500 took effect, borrowing its risk-assessment, CISO-designation, and breach-notification structure — but it is the NAIC's own instrument, adopted state by state, and often diverges from Part 500 in scope, thresholds, and exemptions even where a state has enacted it in "substantially similar" form.

In practice, most insurance compliance programmes are built around three questions rather than one framework: which states are you licensed in, has each of those states adopted MDL-668 (or does NYDFS or GLBA already cover you there), and are you above the ORSA/RBC thresholds that trigger solvency-specific filings. None of this is certifiable in the HITRUST or ISO 27001 sense — there is no "MDL-668 certified" badge — because state insurance commissioners examine and enforce directly rather than delegating to an accreditation body.

---

## How to Approach Implementation

1. **Map your state licensure footprint.** Insurance regulatory obligations attach to where you are licensed (admitted) or where you write surplus lines business, not to where you are headquartered — start by listing every state and territory in which you hold a certificate of authority.
2. **Check GLBA and NYDFS 500 applicability first.** GLBA's Safeguards and Privacy Rules apply to every US insurer regardless of state, and 23 NYCRR Part 500 applies directly if you are licensed in New York — both are fully covered in the companion finserv-compliance list and should be scoped before anything below.
3. **Determine MDL-668 adoption status in each remaining licensed state.** Use the NAIC's model-law state tracker to classify each state as full adoption, previous-version adoption, related-activity-only, or no current activity, since the compliance obligation (and the version of it) differs by category.
4. **Build your information security programme against the strictest applicable version.** Where a state has adopted MDL-668, implement the risk assessment, board oversight, incident-response, and third-party-service-provider-oversight requirements it specifies; where NYDFS or GLBA already applies, extend that programme rather than building a separate one.
5. **Confirm whether you meet ORSA's filing thresholds.** ORSA applies to individual insurers writing over $500 million in annual direct premium and insurance groups over $1 billion; if you are above either threshold, build the risk management framework the Risk Management and ORSA Model Act requires.
6. **File the ORSA Summary Report on the required cycle.** Follow the NAIC ORSA Guidance Manual's structure (risk management framework, own assessment of risk, group risk capital) and file with your lead state regulator; the filing is confidential and not a public disclosure.
7. **Calculate and monitor Risk-Based Capital continuously, not just annually.** Use the RBC formula for your line of business (life/health or property-casualty) and track your ratio against the four regulatory action levels — company action, regulatory action, authorised control, and mandatory control — since falling through a threshold triggers automatic regulatory intervention.
8. **Prepare for market conduct examinations separately from financial examinations.** These test how you treat policyholders (claims handling, underwriting, sales practices), not your solvency — use the NAIC Market Regulation Handbook to understand examiner methodology and file Market Conduct Annual Statement (MCAS) data where required.
9. **Track your states' accreditation status.** A state's NAIC accreditation means its financial examination and solvency-regulation practices meet the NAIC's baseline standards, which gives you a predictable floor for what a financial examination will look like even before it is scheduled.
10. **Monitor continuously at the state level, not just the NAIC level.** Because McCarran-Ferguson routes every substantive change through individual state legislatures, a model law's adoption status can change in any of the 56 jurisdictions in any legislative session — build a recurring review of the state tracker into your compliance calendar rather than treating "adopted" as permanent.

---

## NAIC Insurance Data Security Model Law (MDL-668)

**Applicability:** legal force only where a state legislature has enacted it; as of NAIC's Summer 2026 tracking chart, 26 states have adopted the current version in substantially similar form, Puerto Rico has adopted it, and Tennessee has adopted portions of it. Several other states (including New York, which runs 23 NYCRR Part 500 instead) address the same subject matter through related but non-identical statutes. Not certifiable — enforcement runs through each state insurance commissioner directly.

- [NAIC Insurance Data Security Model Law (#668)](https://content.naic.org/sites/default/files/model-law-668.pdf) - The model law's full text, requiring insurers to develop, implement, and maintain an information security programme, investigate cybersecurity events, and notify the state commissioner of them. Closely modelled on 23 NYCRR Part 500 but is the NAIC's own instrument, adopted (or not) state by state rather than imposed directly.
- [NAIC Insurance Data Security Model Law — Project History (PH-668)](https://content.naic.org/sites/default/files/model-laws-project-history-668.pdf) - The NAIC's own account of why each provision exists, useful for understanding the reasoning behind a requirement when a state's enacted version departs from the model text.
- [NAIC Insurance Data Security Model Law — State Adoption Tracker (ST-668)](https://content.naic.org/sites/default/files/model-law-state-page-668.pdf) - The authoritative, regularly updated chart classifying every state and territory as Model Adoption, Previous Version, Related Activity, or No Current Activity, with citations to the actual state statute or regulation. Start here before assuming MDL-668 applies in any given state.
- [NAIC Insurance Topics: Cybersecurity](https://content.naic.org/insurance-topics/cybersecurity) - The NAIC's practitioner-facing hub summarising the model law, linking to the NAIC Roadmap for Cybersecurity Consumer Protections, and tracking related committee activity.

---

## NAIC ORSA and Risk-Based Capital

**Applicability:** ORSA applies to individual insurers with over $500 million in annual direct premium and insurance groups over $1 billion, once the underlying Risk Management and ORSA Model Act (#505) is adopted in the insurer's state of domicile (adopted in nearly all states, given its status as an accreditation standard); Risk-Based Capital applies to essentially all US insurers as a condition of maintaining a certificate of authority. Neither is certifiable — both are filed directly with state regulators.

- [NAIC ORSA Guidance Manual](https://content.naic.org/sites/default/files/publication-orsa-guidance-manual.pdf) - The NAIC's free, official guidance on structuring and filing the ORSA Summary Report, covering the risk management framework, the insurer's own assessment of risk, and group risk capital.
- [NAIC Insurance Topics: Own Risk and Solvency Assessment (ORSA)](https://content.naic.org/insurance-topics/own-risk-and-solvency-assessment) - The NAIC's overview of ORSA's origins in the post-2008 Solvency Modernization Initiative, current filing thresholds, and the ORSA Implementation Subgroup that oversees the programme.
- [Risk Management and Own Risk and Solvency Assessment Model Act (#505)](https://content.naic.org/sites/default/files/model-law-505.pdf) - The model act's full text, establishing the risk management framework requirement, the annual ORSA obligation, the confidential Summary Report, and exemption criteria.
- [NAIC Insurance Topics: Risk-Based Capital](https://content.naic.org/insurance-topics/risk-based-capital) - The NAIC's overview of how RBC replaced fixed capital standards after the 1980s insurer insolvency wave, how the formula-based system works by line of business, and the four regulatory intervention levels from company action to mandatory control.
- [Risk-Based Capital (RBC) for Health Organizations Model Act (#315)](https://content.naic.org/sites/default/files/model-law-315.pdf) - The RBC model act specific to health organisations, paralleling Model Act #312 for insurers writing health business.
- [Risk-Based Capital (RBC) for Insurers Model Act (#312)](https://content.naic.org/sites/default/files/model-law-312.pdf) - The model act establishing minimum capital standards and regulatory intervention authority for life and property-casualty insurers based on company-specific risk profile.

---

## McCarran-Ferguson Act and Market Conduct Examinations

**Applicability:** McCarran-Ferguson is the foundational federal statute that reserves insurance regulation to the states; market conduct examinations are conducted directly by each state insurance department under its own examination authority, guided by NAIC's uniform handbook. Not certifiable — market conduct exams are periodic regulatory audits, not a pass/fail credential.

- [McCarran-Ferguson Act (15 U.S.C. §§ 1011-1015)](https://www.law.cornell.edu/uscode/text/15/1011) - The full statutory text (Cornell Legal Information Institute) declaring that continued state regulation and taxation of insurance is in the public interest, the legal basis for the entire state-based system this list documents.
- [NAIC Insurance Topics: McCarran-Ferguson Act](https://content.naic.org/insurance-topics/mccarran-ferguson-act) - The NAIC's own explanation of the Act's history — from the 1869 *Paul v. Virginia* decision through its 1944 reversal and the 1945 statutory response — and its continuing antitrust and federalism implications.
- [NAIC Insurance Topics: Market Conduct Regulation](https://content.naic.org/insurance-topics/market-conduct-regulation) - The NAIC's overview distinguishing market conduct regulation (how insurers treat consumers) from solvency regulation, covering the Market Conduct Annual Statement (MCAS) and current regulatory focus areas including AI oversight.
- [NAIC Market Regulation Handbook (2025)](https://content.naic.org/sites/default/files/publication-market-reg-hb.pdf) - The NAIC's comprehensive, free reference combining market conduct examination and analysis guidance into one source, the closest thing to an official market conduct exam protocol.

---

## NAIC Accreditation and Model Law Adoption Tracking

**Applicability:** accreditation is a state-to-state status, not an insurer-facing certification; all 50 states and US territories currently hold NAIC accreditation. Useful primarily as a practitioner's shortcut for predicting examination rigor and model-law adoption likelihood across a multi-state licence footprint.

- [NAIC Financial Regulation Standards and Accreditation (F) Committee](https://content.naic.org/committees/f/financial-regulation-standards-accreditation-cmte) - The NAIC committee that administers the accreditation programme, interprets model laws against state statutes, conducts the five-year comprehensive reviews and annual desk audits, and maintains the Accreditation Program Manual.
- [NAIC Insurance Topics: Accreditation](https://content.naic.org/insurance-topics/accreditation) - The NAIC's overview of the Financial Regulation Standards and Accreditation Program, established in 1989 after a wave of insurer insolvencies, explaining how accreditation conditions state solvency-oversight authority on adopting specific model laws.
- [NAIC Model Laws, Regulations, Guidelines and Other Resources](https://content.naic.org/model-laws) - The NAIC's searchable database of every model law, each with its model text (MO), state-adoption tracking page (ST), and project history (PH) — the primary tool for checking adoption status of any model law, not just MDL-668, across all 56 jurisdictions.

---

## Cross-Framework Mapping and GRC Platforms

No HITRUST-equivalent body exists to combine insurance's overlapping state, NAIC, and federal obligations into one assessable control set — most insurers instead run a general-purpose risk or GRC platform underneath their state-specific compliance work. Several platforms already listed in the companion [finserv-compliance](https://github.com/garynair/finserv-compliance) list (Mitratech Continuity, Wolters Kluwer OneSumX) also publish insurance-industry modules; check that list before evaluating a new platform, since it is not duplicated in full here.

- [Origami Risk](https://www.origamirisk.com/) - Commercial SaaS platform purpose-built for P&C insurance carriers (policy administration, claims, RMIS, TCOR analytics) alongside general GRC modules for compliance management, internal audit, and third-party risk. Recognised in Gartner's Magic Quadrant for SaaS P&C Insurance Core Platforms.
- [Riskonnect](https://riskonnect.com/) - Commercial enterprise risk platform combining a GRC suite (compliance, internal audit, policy management) with an Insurable Risk suite (RMIS, claims and policy administration) used by insurance buyers and carriers alike.
- [Secure Controls Framework (SCF)](https://securecontrolsframework.com/) - Free, open (Creative Commons) meta-framework mapping outward to 200+ laws, regulations, and frameworks. General-purpose rather than insurance-specific; shared with the companion [Security Frameworks](https://github.com/garynair/security-frameworks), [IT Audit & Controls](https://github.com/garynair/it-audit-controls), and [finserv-compliance](https://github.com/garynair/finserv-compliance) lists.

---

## Assessment, Audit, and Risk Analysis Resources

- [NAIC Financial Condition Examiners Handbook (2026)](https://content.naic.org/sites/default/files/publication-fc-examiner-hb.pdf) - The NAIC's free examiner reference for establishing and running a financial (solvency) examination system, with phase-by-phase instructions — the financial-exam counterpart to the Market Regulation Handbook.
- [NAIC Market Regulation Handbook (2025)](https://content.naic.org/sites/default/files/publication-market-reg-hb.pdf) - Listed above under Market Conduct Examinations; included here as the primary market-conduct audit protocol a practitioner should read before an examination.
- [NAIC ORSA Guidance Manual](https://content.naic.org/sites/default/files/publication-orsa-guidance-manual.pdf) - Listed above under ORSA; the practical risk-analysis methodology reference for structuring the required annual self-assessment.

---

## Certifications and Training

- [ARM (Associate in Risk Management)](https://web.theinstitutes.org/designations/associate-risk-management) - The Institutes' risk-management credential (three courses plus ethics), aimed at risk management professionals and agents/brokers building consultative, enterprise-risk skills; counts toward the CPCU designation.
- [CPCU (Chartered Property Casualty Underwriter)](https://web.theinstitutes.org/designations/cpcu) - The Institutes' flagship leadership credential in risk management and insurance, a ten-course programme widely regarded as the most valuable general insurance designation for underwriting, claims, and risk-management leadership roles.
- [IRES AIE/CIE (Accredited/Certified Insurance Examiner)](https://www.go-ires.org/aie-cie) - The Insurance Regulatory Examiners Society's credential for state regulatory examiners, awarded after two-plus years of regulatory work experience and coursework in a specific line (property-casualty, life-annuities, or health); CIE requires cross-training in a second line.
- [IRES MCM (Market Conduct Management)](https://www.go-ires.org/mcm-designation) - IRES's market conduct examination credential for regulators and company compliance personnel, covering exam procedures, exam management, report writing, and data analytics, earned via a textbook, a 2.5-day programme, and a certification exam.

---

## Government and Standards Bodies

- [International Association of Insurance Supervisors (IAIS)](https://www.iais.org/) - The global standard-setting body for insurance supervision, representing regulators from 200+ jurisdictions; publishes the Insurance Core Principles (ICPs) that inform, but do not bind, US state regulation.
- [IRES (Insurance Regulatory Examiners Society)](https://www.go-ires.org/) - The professional association of state and federal insurance regulatory examiners, publisher of the AIE/CIE and MCM designations and a source of examiner continuing education.
- [NAIC State Insurance Department Directory](https://content.naic.org/state-insurance-departments) - The NAIC's own directory and interactive map for locating every state, DC, and territorial insurance department's contact information — the practitioner's starting point for a multi-state licence footprint rather than a list of 56 individual department links.
- [National Association of Insurance Commissioners (NAIC)](https://content.naic.org/) - The voluntary standard-setting association of the 56 state, DC, and territorial insurance commissioners; drafts the model laws this list documents but has no independent statutory authority of its own.

---

## Learning Resources

- [IAIS Insurance Core Principles and ComFrame](https://www.iais.org/activities-topics/standard-setting/icps-and-comframe/) - The globally accepted framework for insurance supervision and its extension for internationally active insurance groups, useful background for understanding how US state regulation compares internationally.
- [Insurance Information Institute (Triple-I)](https://www.iii.org/) - A widely cited, free industry research and education hub covering insurance lines, emerging risks (cyber, catastrophe, litigation trends), and plain-language explainers aimed at both practitioners and the public.
- [NAIC Glossary of Insurance Terms](https://content.naic.org/glossary-insurance-terms) - The NAIC's own plain-language glossary of commonly used insurance terminology, maintained by its Research and Actuarial Department.

---

## Related Lists

- [FinServ Compliance](https://github.com/garynair/finserv-compliance) - A companion curated list covering GLBA/FFIEC, NYDFS 500, SEC/FINRA, BSA/AML/OFAC, and model risk management — the source for full coverage of GLBA and NYDFS 500, both of which apply to insurers but are only cross-referenced here.
- [Healthcare Compliance](https://github.com/garynair/healthcare-compliance) - A companion curated list covering HIPAA, HITECH, and HITRUST CSF, the healthcare-sector equivalent of this list and the original template it follows.
- [IT Audit & Controls](https://github.com/garynair/it-audit-controls) - A companion curated list covering COBIT, COSO, and ITGC/ITAC — the source for anything SOX-, ITGC-, or COBIT-related that is out of scope here.
- [Security Frameworks](https://github.com/garynair/security-frameworks) - A companion curated list covering NIST CSF, ISO/IEC 27001, and PCI-DSS — the source for the general-purpose control framework most insurers layer underneath the state-specific obligations above.

Also part of this series: **Federal Compliance** (FedRAMP, CMMC, NIST SP 800-171/800-53, FISMA, and related federal contracting frameworks) is being built locally alongside this list and is not yet published to GitHub, so it is named here rather than linked.

---

## Contributing

PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the criteria a new entry must meet.

## Licence

This list is published under [CC0 1.0 Universal](LICENSE). The linked resources retain their own licences.
