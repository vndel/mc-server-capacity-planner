# Minecraft Server Capacity Planner

A repeatable way to capture workload assumptions and plan capacity for Paper backends and Velocity proxies. This is a planning aid, not a player-count guarantee: performance depends on plugins, world behavior, CPU single-thread performance, storage, and traffic patterns.

## Workflow
1. Define representative peak and off-peak workloads, including view/simulation distances and plugin features.
2. Measure a staging server under controlled load; record MSPT percentiles, heap/GC, CPU, disk latency, network, and login throughput.
3. Estimate headroom from the measured bottleneck, not nominal CPU or memory totals.
4. Change one resource or configuration dimension at a time and repeat the test.
5. Set alert and scaling thresholds before production rollout.

Avoid extrapolating linearly beyond tested ranges. Keep player data out of load-test artifacts.

## Files
- `workload.yml`: example workload assumptions to replace with measured values.
- `templates/measurement.md`: test record template.