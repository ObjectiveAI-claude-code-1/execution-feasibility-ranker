# Execution Feasibility Ranker: Task Definitions

This document defines the tasks that the Execution Feasibility Ranker function must perform to evaluate and comparatively rank startup ideas by execution feasibility. Each task evaluates a specific dimension of feasibility, and the outputs are combined to produce a relative ranking across all submitted ideas.

---

## Task 1: Technical Feasibility Assessment

**Purpose:** Evaluate whether the idea can be built with currently available technology, or whether it requires scientific breakthroughs or engineering miracles.

**Description:** For each startup idea in the input array, assess the technical feasibility by determining where it falls on the spectrum from "recombines existing proven technologies" to "requires scientific breakthroughs not yet achieved." The task must identify the core technical requirements, evaluate the technology readiness level (TRL) of critical components, and determine whether existence proofs exist (similar things that have been built). Software ideas generally score higher than hardware; incremental improvements score higher than revolutionary inventions. The assessment must distinguish between "hard but possible" and "requires a miracle."

**Evaluation Criteria:**
- Does this require new science, or just new engineering?
- Are the core technologies in production use elsewhere?
- What is the technology readiness level of critical components?
- How many simultaneous technical challenges must be solved?
- Are there existence proofs—similar systems that have been built?
- Is this software (high feasibility), hardware (moderate), or deep science (low)?

**Output:** A raw feasibility signal per item indicating technical buildability.

---

## Task 2: Resource Requirements Assessment

**Purpose:** Evaluate whether the resources required (capital, talent, time, materials) can realistically be assembled by a startup team.

**Description:** For each startup idea, assess the resource intensity by determining where it falls on the spectrum from "bootstrappable with laptop and sweat equity" to "requires institutional capital and rare expertise." The task must estimate the minimum viable capital requirement, determine whether initial versions can be built with founder labor, assess talent availability in the market, and evaluate time-to-revenue against survival runway. Ideas requiring proprietary inputs (rare materials, licensed IP) or rare expertise (nuclear engineers, biotech executives) score lower for their assembly difficulty.

**Evaluation Criteria:**
- What is the minimum viable capital requirement?
- Can initial versions be built with founder labor alone?
- Are required skills readily available in the talent market?
- Does the idea require proprietary inputs (rare materials, licensed IP)?
- What is the time-to-revenue, and can a typical team survive until then?
- Does execution require world-class talent or can competent generalists succeed?

**Output:** A raw feasibility signal per item indicating resource assemblability.

---

## Task 3: Regulatory Complexity Assessment

**Purpose:** Evaluate the legal and regulatory barriers that must be navigated to bring the idea to market.

**Description:** For each startup idea, assess regulatory complexity by determining where it falls on the spectrum from "permissive environment with minimal constraints" to "heavily regulated with lengthy approvals or legal ambiguity." The task must identify what permits, licenses, or certifications are required, determine whether clear regulatory pathways exist, estimate typical approval timelines, and flag ideas operating in legal gray zones. Software and most digital services score highest; healthcare, pharma, aviation, and nuclear score lowest; ideas requiring legal reform score near zero.

**Evaluation Criteria:**
- What permits, licenses, or certifications are required?
- Are there clear regulatory pathways, or is legal status ambiguous?
- What is the typical approval timeline in this domain?
- What are the penalties for non-compliance?
- Does the idea require lobbying or legal reform to become viable?
- Does regulatory complexity vary significantly by geography?

**Output:** A raw feasibility signal per item indicating regulatory navigability.

---

## Task 4: Execution Risk Profile Assessment

**Purpose:** Evaluate the complexity of the path from concept to customer—how straightforward or treacherous is the go-to-market journey?

**Description:** For each startup idea, assess execution risk by determining where it falls on the spectrum from "clear customer, established channel, straightforward operations" to "requires ecosystem creation, behavior change, or network effects that may never materialize." The task must identify how clear the target customer is, whether established sales/distribution channels exist, whether success requires changing user behavior, and whether chicken-and-egg dynamics must be overcome. Consulting practices and SaaS tools for known problems score highest; social networks, marketplaces, and platform businesses requiring simultaneous supply and demand score lowest.

