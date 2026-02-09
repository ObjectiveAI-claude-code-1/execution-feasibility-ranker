# Execution Feasibility Ranker: Task Definitions

This document defines the individual evaluation tasks that comprise the Execution Feasibility Ranker. Each task evaluates a specific dimension of feasibility across all startup ideas simultaneously, contributing to the final comparative ranking.

The function is a **vector.function** that produces a probability distribution across input ideas. Each sub-task must evaluate all ideas in the input array and contribute scores that help determine relative feasibility.

---

## Pillar 1: Technical Feasibility

### Task 1.1: Technology Readiness Ranker

**Purpose**: Rank startup ideas by how ready the required technology is for productization.

**Description**: This task evaluates each idea based on where its core technology sits on the spectrum from proven/off-the-shelf to requiring scientific breakthroughs. Ideas using established, well-understood technology rank higher than those requiring immature, experimental, or non-existent technology.

**Evaluation Criteria**:
- Can the idea be built with off-the-shelf components and established architectures?
- Does the idea depend on technology that exists in research but hasn't been productized?
- Does the idea require scientific discoveries that haven't occurred yet?
- How far along is the technology from "works in a lab" to "works at scale in production"?

**Signal Interpretation**: Ideas describable with concrete existing technologies score higher. Vague technological claims or references to futuristic capabilities score lower.

---

### Task 1.2: Integration Complexity Ranker

**Purpose**: Rank startup ideas by the complexity of integrating required systems and components.

**Description**: This task evaluates each idea based on how many distinct systems must work together and how challenging their integration would be. Ideas requiring integration of systems that have never been combined, or that face significant interoperability challenges, rank lower.

**Evaluation Criteria**:
- How many distinct technical systems must be integrated?
- Have these systems been integrated before, or is this novel combination?
- What data synchronization and architectural coherence challenges exist?
- Are there known integration patterns, or must new ones be invented?

**Signal Interpretation**: Simple, self-contained systems score higher. Complex multi-system integrations with unknown emergent behaviors score lower.

---

### Task 1.3: Talent Availability Ranker

**Purpose**: Rank startup ideas by how accessible the required technical talent is.

**Description**: This task evaluates each idea based on whether the necessary expertise exists in sufficient supply and can realistically be recruited. Ideas requiring extremely specialized talent that is scarce or monopolized by well-funded incumbents rank lower.

**Evaluation Criteria**:
- Can generalist engineers build this, or are rare specialists required?
- How large is the talent pool for the required skills?
- Are the needed experts available or locked into competitive organizations?
- What geographic constraints exist on accessing this talent?

**Signal Interpretation**: Ideas buildable by competent generalists score higher. Ideas requiring the world's top 50 experts in a niche field score lower.

---

### Task 1.4: Infrastructure Dependency Ranker

**Purpose**: Rank startup ideas by their dependence on external infrastructure that may not exist or be accessible.

**Description**: This task evaluates each idea based on whether the necessary infrastructure (networks, platforms, APIs, physical systems) exists and is accessible. Ideas that can only work once certain infrastructure becomes ubiquitous rank lower.

**Evaluation Criteria**:
- Does the required infrastructure already exist and is widely deployed?
- Is the idea dependent on platform access that could be denied?
- Are there hardware or connectivity prerequisites not yet met?
- Is the world ready to receive this product, or must infrastructure catch up first?

**Signal Interpretation**: Ideas that work with today's infrastructure score higher. Ideas awaiting future infrastructure deployment score lower.

---

## Pillar 2: Resource Requirements

### Task 2.1: Capital Intensity Ranker

**Purpose**: Rank startup ideas by how much capital they require before generating value.

**Description**: This task evaluates each idea based on the capital required to reach meaningful milestones. Ideas that can demonstrate value with minimal resources rank higher than those requiring massive upfront investment before any validation is possible.

**Evaluation Criteria**:
- Can this be built by two developers with laptops, or does it require massive facilities?
- Is capital front-loaded (huge investment before any revenue) or gradual (grow with reinvestment)?
- Can meaningful progress be made on a tight budget?
- Is this a winner-take-all market requiring huge raises from day one?

