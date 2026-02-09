# Execution Feasibility Ranker: Task Definitions

This document defines the tasks that comprise the Execution Feasibility Ranker function. Each task evaluates a specific dimension of execution feasibility across all startup ideas simultaneously, producing comparative rankings that inform the final probability distribution.

The function operates on the Four Pillars defined in ESSAY.md: Technical Feasibility, Resource Requirements, Regulatory and Legal Complexity, and Execution Risk Profile. Each pillar is decomposed into specific evaluation tasks.

---

## Pillar I: Technical Feasibility Tasks

### Task 1: Technology Maturity Ranking

**Purpose**: Rank startup ideas by the maturity level of the technology they require.

**Description**: Compare all startup ideas to determine which rely on established, battle-tested technologies versus those requiring emerging or speculative technologies. Ideas using proven tech stacks (standard web/mobile frameworks, established databases, proven infrastructure) should rank higher than those requiring cutting-edge or not-yet-invented technologies. Consider whether the core technology exists, works reliably, and is accessible.

**Evaluation Criteria**:
- Does the idea use well-understood, production-ready technology?
- Does it rely on emerging tech that works in principle but may have gaps?
- Does it require breakthroughs that don't yet exist?
- Is there prior art demonstrating the technical approach works?

**Output**: Comparative ranking where ideas using more mature technology receive higher feasibility scores.

---

### Task 2: Integration Complexity Ranking

**Purpose**: Rank startup ideas by the complexity of integrating their component technologies.

**Description**: Compare all startup ideas to assess how many different systems, technologies, and components must work together seamlessly. A simple mobile app with a basic backend ranks higher than a system requiring hardware manufacturing, AI processing, global logistics, and regulatory systems to coordinate perfectly. Even mature technologies become risky when integration complexity is high.

**Evaluation Criteria**:
- How many distinct technical systems must integrate?
- Do the integrations cross domains (software-hardware, digital-physical)?
- Is coordination required across multiple external platforms or APIs?
- Are there known integration patterns, or is novel coordination required?

**Output**: Comparative ranking where simpler integration requirements receive higher feasibility scores.

---

### Task 3: Technical Talent Accessibility Ranking

**Purpose**: Rank startup ideas by how accessible the required technical expertise is.

**Description**: Compare all startup ideas to assess the availability of talent needed to build them. Ideas requiring common skill sets (web development, mobile apps, standard data engineering) rank higher than those needing rare specialists (quantum computing experts, novel drug discovery scientists, specialized chip designers). Consider both the size of the talent pool and the competition for that talent.

**Evaluation Criteria**:
- Can generalist engineers build this, or are specialists required?
- How large is the pool of people with the necessary skills?
- Is the required expertise taught in standard programs or highly specialized?
- Are there dozens, hundreds, thousands, or millions of qualified people?

**Output**: Comparative ranking where ideas requiring more accessible talent receive higher feasibility scores.

---

### Task 4: MVP Buildability Ranking

**Purpose**: Rank startup ideas by how quickly and easily a minimum viable product can be built.

**Description**: Compare all startup ideas to assess the path to a working prototype. Ideas where an MVP can be built in weeks by a small team using standard tools rank higher than those requiring years of development, specialized equipment, or large teams before any functional version exists. The ability to iterate quickly is a strong feasibility signal.

**Evaluation Criteria**:
- Can a functional MVP be built in weeks or months, or does it require years?
- Does building a prototype require specialized equipment or facilities?
- Can a small team build it, or is a large organization needed from the start?
- Are there existing tools, frameworks, and platforms that accelerate development?

**Output**: Comparative ranking where faster, easier MVP development receives higher feasibility scores.

---

## Pillar II: Resource Requirements Tasks

### Task 5: Capital Intensity Ranking

**Purpose**: Rank startup ideas by how much capital they require to reach viability.

