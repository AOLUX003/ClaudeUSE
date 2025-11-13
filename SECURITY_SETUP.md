# Security Setup Guide

This repository has comprehensive secret scanning protection at multiple layers.

## Quick Start

### 1. Install Pre-Commit Hooks (Local Protection)

```bash
# Install pre-commit tool
pip install pre-commit

# Install the hooks in this repository
cd /path/to/ClaudeUSE
pre-commit install

# Test it works
pre-commit run --all-files
```

### 2. Verify GitHub Actions (Remote Protection)

GitHub Actions automatically scan on:
- Every push to main/master/develop
- Every pull request
- Daily at 2 AM UTC

View workflow runs: https://github.com/AOLUX003/ClaudeUSE/actions

## Protection Layers

### Layer 1: Local Pre-Commit Hooks
**Blocks commits BEFORE they leave your machine**

- TruffleHog secret detection
- Gitleaks scanning
- .env file blocking
- MCP configuration file blocking
- Backup file detection
- API key pattern matching (Anthropic, OpenAI, GitHub, AWS)
- .gitignore validation

### Layer 2: GitHub Actions Workflow
**Scans code in GitHub on every push/PR**

- TruffleHog (verified secrets only)
- Gitleaks comprehensive scan
- File checks (.env, MCP configs, backups)
- Pattern matching (API keys, tokens)
- .gitignore validation

### Layer 3: Daily Automated Scans
**Catches anything that slipped through**

- Runs automatically at 2 AM UTC
- Full repository history scan
- Email notifications on findings

## What Gets Blocked

### Files
- `.env`, `.env.*` (environment files)
- `mcp.json`, `claude_desktop_config.json` (MCP configs)
- `*.bak`, `*.old`, `*.tmp` (backup files)
- `credentials.json`, `secrets.json`
- `*.key`, `*.pem` (key files)

### Patterns
- GitHub tokens: `ghp_`, `gho_`, `ghs_`, `ghu_`, `ghr_`
- Anthropic API keys: `sk-ant-api##-...`
- OpenAI API keys: `sk-...` (48 chars)
- AWS Access Keys: `AKIA...`
- Generic API keys and passwords
- Bearer tokens

## Troubleshooting

### Pre-commit hook blocking legitimate code?

```bash
# Skip hooks for this commit only (use with caution!)
git commit --no-verify -m "your message"

# Or update .pre-commit-config.yaml to exclude false positives
```

### Need to commit a test fixture with fake secrets?

Add to `.pre-commit-config.yaml`:
```yaml
exclude: ^tests/fixtures/
```

### Check what would be scanned

```bash
# Run all hooks without committing
pre-commit run --all-files

# Run specific hook
pre-commit run block-mcp-configs --all-files
```

## Best Practices

1. **Never commit secrets** - Use environment variables
2. **Use .env.example** - Template without real values
3. **Rotate exposed secrets immediately**
4. **Review .gitignore** - Ensure it includes all sensitive patterns
5. **Run pre-commit before pushing** - `pre-commit run --all-files`

## MCP Configuration Security

MCP tokens should NEVER be committed to git. Instead:

### Development
```bash
# Store in user config directory (already ignored by git)
# Windows: %APPDATA%/Claude/
# macOS: ~/Library/Application Support/Claude/
# Linux: ~/.config/claude/
```

### CI/CD
```bash
# Use GitHub Secrets
# Settings → Secrets and variables → Actions → New repository secret
```

## Emergency Response

If you accidentally commit a secret:

1. **Rotate the secret immediately**
   - GitHub: Settings → Developer settings → Tokens → Revoke
   - Anthropic: https://console.anthropic.com/settings/keys

2. **Remove from git history**
   ```bash
   git filter-repo --path-glob '**/*secret-file*' --invert-paths
   # OR use BFG Repo-Cleaner
   ```

3. **Force push** (if safe)
   ```bash
   git push --force
   ```

4. **Notify your team**

## Additional Resources

- [GitHub Secret Scanning](https://docs.github.com/en/code-security/secret-scanning)
- [TruffleHog Documentation](https://github.com/trufflesecurity/trufflehog)
- [Gitleaks Documentation](https://github.com/gitleaks/gitleaks)
- [Pre-commit Documentation](https://pre-commit.com/)

---

🤖 Generated with [Claude Code](https://claude.com/claude-code)