**Signal Interpretation**: Bootstrappable ideas score higher. Capital-intensive plays requiring years of burn before revenue score lower.

---

### Task 2.2: Team Size and Specialization Ranker

**Purpose**: Rank startup ideas by the size and specialization level of the team required to execute.

**Description**: This task evaluates each idea based on how many people are needed and how specialized they must be. Ideas executable by small, generalist teams rank higher than those requiring large, highly specialized organizations.

**Evaluation Criteria**:
- What is the minimum team size to reach meaningful milestones?
- Can generalists execute, or are multiple specialists required?
- Does the founder need specific domain expertise, or can smart outsiders lead?
- How much organizational complexity is inherent in the execution?

**Signal Interpretation**: Solo founder or small team viability scores higher. Ideas requiring dozens of specialists from day one score lower.

---

### Task 2.3: Time to Market Ranker

**Purpose**: Rank startup ideas by how quickly they can reach paying customers.

**Description**: This task evaluates each idea based on the expected timeline from start to market and the certainty of that timeline. Ideas with shorter, more predictable paths to market rank higher.

**Evaluation Criteria**:
- How long until a minimum viable product can reach customers?
- Is the timeline predictable or highly variable?
- Are there long development cycles before any feedback is possible?
- Do regulatory or partnership timelines create unavoidable delays?

**Signal Interpretation**: Six-month-to-market ideas score higher. Multi-year development cycles with uncertain timelines score lower.

---

### Task 2.4: Partnership Dependency Ranker

**Purpose**: Rank startup ideas by their dependence on external partnerships, data access, or platform relationships.

**Description**: This task evaluates each idea based on how many external relationships must be established and how difficult those relationships are to secure. Ideas that can go directly to customers rank higher than those requiring permission from gatekeepers.

**Evaluation Criteria**:
- Can this go direct to customers, or are intermediary partnerships required?
- How many external approvals or integrations are needed before launch?
- Are potential partners incentivized to cooperate or to block?
- Is proprietary data access required that may be denied?

**Signal Interpretation**: Direct-to-consumer models score higher. Ideas requiring reluctant enterprise partnerships score lower.

---

## Pillar 3: Regulatory Complexity

### Task 3.1: Regulatory Burden Ranker

**Purpose**: Rank startup ideas by the weight of industry-specific regulations they must navigate.

**Description**: This task evaluates each idea based on how heavily regulated its target industry is. Ideas in lightly regulated spaces rank higher than those in industries with extensive compliance requirements.

**Evaluation Criteria**:
- Is this a lightly regulated industry (internal tools, productivity software)?
- Does this fall under heavy regulation (healthcare, finance, transportation)?
- Are there licensing, certification, or approval requirements?
- How much compliance infrastructure must be built before launch?

**Signal Interpretation**: Unregulated software plays score higher. Healthcare, financial services, or controlled substances score lower.

---

### Task 3.2: Regulatory Clarity Ranker

**Purpose**: Rank startup ideas by how clear and stable the regulatory environment is.

**Description**: This task evaluates each idea based on whether the rules are established and predictable versus emerging and uncertain. Ideas in mature regulatory environments rank higher than those in spaces where the rules are still being written.

**Evaluation Criteria**:
- Are the regulations clear and well-established?
- Is the regulatory environment actively changing or under political debate?
- Could the idea be legal today and illegal tomorrow?
- Does execution require lobbying for new regulatory frameworks?

**Signal Interpretation**: Stable, predictable regulatory environments score higher. Emerging, uncertain, or contested regulatory spaces score lower.

---

### Task 3.3: Geographic Regulatory Variation Ranker

**Purpose**: Rank startup ideas by how much regulatory complexity varies across geographies.

**Description**: This task evaluates each idea based on whether it can scale globally under relatively uniform rules or faces a patchwork of conflicting jurisdictional requirements. Ideas with simpler geographic regulatory profiles rank higher.

**Evaluation Criteria**:
- Can this operate globally under similar rules, or does each market require different approaches?
- Are there jurisdictions where this is simply prohibited?
- Can sufficient scale be achieved within favorable jurisdictions?
- How much does international expansion multiply regulatory complexity?

