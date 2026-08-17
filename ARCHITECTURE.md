# Architecture Overview

## Perception
The camera image is transformed into a three-class semantic map. The wire and mover masks are then processed separately to obtain compact geometry suitable for planning.

## Geometry and tracking
Mover positions, dimensions and orientation are extracted from connected components and contours. Wire masks are refined and skeletonized to derive centerlines, branches and attachment relationships. Persistent mover identity is maintained across visual updates.

## Hierarchical motion planning
A global planner generates coordinated formation-level motion toward the target configuration. A local planner evaluates short-horizon alternatives when wire, mover or workspace risks are detected.

## PLC integration
The Python runtime exchanges commands, acknowledgements, mover states and local overrides with the PLC. Runtime execution is supervised through an explicit state-machine and handshake architecture.