**Description**: Compare all startup ideas to assess their funding requirements. Bootstrappable businesses that can reach profitability on founder effort rank highest. Seed-fundable ideas requiring modest external capital rank next. Venture-scale ideas needing significant funding before proving the model rank lower. Capital-intensive ideas requiring massive funding with long timelines rank lowest. Each funding round is a risk gate that compounds execution difficulty.

**Evaluation Criteria**:
- Can this reach profitability with minimal external capital?
- How much funding is needed before the model can be validated?
- How many funding rounds must be successfully completed?
- What is the burn rate before revenue, and how long until break-even?

**Output**: Comparative ranking where lower capital requirements receive higher feasibility scores.

---

### Task 6: Time to Market Ranking

**Purpose**: Rank startup ideas by how long it takes to reach market.

**Description**: Compare all startup ideas to assess the timeline from start to launch. Ideas that can launch in weeks or months rank higher than those requiring years of development. Long timelines mean more runway to fund, more things that can go wrong, market shifts during development, team cohesion challenges, and competitive emergence risk.

**Evaluation Criteria**:
- How long from start until a product can be sold or used?
- Are there inherent timeline constraints (clinical trials, manufacturing, regulatory)?
- Can development be parallelized or is it necessarily sequential?
- How much of the timeline is under the founders' control vs. external dependencies?

**Output**: Comparative ranking where shorter time-to-market receives higher feasibility scores.

---

### Task 7: External Dependency Ranking

**Purpose**: Rank startup ideas by their dependence on external partners and infrastructure.

**Description**: Compare all startup ideas to assess how much they rely on factors outside the founders' control. Ideas that can be built entirely with internal resources rank highest. Those requiring manufacturing partnerships, distribution deals, platform access, or regulatory relationships rank lower. Each external dependency is a potential point of failure or delay.

**Evaluation Criteria**:
- Can this be built entirely with internal team resources?
- Are manufacturing, distribution, or platform partnerships required?
- Must relationships be established with regulators or gatekeepers?
- How much leverage do external parties have over the startup's success?

**Output**: Comparative ranking where fewer external dependencies receive higher feasibility scores.

---

## Pillar III: Regulatory and Legal Complexity Tasks

### Task 8: Regulatory Burden Ranking

**Purpose**: Rank startup ideas by the weight of regulatory requirements they face.

**Description**: Compare all startup ideas to assess regulatory overhead. Unregulated or lightly regulated ideas (standard software, content, consumer products) rank highest. Industry-regulated ideas (fintech, edtech, real estate) rank lower. Heavily regulated ideas (healthcare, aviation, pharmaceuticals) rank lower still. Ideas touching prohibited or restricted domains rank lowest.

**Evaluation Criteria**:
- Does this operate in a regulated industry?
- What approvals, licenses, or certifications are required?
- Is ongoing compliance monitoring required?
- Are there approval processes that take months or years (FDA, FAA, etc.)?

**Output**: Comparative ranking where lighter regulatory burden receives higher feasibility scores.

---

### Task 9: Jurisdictional Complexity Ranking

**Purpose**: Rank startup ideas by the complexity of operating across legal jurisdictions.

**Description**: Compare all startup ideas to assess multi-jurisdictional challenges. Ideas that can operate in a single, clear jurisdiction rank highest. Those requiring compliance across multiple states or countries face compounded burden. International operations multiply regulatory effort, data protection requirements, and legal exposure.

**Evaluation Criteria**:
- Can this operate in a single, well-understood jurisdiction?
- Does it require multi-state or multi-country compliance?
- Are there conflicting regulations across target jurisdictions?
- How complex is data protection compliance for the target markets?

**Output**: Comparative ranking where simpler jurisdictional requirements receive higher feasibility scores.

---

### Task 10: Legal Defensibility Ranking

**Purpose**: Rank startup ideas by their exposure to legal challenges beyond regulation.

**Description**: Compare all startup ideas to assess legal risks including patent encumbrance, trademark conflicts, liability exposure, and contractual constraints. Ideas with clear legal paths and minimal IP entanglement rank highest. Those building in patent-dense fields, facing trademark challenges, carrying liability for harm, or constrained by platform terms rank lower.

