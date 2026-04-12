# Claude Instructions: OpenClaw Env Builder

Read `AGENTS.md` first before any action. Follow the System Architect role and Harness Engineering methodology.

## 🤖 Core Mandates
1. **Local-First**: Prioritize local tools and LLMs when possible.
2. **Sandbox Isolation**: High-risk tasks (Zone 2) MUST run in `jarvis-box`.
   - **Routing**: Use `openshell sandbox exec -n jarvis-box -- [command]`.
3. **Harness Adherence**: Follow `AGENTS.md` and `docs/methodology/HarnessEngineering.md`.
4. **Guided Autonomy**: Follow the protocol defined in `GEMINI.md` to prevent loops and ensure state-driven progression.

## 🛠️ Environment Info
- **OS**: macOS (Darwin) - Mac Mini Server based
- **Sandbox Manager**: NemoClaw / OpenShell
- **Default Sandbox**: `jarvis-box`
- **Policies**: See `docs/policy/SANDBOX_POLICY.md`