**Signal Interpretation**: Globally uniform regulatory treatment scores higher. Fragmented, jurisdiction-by-jurisdiction compliance requirements score lower.

---

### Task 3.4: Compliance Cost Ranker

**Purpose**: Rank startup ideas by the ongoing cost and expertise required for regulatory compliance.

**Description**: This task evaluates each idea based on how expensive and expertise-intensive ongoing compliance will be. Ideas with low compliance overhead rank higher than those requiring dedicated legal teams, audit systems, and continuous monitoring.

**Evaluation Criteria**:
- What legal expertise is required for ongoing operations?
- Are there documentation, audit, and monitoring requirements?
- How much does compliance cost relative to core product development?
- Can compliance be handled part-time or does it require dedicated staff?

**Signal Interpretation**: Minimal ongoing compliance burden scores higher. Continuous, expensive, expertise-intensive compliance scores lower.

---

## Pillar 4: Execution Risk Profile

### Task 4.1: Go-to-Market Clarity Ranker

**Purpose**: Rank startup ideas by how clear and direct the path to customers is.

**Description**: This task evaluates each idea based on how obvious and navigable the distribution and sales path is. Ideas with self-evident go-to-market strategies rank higher than those requiring complex, unproven customer acquisition approaches.

**Evaluation Criteria**:
- Is the path to customers obvious (app store, direct sales, clear channel)?
- How complex is the sales cycle (self-serve vs. enterprise vs. government)?
- Are there established playbooks for reaching this customer, or must new approaches be invented?
- How much behavior change is required from customers?

**Signal Interpretation**: Clear, proven distribution channels score higher. Novel, complex, or unproven go-to-market strategies score lower.

---

### Task 4.2: Market Validation Certainty Ranker

**Purpose**: Rank startup ideas by how validated the market demand is.

**Description**: This task evaluates each idea based on the gap between hypothesis and proven demand. Ideas addressing well-documented pain points with established willingness to pay rank higher than those requiring category creation.

**Evaluation Criteria**:
- Is this addressing a well-documented, widely-felt pain point?
- Do customers already pay for solutions in this space?
- Is willingness to pay established, or must it be created?
- Is this creating a new category where demand is theoretical?

**Signal Interpretation**: Proven demand with existing budget allocation scores higher. Category creation requiring customer education scores lower.

---

### Task 4.3: Competitive Positioning Ranker

**Purpose**: Rank startup ideas by the favorability of the competitive landscape.

**Description**: This task evaluates each idea based on how defensible a position can be established against existing and future competitors. Ideas entering underserved niches rank higher than those attacking entrenched incumbents with high switching costs.

**Evaluation Criteria**:
- How entrenched are existing competitors?
- How high are switching costs for customers?
- Can meaningful moats be built and defended?
- Is this an underserved niche or a crowded battlefield?

**Signal Interpretation**: Underserved markets with low incumbent entrenchment score higher. Well-defended markets with high switching costs score lower.

---

### Task 4.4: Operational Complexity Ranker

**Purpose**: Rank startup ideas by the operational complexity required to deliver value.

**Description**: This task evaluates each idea based on how operationally complex delivery is beyond the core product. Ideas that are primarily software with simple delivery rank higher than those requiring physical logistics, real-time coordination, or complex supply chains.

**Evaluation Criteria**:
- Is this primarily software/digital, or are physical operations required?
- Are there logistics, inventory, or supply chain requirements?
- Is real-time coordination across parties required?
- How many operational failure modes exist beyond the core product?

**Signal Interpretation**: Pure software with digital delivery scores higher. Physical operations with complex logistics score lower.

---

### Task 4.5: Iteration Speed Ranker

**Purpose**: Rank startup ideas by how quickly founders can learn and adapt based on market feedback.

**Description**: This task evaluates each idea based on the speed and reversibility of learning cycles. Ideas allowing rapid experimentation, measurement, and iteration rank higher than those requiring long commitment cycles before feedback.

**Evaluation Criteria**:
- How quickly can changes be shipped and measured?
- Are decisions reversible, or do early choices lock in?
- Can meaningful experiments be run with limited resources?
- How fast is the feedback loop from customer to product iteration?

