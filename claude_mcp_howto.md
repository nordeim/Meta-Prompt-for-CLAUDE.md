# Validation of Your `claude mcp add` Commands

All of your commands conform to the documented syntax:

```bash
claude mcp add <name> [-s user] [-e KEY=VAL…] -- <launch-command>
```

Below is a quick audit:

| Command                                                                                  | `-s` Scope | Env Vars                                             | Final Config Target |
|------------------------------------------------------------------------------------------|------------|------------------------------------------------------|---------------------|
| `claude mcp add context7 -- npx -y @upstash/context7-mcp@latest`                         | local      | none                                                 | project-local       |
| `claude mcp add playwright -- npx -y @playwright/mcp@latest`                             | local      | none                                                 | project-local       |
| `claude mcp add firecrawl -e FIRECRAWL_API_KEY=… -- npx -y firecrawl-mcp`                | local      | `FIRECRAWL_API_KEY`                                  | project-local       |
| `claude mcp add firecrawl -s user -e FIRECRAWL_API_KEY=… -- npx -y firecrawl-mcp`        | user       | `FIRECRAWL_API_KEY`                                  | user-level          |
| `claude mcp add playwright -s user -- npx -y @playwright/mcp@latest`                    | user       | none                                                 | user-level          |
| `claude mcp add context7 -s user -- npx -y @upstash/context7-mcp@latest`                | user       | none                                                 | user-level          |

- Each command uses `--` to end `claude`’s flag parsing and hand off all remaining args (e.g. `-y`) to the inner `npx` invocation.
- The `-s user` flag correctly shifts the config write target from project-local to your home directory.
- Your environment variable syntax with `-e KEY=VAL` is spot-on.

---

## Config File Locations

- **Project-local config**  
  Located in the working directory under  
  ```
  .claude/project-config.json
  ```  
  This file accumulates all MCP servers added without `-s user`.

- **User-level config**  
  Stored in your home folder at  
  ```
  ~/.claude/settings.json
  ```  
  (or on some installs `~/.claude/config.json`)  
  This holds servers registered with `-s user`.

---

## Next-Level Tips

- To inspect the exact JSON structure, open your project’s `.claude/project-config.json` or `~/.claude/settings.json` in an editor.
- Remove an entry with  
  ```bash
  claude mcp remove <name> [-s user]
  ```
- Override a local setting temporarily by passing `-s user` or vice versa.
- Pin a specific Docker-based server by replacing the `npx` line with your `docker run …` command after the `--`.

Let me know if you want examples of removal workflows or deeper dives into env-var precedence!