**Evaluation Criteria:**
- How clear and identifiable is the target customer?
- Is there an established sales or distribution channel?
- Does success require changing user behavior or habits?
- Are there chicken-and-egg dynamics to overcome?
- How long is the typical sales cycle in this domain?
- Does value depend on network effects or ecosystem development?

**Output:** A raw feasibility signal per item indicating path-to-market clarity.

---

## Task 5: Limiting Factor Identification

**Purpose:** Identify which dimension is the limiting factor for each idea—the single dimension most likely to block execution.

**Description:** For each startup idea, determine which of the four pillars (technical, resource, regulatory, execution) represents the binding constraint. An idea that scores well on three dimensions but fails on one is not feasible. A deep-tech venture's feasibility is dominated by technical factors; a restaurant's feasibility is dominated by execution and regulatory factors; a biotech startup is dominated by regulatory complexity and resource requirements. This task adjusts the weighting of the other assessments based on the nature of each idea.

**Evaluation Criteria:**
- For technology ventures: Technical feasibility is the binding constraint
- For service businesses: Execution risk is the binding constraint
- For regulated industries: Regulatory complexity is the binding constraint
- For capital-intensive ventures: Resource requirements are the binding constraint
- Which single dimension, if it fails, would kill the entire venture?

**Output:** An identification of the limiting factor and appropriate weighting adjustment per item.

---

## Task 6: Holistic Feasibility Synthesis

**Purpose:** Synthesize all dimension assessments into a single holistic feasibility judgment for each idea.

**Description:** For each startup idea, combine the technical, resource, regulatory, and execution risk assessments—weighted by the limiting factor identification—into a unified feasibility score. This task must also apply the philosophical constraints: assume a 5-10 year startup-relevant timeframe, assume "reasonable startup resources" (small team, modest seed capital), assume a competent but not exceptional founding team. The synthesis must be unsentimental—feasibility is not desirability, not profitability, not certainty. A trivially feasible lemonade stand should score higher than a brilliant but impossible fusion reactor.

**Evaluation Criteria:**
- How do all four dimensions combine for this specific idea?
- Is the idea feasible within a 5-10 year timeframe?
- Is it feasible for a typical startup team with modest resources?
- Does it require world-class talent or exceptional circumstances?
- Setting aside whether the idea is good or profitable, CAN it be executed?

**Output:** A holistic feasibility score per item ready for comparative ranking.

---

## Task 7: Comparative Ranking Distribution

**Purpose:** Distribute probability mass across all ideas to produce a relative ranking that sums to approximately 1.

**Description:** Take the holistic feasibility scores from all items and normalize them into a probability distribution. This task enforces the vector output format: scores must sum to approximately 1, forcing discriminating judgments rather than grade inflation. The output represents "If I had to bet on which of these could actually be built and brought to market, how would I allocate my confidence?" Ideas with higher feasibility receive proportionally more of the probability mass; ideas with lower feasibility receive less. The distribution should reflect genuine comparative differences—an idea twice as feasible as another should receive roughly twice the probability mass.

**Evaluation Criteria:**
- All scores must sum to approximately 1
- Scores must reflect genuine comparative feasibility differences
- The distribution must force discriminating judgments
- Higher feasibility = higher share of probability mass
- Output vector length must equal input array length

**Output:** A vector of scores (one per item) summing to ~1, representing relative execution feasibility.

---

## Task Composition Notes

The tasks are designed to operate in a logical sequence:

1. **Tasks 1-4** (Dimension Assessments) can run in parallel—each evaluates one pillar of feasibility independently for all items.

2. **Task 5** (Limiting Factor) requires awareness of all dimension scores to identify the binding constraint for each idea.

3. **Task 6** (Holistic Synthesis) combines all dimension assessments with limiting factor weighting to produce per-item scores.

4. **Task 7** (Comparative Ranking) normalizes all per-item scores into the final probability distribution.

The function must handle multimodal inputs (text, image, audio, video, composite) uniformly. Presentation quality must not corrupt feasibility assessment—a poorly produced pitch for a feasible idea should outscore a slick pitch for an impossible concept.
