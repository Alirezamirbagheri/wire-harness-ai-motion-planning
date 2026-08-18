# Architecture Overview — Final Version 3

This document summarizes the architecture represented by the final **Version 3** research implementation. The public repository intentionally describes the system at portfolio level rather than exposing the complete private research codebase.

## Perception

The camera image is converted into a three-class semantic map: **background**, **wire harness**, and **mover**. Wire and mover masks are processed separately so that perception output can be reduced to compact geometry suitable for planning and runtime control.

## Geometry and tracking

Mover positions, dimensions and orientation are extracted from the segmented mover regions. The wire mask is refined to obtain centerline/branch geometry and attachment relationships. Persistent mover identity is maintained across visual updates so planning and PLC commands remain associated with the correct physical movers.

## Hierarchical motion planning

The system separates motion planning into two levels:

- **Global planning** generates coordinated formation-level motion toward the target configuration.
- **Local planning** evaluates short-horizon alternatives when wire, mover or workspace risks require a local correction.

This split keeps the global task objective explicit while allowing collision-aware corrections close to execution time.

## PLC integration

The Python runtime exchanges commands, acknowledgements, mover states and local overrides with the PLC. Execution is supervised through an explicit state-machine and handshake architecture so AI/perception updates and motion commands are synchronized with the industrial controller.

## Public/private boundary

The public showcase contains architecture, verified benchmark results and demo media. Machine-specific paths, network/PLC configuration, raw datasets, model checkpoints, experiment logs and the complete Version 3 implementation remain outside the public portfolio repository.
