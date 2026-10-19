---
name: hermes-remote-mcp-setup
description: "Use when installing remote OAuth MCP servers in Hermes."
version: 1.0.0
author: Hermes Agent
license: MIT
platforms: [macos, linux, windows]
metadata:
  hermes:
    tags: [hermes, mcp, oauth, remote-server, setup, verification]
---

# Hermes Remote MCP Setup

## When to Use

Use this skill when adding, authorizing, troubleshooting, or verifying a remote OAuth MCP server in Hermes.

## Procedure

1. **Preserve the requested server identity and endpoint.** Use the exact URL supplied by the user first. If it returns a non-MCP response, consult the vendor's official documentation or endpoint metadata before trying an alternate endpoint; never silently substitute a guessed URL.
2. **Add OAuth-capable servers with the native CLI.** Use:
   ```bash
   hermes mcp add <name> --url <endpoint> --auth oauth
   ```
   Add `--connect-timeout 120` when authorization or tool discovery is slow.
3. **Run interactive setup through a PTY.** The initial OAuth flow may open a browser and pause for authorization. Keep the process alive, tell the user to complete authorization in the browser, and never request or accept OAuth codes in chat.
4. **Enable tools explicitly.** When Hermes lists discovered tools, select all only when the user asked to install the server generally; otherwise select the requested subset. In PTY flows, a raw `y\r` may be needed after a normal submit if the selection prompt remains open.
5. **Verify before reporting success.** Run:
   ```bash
   hermes mcp list
   hermes mcp test <name>
   hermes config get mcp_servers.<name>
   ```
   Report the endpoint, auth method, connection status, and exact discovered/enabled tool count.
6. **State activation scope.** Native MCP discovery is startup/session scoped. Tell the user to run `/reload-mcp` or start a new session before using newly added tools in an already-open conversation.

## Pitfalls

- Do not save a server after a failed endpoint probe unless the user explicitly wants a deferred, unverified configuration; a 403 HTML page or an SSE content-type mismatch is evidence that the URL is not the usable MCP endpoint.
- Do not claim OAuth setup succeeded merely because Hermes wrote configuration; require a successful authenticated `hermes mcp test`.
- Keep credentials, authorization codes, bearer tokens, and full OAuth URLs out of memory, skills, and chat; they are secrets or short-lived session data.
- Treat vendor endpoint redirects as a discovery problem, not a reason to normalize the user's URL silently; preserve the original URL in the report and name the verified alternate endpoint.
