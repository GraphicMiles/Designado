# Agent Design & Instruction Skills

Upload this folder to your GitHub repository and configure your agent to load the relevant skill files for every task.

## Files

- `SKILL.md` — Skill index and mandatory loading protocol.
- `product-native-ui.md` — Prevents presentation-style, tutorial-like application interfaces.
- `ui-composition.md` — Establishes professional layout, sizing, alignment, spacing and hierarchy.
- `color-intelligence.md` — Establishes disciplined color selection, semantic colors and surface treatment.
- `skill-fidelity.md` — Requires complete reading, understanding, execution and verification of applicable skills.

## Agent integration

Add the following instruction to the agent's permanent system/developer instructions:

> Before designing or modifying any user interface, load and follow `SKILL.md` and every applicable skill it references. Read each applicable file completely, including all sections. Treat mandatory requirements and prohibitions as binding. Do not substitute your defaults or silently deviate. Verify the finished work against the original files before reporting completion. If the repository or runtime cannot access a required file, stop and report the limitation rather than pretending it was read.

The agent must have repository/file access and a mechanism to load these files. Merely placing files in GitHub does not make an agent read them automatically; configure the agent's skill discovery or explicitly include the loading instruction above.
