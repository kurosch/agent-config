# agent-config
My vibe configuration for Mistral Vibe with Superpowers integration.

## Setup

This repository contains my Mistral Vibe agent configurations with Superpowers integrated as a Git submodule.

### Structure

- `mistral-vibe/` - Mistral Vibe agent configurations
  - `agents/` - Subagent definitions (implementer, code-quality-reviewer, spec-reviewer)
- `superpowers/` - [Obra Superpowers](https://github.com/obra/superpowers) submodule

### Superpowers Integration

Superpowers is added as a Git submodule to provide agentic skills and software development methodology.

To use Superpowers with Mistral Vibe (which is based on OpenCode):

1. **Clone this repository with submodules:**
   ```bash
   git clone --recursive https://github.com/kurosch/agent-config.git
   cd agent-config
   ```

2. **Or initialize submodules after cloning:**
   ```bash
   git submodule init
   git submodule update
   ```

3. **Configure OpenCode/Mistral Vibe to use Superpowers:**
   Add superpowers to your `opencode.json`:
   ```json
   {
     "plugin": ["superpowers@git+https://github.com/obra/superpowers.git"]
   }
   ```

4. **Restart Mistral Vibe/OpenCode** to load the plugin.

5. **Verify installation:** Ask your agent "Tell me about your superpowers"

### Available Subagents

- **Implementer** - Implements tasks with isolated context
- **Code Quality Reviewer** - Reviews code for bugs, conventions, and best practices
- **Spec Compliance Reviewer** - Verifies implementation matches requirements

### Updating Superpowers

To update the Superpowers submodule to the latest version:

```bash
cd agent-config
git submodule update --remote superpowers
```

### References

- [Obra Superpowers](https://github.com/obra/superpowers)
- [Superpowers Documentation](https://github.com/obra/superpowers/blob/main/docs/README.opencode.md)
