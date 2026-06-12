# Objectives

## Goals
- Enforce deterministic toolchain versions across all workstations, eliminating environment drift as a source of bugs and friction.
- Isolate development runtimes from the host machine so that the host OS and its configuration are irrelevant to the development workflow.
- Support both Neovim and VS Code workflows.

## Non-goals
- **Application-specific business logic.** **Abovo** defines the environment, not what runs inside it. No assumptions are made about the nature of the project being developed.

---

## Planned features
- **Automated provisioning installer.** A binary that handles host setup end-to-end, reducing the prerequisite steps to a single command.
- **User preference injection.** A layer for injecting developer-specific configuration (dotfiles, editor settings, shell preferences) without modifying the shared container definition.

---

## Architectural decisions
### Base image: Arch Linux
Arch was chosen over purpose-built development images (e.g. Ubuntu-based devcontainer images) because it ships no opinionated defaults, installs no toolchain assumptions, and has minimal baseline resource usage. The environment is built explicitly from a known-minimal state rather than trimmed down from a bloated one. The Arch User Repository also provides access to a broad range of tools without requiring custom package sources.

### Container interface: Dev Containers
Dev Containers were adopted as the initial integration layer because they offer the lowest barrier to entry for VS Code-centric developers: clone, reopen in container, done. The spec is open and not exclusive to VS Code, which keeps options open for future editor integrations without requiring a new container strategy.

### License: GNU GPLv3
The GPLv3 was chosen deliberately to ensure that improvements to **Abovo** remain open. If the tooling proves useful enough that an enterprise or commercial product wants to incorporate it, they must contribute back under the same terms. This protects the project from becoming upstream labor for closed toolchains.

---

## Phases
### Phase 1 — Bootstrap
- Establish a deterministic, minimal container definition.
- Validate Dev Container integration end-to-end.
- Keep complexity low: no profiles, no installer, no preference layer.

**Dependencies:** Git, Docker, VSCode, Dev Container Extension.

### Phase 2 — VsCode + Neovim Integration
- Add Multi-Stage build behaviour.
- Add Neovim support at parity with VS Code.

**Dependencies:** Git, Docker, VSCode (*optional*), Dev Container Extension (*optional*).

### Phase 3 — Non-root user setup (*current*) 
- Remove root-based workflow.
- Ensure files created in the environment are owned by the correct user.

**Dependencies:** Git, Docker, VSCode (*optional*), Dev Container Extension (*optional*).

### Phase 4 — Preference injection layer setup
- Add build arguments for container customization support.
- Define architectural protocol for container customization setup and injection.

**Dependencies:** Git, Docker, VSCode (*optional*), Dev Container Extension (*optional*).
