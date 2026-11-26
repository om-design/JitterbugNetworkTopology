# Jitterbug Network Topology

**A strategy for sparse network resiliency**

Originator: omdesign  
26 November 2026 | Independent specification 0.3  
Copyright © 2026 omdesign. All rights reserved.

This document describes the proposed topology, not a validated protocol, performance claim, or implementation standard.

## 1. Starting conditions

Consider a collection of independently operating participants. Each participant can communicate with some of the others. Which interactions are possible changes with proximity, availability, interference, energy and other local conditions. A participant may know its own surroundings without knowing the structure or condition of the entire collection.

Maintaining communication relationships consumes resources. A participant need not maintain every possible relationship continuously, but must be able to increase its opportunities for communication when circumstances require it.

Jitterbug begins with these conditions. Sparse and intermittent connectivity is an ordinary operating environment. Continuous infrastructure, a global network map and a supervising participant are not prerequisites.

## 2. Elementary relationships

- **Node:** an independently operating participant capable of local communication and local state changes.
- **Potential contact:** another node with which communication may be physically possible under current conditions.
- **Connection:** a locally enabled communication relationship. Its realization depends on the transport and the availability of both participants.
- **Obstruction:** an impediment encountered during an attempted communication. Retention of a previously forwarded message is not, by itself, a new obstruction.
- **Message:** an abstract unit of information carried in ordinary communication. Its application meaning and wire representation are outside this specification.

A potential contact, an enabled connection and a successful transfer are distinct. A node cannot establish communication merely by deciding that a connection should exist.

## 3. Topology behavior

The reference architecture has exactly two local connectivity states: resting and expanded. The expansion instruction's countdown does not introduce additional connectivity states or successive tiers of expansion.

### Resting configuration

A node maintains an economical configuration of listening or communication relationships. This is an operating state in which ordinary communication can occur, not necessarily a sleeping state. A resting node may change its relationships as local opportunities change. It is not restricted to a single predetermined next hop.

### Expansion

When a node encounters an obstruction during an attempted communication, it opens additional local connection possibilities and attempts onward communication. It does not require a reply from the obstructing node or permission from a supervisor.

Expansion is a change in the local connectivity available to the node. Changing only a scan rate, forwarding eligibility, or copy budget is insufficient to represent this structural change. The realized additional connections remain constrained by actual contact opportunities and resources.

### Propagation

The initiating node associates an expansion instruction, `open_flag`, with the communication it sends through its expanded topology. In the reference sequence the outgoing value is 3. A node receiving a positive value opens additional local connection possibilities and decrements the instruction for onward successful transmission. The reference sequence is 3 → 2 → 1 → 0.

Zero does not request additional expansion from that instruction. It is not a message lifetime or a prohibition on ordinary forwarding. A node that was unavailable does not have to participate in the initiating event. Once available, it can participate through subsequent communication, including receipt of a positive expansion instruction.

The instruction accompanies the ordinary message exchange; no particular header encoding is prescribed. Separate activation-control traffic would be a different experimental profile, not an equivalent assumption.

### Contraction

Each expanded node has its own return timer. Upon expiry it contracts toward its resting configuration. A new obstruction or receipt of a positive expansion instruction can renew expanded operation; the exact renewal rules remain to be specified.

The propagation count and the return timer govern different things. The count limits successive propagation of an instruction. The timer governs the duration of a node's expanded connectivity. Receiving 1 does not mean that a node immediately contracts when its onward count reaches 0. Nor does receiving 3 require a greater local expansion than receiving 1.

### Retained experience

Contraction reduces maintained connectivity without requiring the node to forget useful connection experience. Ordinary communications, including routine background activity when available, provide opportunities to observe useful connections. Experience may inform subsequent selection of relationships. Its precise representation, retention and influence are open engineering decisions.

No application-specific matching, identity, receipt mechanism or semantic routing is required to study this behavior.

## 4. Observable model

A proposed abstract representation separates the external contact environment from the topology that participating nodes can change.

- `A_i(t)`: potential contacts of node i at time t, determined by the experimental environment, not necessarily known to the node.
- `L_i(t)`: locally enabled relationships of node i, according to the implementation's declared connection semantics.
- `E(t)`: actual usable communication relationships, derived from enabled relationships, contact feasibility and the transport's endpoint rules.
- `S_i(t)`: resting or expanded configuration.
- `H_i(t)`: retained local connection experience.
- `T_i`: return interval; expiry and renewal are local.
- `k`: expansion count carried with a message.

An implementation must make it possible to observe a change in `L_i` independently of changes in message-copy counts or scan frequency. `E(t)` may remain unchanged when no additional contact is available. The experiment may know the full contact schedule, but nodes must not use that global knowledge or future events to make their decisions.

This notation is a proposed measurement model, not the inventor's original mathematical formulation. It leaves directed versus reciprocal relationships and establishment semantics to the declared transport profile.

## 5. Reference geometry and unresolved parameters

The author confirms a two-state reference design: resting and expanded. The number of maintained connections in each state is an experimental parameter, not a universal architectural constant. A recalled candidate profile of four resting connections and up to six additional connections during expansion may be investigated, but has not been selected as a canonical numeric profile.

A graduated or three-tier expansion may be studied as a separately identified experimental alternative. It is not part of the reference topology, and no comparative benefit or disadvantage has yet been established.

The reference countdown is 3 → 2 → 1 → 0. These values describe successive propagation of an instruction, not connection counts or tiers.

The numerical return interval, exact obstruction detection, selection of additional relationships, reciprocal connection requirements, duplicate handling, timer renewal, concurrent expansion, explicit zero transmission, retention and retry policies remain open. An experimental implementation may select values, but must label its selections rather than attribute them to the architecture.

## 6. Limits and research objectives

Jitterbug cannot create a physical contact where none is possible. If there is no temporally feasible path, no topology policy can deliver across the separation. The count limits the depth of one uninterrupted instruction, not its aggregate branching or the number of successive or overlapping expansions. Resource consumption under persistent obstruction is a research question.

The scientific objective is to establish under what conditions localized structural adaptation improves communication while limiting sustained resource expenditure. Test delivery, delay, extent and duration of expansion, connection utilization, recovery, resource cost and scalability. Test the contribution of retained experience separately. Neither low energy consumption, superior delivery nor bounded aggregate activity is assumed.

## 7. Scope and status

Jitterbug originated in Has-Needs but is independently applicable to sparse communications environments. Has-Needs integration, packet formats, radio choice, security and application semantics are outside this specification. No laboratory participation, technical novelty or empirical advantage is claimed as established.

Before implementation, agree on an explicit reference profile for the open parameters in section 5. Evaluate independent comprehension before comparing experimental results. The accompanying [research plan](RESEARCH_PLAN.md) and the independent [Positive Forward](https://github.com/om-design/PositiveForward) research program do not define the architecture.

See [LICENSE](LICENSE) for the reservation of rights and attribution policy.