**Signal Interpretation**: Rapid, reversible experimentation scores higher. Long, locked-in commitment cycles score lower.

---

### Task 4.6: Network Effect Bootstrapping Ranker

**Purpose**: Rank startup ideas by how achievable critical mass is if network effects are required.

**Description**: This task evaluates each idea based on whether network effects are required and, if so, how achievable bootstrapping strategies are. Ideas not dependent on network effects, or with clear bootstrapping paths, rank higher.

**Evaluation Criteria**:
- Does this idea require network effects to deliver value?
- Are there proven strategies for bootstrapping this type of network?
- Can value be delivered with small networks, or is critical mass required?
- How severe is the chicken-and-egg problem?

**Signal Interpretation**: Ideas not requiring network effects, or with clear bootstrapping paths, score higher. Severe cold-start problems with no clear solution score lower.

---

## Synthesis and Ranking

### Task 5.1: Holistic Feasibility Synthesizer

**Purpose**: Synthesize all pillar evaluations into a final comparative ranking.

**Description**: This task takes the outputs from all previous evaluation tasks and produces the final probability distribution across startup ideas. It must weight the various dimensions appropriately given the specific ideas being compared, recognizing that the relative importance of technical feasibility, resources, regulation, and execution risk varies by context.

**Evaluation Criteria**:
- Consider all four pillars holistically for each idea
- Weight dimensions based on which are most differentiating for this specific comparison
- Produce a probability distribution reflecting relative feasibility
- Ensure the ranking reflects practical execution paths, not idea quality or market size

**Output**: A vector of probabilities summing to approximately 1, with higher values indicating higher relative execution feasibility.

---

## Task Summary

| Pillar | Task | Description |
|--------|------|-------------|
| Technical Feasibility | 1.1 Technology Readiness | Maturity of required technology |
| Technical Feasibility | 1.2 Integration Complexity | Difficulty of system integration |
| Technical Feasibility | 1.3 Talent Availability | Accessibility of required expertise |
| Technical Feasibility | 1.4 Infrastructure Dependency | Reliance on external infrastructure |
| Resource Requirements | 2.1 Capital Intensity | Upfront capital requirements |
| Resource Requirements | 2.2 Team Size/Specialization | Human resource requirements |
| Resource Requirements | 2.3 Time to Market | Speed to customer delivery |
| Resource Requirements | 2.4 Partnership Dependency | External relationship requirements |
| Regulatory Complexity | 3.1 Regulatory Burden | Industry regulation weight |
| Regulatory Complexity | 3.2 Regulatory Clarity | Stability of regulatory environment |
| Regulatory Complexity | 3.3 Geographic Variation | Jurisdictional complexity |
| Regulatory Complexity | 3.4 Compliance Cost | Ongoing compliance overhead |
| Execution Risk | 4.1 Go-to-Market Clarity | Distribution path clarity |
| Execution Risk | 4.2 Market Validation | Demand certainty |
| Execution Risk | 4.3 Competitive Positioning | Competitive landscape favorability |
| Execution Risk | 4.4 Operational Complexity | Delivery complexity beyond product |
| Execution Risk | 4.5 Iteration Speed | Learning cycle velocity |
| Execution Risk | 4.6 Network Effect Bootstrapping | Network effect achievability |
| Synthesis | 5.1 Holistic Synthesizer | Final comparative ranking |

---

## Implementation Notes

1. **Comparative Nature**: Each task must evaluate ALL ideas in the input array simultaneously and produce comparative rankings, not absolute scores.

2. **Multimodal Handling**: Tasks must interpret startup ideas across all input formats (text, image, audio, video, composites) and extract relevant signals for their specific dimension.

3. **Score Normalization**: Individual task outputs contribute to the final probability distribution, which must sum to approximately 1.

4. **Context Sensitivity**: The weighting of different dimensions should reflect what is most differentiating for the specific set of ideas being compared.

5. **Feasibility Focus**: Tasks evaluate execution feasibility only—not idea quality, market size, founder capability, or success probability.
