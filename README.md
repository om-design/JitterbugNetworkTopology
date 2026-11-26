# Jitterbug Network Topology

**A strategy for sparse network resiliency**

Originator: omdesign  
Foundational statement: 26 November 2026

## Concept

Jitterbug is an adaptive topology designed for environments where connectivity is sparse, intermittent, and continually changing. Rather than restricting adaptation to routes through an existing network, Jitterbug enables the topology itself to respond to difficulties encountered during communication. Participants can temporarily expand connectivity and then contract, retaining useful connection experience. No supervising node or continuously available coordination service is required by the proposed architecture. The strategy is independent of any particular application or communications technology.

## Origin and purpose

Jitterbug originated during the development of [Has-Needs](https://github.com/has-needs/docs), where an individual's ability to communicate during a disaster is fundamental. Disasters, however, are only one instance of a broader design problem.

Throughout the world, geography, economics, energy availability, and infrastructure development make intermittent connectivity an ordinary condition of life. Approaches that take ubiquitous connectivity as their starting point risk treating these conditions as exceptions, with the implicit assumption that the objective is to reproduce the infrastructure of wealthier regions.

Jitterbug takes sparsity as a legitimate starting condition. Sparsity may be spatial, temporal, or related to the resources available to sustain communication. The aim is to make economical use of available connectivity while enabling participants to respond autonomously when more is needed.

## Research direction

The immediate objective is to determine whether autonomous structural adaptation improves communication under sparse conditions, at what resource cost, and within what limits. Jitterbug will be examined independently of Has-Needs using abstract participants and communication relationships, without prescribing a particular message format, hardware platform, or application.

Comparative experiments will investigate delivery, delay, resource expenditure, scalability, and behavior under changing connectivity. Independent laboratory evaluation is sought, including prospective engagement with the University of New Hampshire.

Potential applications include humanitarian logistics, disaster response, rural and remote communications, and resource-constrained distributed devices. Resiliency and efficiency are design objectives, not established experimental findings. Technical novelty and comparative performance remain subjects for investigation.

## Publication and rights

This dated statement introduces the research direction for scholarly discussion. The [independent specification](SPECIFICATION.md) establishes the two-state reference architecture, and the [proposed research plan](RESEARCH_PLAN.md) outlines its scientific evaluation. Neither constitutes a validated implementation or a report of experimental results. The [Positive Forward](https://github.com/om-design/PositiveForward) research initiative addresses reliable understanding across diverse intelligence systems and is distinct from Jitterbug itself.

Copyright © 2026 omdesign. All rights reserved.

See [LICENSE](LICENSE) for the reservation of rights and attribution policy.