**Evaluation Criteria**:
- Is the space crowded with patents that could block execution?
- Are there potential trademark conflicts with established players?
- What liability exposure exists if the product causes harm?
- Does building on existing platforms create contractual constraints?

**Output**: Comparative ranking where clearer legal paths receive higher feasibility scores.

---

## Pillar IV: Execution Risk Profile Tasks

### Task 11: Path Clarity Ranking

**Purpose**: Rank startup ideas by how well-defined the path to success is.

**Description**: Compare all startup ideas to assess whether established playbooks exist. Ideas following proven paths (SaaS, e-commerce, professional services) rank highest. Those with partially mapped territories (novel marketplaces, emerging categories) rank lower. Exploratory ventures where success criteria themselves are unclear (moonshots, category creation) rank lowest.

**Evaluation Criteria**:
- Do established playbooks exist for building this type of business?
- Are the steps to success well-known and documented?
- How many critical unknowns must be resolved?
- Are success criteria clear, or is the endpoint itself uncertain?

**Output**: Comparative ranking where clearer paths receive higher feasibility scores.

---

### Task 12: Risk Interdependence Ranking

**Purpose**: Rank startup ideas by how entangled their risks are.

**Description**: Compare all startup ideas to assess whether risks can be addressed independently or are deeply correlated. Ideas where challenges can be tackled separately (iterate on product, then sales, then marketing) rank highest. Those where risks are entangled (technical success requires regulatory approval which requires funding which requires technical progress) create fragile execution paths and rank lower.

**Evaluation Criteria**:
- Can challenges be addressed independently and sequentially?
- Do failures in one area cascade to others?
- Are there circular dependencies between key risks?
- How many things must go right simultaneously vs. sequentially?

**Output**: Comparative ranking where more independent risks receive higher feasibility scores.

---

### Task 13: Unknown Risk Exposure Ranking

**Purpose**: Rank startup ideas by their exposure to unknown unknowns.

**Description**: Compare all startup ideas to assess the ratio of known to unknown risks. Ideas in well-understood domains with known challenges rank highest. Those venturing into novel territory with many unknown unknowns rank lowest. The most dangerous risks are those we haven't identified—deep tech, regulatory gray areas, and unprecedented business models are dominated by unknown unknowns.

**Evaluation Criteria**:
- Is this a well-understood domain with documented challenges?
- How novel is the approach—are there precedents to learn from?
- What proportion of risks can be identified versus lurking unknown?
- Does this venture into territory where unknown unknowns dominate?

**Output**: Comparative ranking where more predictable risk profiles receive higher feasibility scores.

---

### Task 14: Failure Mode Severity Ranking

**Purpose**: Rank startup ideas by what happens when things go wrong.

**Description**: Compare all startup ideas to assess failure mode severity. Ideas with graceful degradation (pivot options exist, partial failures don't doom the company) rank highest. Those with catastrophic failure modes (clinical trial failures, regulatory actions, safety incidents that end the company entirely) rank lowest. Recoverability from setbacks is a key execution feasibility factor.

**Evaluation Criteria**:
- Can the company pivot if the initial approach fails?
- Are there partial failure modes, or is it all-or-nothing?
- What happens if a key technical, regulatory, or market bet fails?
- Is there recoverability from mistakes, or are some errors terminal?

**Output**: Comparative ranking where more recoverable failure modes receive higher feasibility scores.

---

## Aggregation Approach

The 14 tasks above produce comparative rankings across the four pillars:

- **Pillar I (Technical Feasibility)**: Tasks 1-4
- **Pillar II (Resource Requirements)**: Tasks 5-7
- **Pillar III (Regulatory Complexity)**: Tasks 8-10
- **Pillar IV (Execution Risk Profile)**: Tasks 11-14

Each pillar receives approximately equal weight (~25%) in the final aggregation. Within each pillar, component tasks are weighted equally. The final output is a probability distribution summing to ~1, where each score represents the relative execution feasibility of that startup idea compared to the alternatives presented.
