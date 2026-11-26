# Jitterbug: proposed independent evaluation

26 November 2026 | Proposed research plan | Copyright © 2026 omdesign. All rights reserved.

This is a proposed laboratory method, not part of the topology specification. No laboratory access or participation is assumed.

## 1. Research questions

Does obstruction-responsive expansion of local connectivity increase communication opportunities under sparse conditions? Does independent contraction reduce the sustained resource burden? Does retained experience improve subsequent communication? How does the extent of the response change as the size of the network grows while the local disturbance remains fixed?

These are separate hypotheses. Report negative and inconclusive results on equal terms with positive results.

## 2. Establish a reference profile

Use the two-state architecture in [the specification](SPECIFICATION.md). Agree on numeric connection limits and operational semantics with omdesign. Define contact availability, what constitutes an enabled relationship and successful transfer, exact trigger, countdown transmission and renewal rules, return timer, retention and ordinary traffic. Declare all assumptions. Freeze a version of the specification and the chosen experimental profile before collecting comparative data.

Use deterministic traces before stochastic studies. Independently observe potential contacts, enabled relationships, actual usable relationships, attempted and successful communication, count values, local timer events and retained experience. Check that the enabled connectivity actually expands and contracts. A model changing scan frequency alone is not a structural conformance test.

## 3. Comparisons

Use identical contact schedules, traffic, observation windows and resource constraints across the compared policies. Select a shared forwarding and retention policy where possible so that topology effects are identifiable. Compare the reference adaptive policy with an economical non-expanding configuration, a continuously expanded configuration, and a suitable established adaptive or disruption-tolerant comparator. Add component ablations of propagation, contraction and retained experience. Document comparator limitations; do not construct deliberately weak alternatives to establish an advantage.

Vary spatial sparsity, temporal sparsity and resource budgets separately; also investigate their interactions. Include a temporarily unavailable participant, persistent local obstruction, correlated loss, restoration, a permanently disconnected component, routine traffic at different intensities, and a repeated disturbance after contraction. Increase network size with the local neighborhood and disturbance held comparable. Use independent seeds and paired runs; avoid interpreting messages in the same run as independent replicates.

Graduated expansion (including a three-tier variant) may be investigated as a separately labeled alternative after the two-state reference profile has been evaluated. Compare any additional benefit against complexity, resource consumption and failure behavior. No benefit is presumed.

## 4. Measures

Measure delivery by deadline, delay with failures reported, link establishment, enabled and realized degree over time, spatial or graph distance of affected nodes, duration of expansion, time to recovery after restoration, transmitted bytes including control overhead, duplicates, retries and contention. Compare full-window resource expenditure, including idle periods and background traffic. Instrument actual devices for electrical energy measurements; expanded node-time is a proxy, not joules.

For scalability, report local response cost, response extent, duration and aggregate cost as functions of network size and workload. The countdown alone does not establish a bound on total activity. Preserve all raw traces, code versions, assumptions, seeds and analysis. State uncertainty and external-validity limits.

## 5. Separate interpretation research

[Positive Forward](https://github.com/om-design/PositiveForward) is the independent research initiative for reliable understanding. Use the separate comprehension prompt and answer key to test how independent participants interpret the same pinned Jitterbug specification before execution. Preserve first responses, source revisions, supplied context, platform, date and model identifier if known. Record corrections outside the model. A new session or model version requires fresh calibration; passing one check does not establish future reliability.

Do not provide the answer key or earlier experimental conclusions to the model in the initial condition. Separate inadequate specification, ambiguous semantics, disclosed experimental substitutions and unsupported inferences. Repeat with new cases after intervening work. An unfavorable result about a faithfully represented topology is not a comprehension failure.

The proposed test conditions compare the original or clarified specification, with and without explicit Positive Forward guidance. Independent evaluators should score behavior against the same author-approved criteria before seeing performance metrics. Do not infer properties of a model's training corpus from its output alone.
