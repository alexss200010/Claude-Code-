# Claude Code Resources

A comprehensive collection of Claude Code setup guides, workflow templates, and custom skills to accelerate your AI-assisted development workflow.

## What's Inside

### 📚 [Comprehensive Cheat Sheet](cheat-sheet.md)

A complete guide covering everything you need to master Claude Code:

- **First-Time Setup**: Login, Shift+Enter configuration, essential settings
- **MCP Server Integration**: Supabase, Context7, and custom server setup
- **Hooks & Automation**: Event-driven workflows and audio feedback
- **Editor Shortcuts**: Keyboard-first navigation for Cursor/VS Code
- **Slash Commands**: Built-in commands and ShipKit workflow templates
- **Development Workflows**: Practical patterns for code review, commits, and more

[→ Read the Cheat Sheet](cheat-sheet.md)

### 🔧 Custom Skills

#### Project Analyzer Skill

A production-ready Claude Code skill that systematically analyzes codebases, following the official [anthropics/skills](https://github.com/anthropics/skills) format.

**Features:**
- Technology stack detection (Node.js, Python, Rust, Go, Java, etc.)
- Project structure analysis
- Architecture pattern identification
- Dependency review
- Entry point identification

**Installation:**

```bash
# Copy the skill to your Claude Code skills directory
cp -r project-analyzer ~/.claude/skills/

# Or symlink it for easier updates
ln -s "$(pwd)/project-analyzer" ~/.claude/skills/project-analyzer
```

**Usage:**

Once installed, the skill activates automatically when you ask:
- "What does this project do?"
- "Analyze this codebase"
- "Explain this repository"

[→ View Skill Definition](project-analyzer/SKILL.md)

#### Commit Helper Skill

A comprehensive git workflow skill that guides you through creating meaningful, well-structured commits following industry best practices and Conventional Commits specification.

**Features:**
- Atomic commit principles (one logical change per commit)
- Conventional Commits support (feat, fix, docs, refactor, etc.)
- 6-step commit analysis process
- Message templates for features, fixes, refactoring, and docs
- Pre-commit checklist for code quality
- Special cases handling (WIP, amending, co-authors)
- Anti-patterns to avoid

**Installation:**

```bash
# Copy the skill to your Claude Code skills directory
cp -r commit-helper ~/.claude/skills/

# Or symlink it for easier updates
ln -s "$(pwd)/commit-helper" ~/.claude/skills/commit-helper
```

**Usage:**

Once installed, the skill activates automatically when you:
- Ask to "commit changes" or "create a commit"
- Request "help with commit message"
- Need guidance on organizing multiple changes
- Want to follow git best practices

[→ View Skill Definition](commit-helper/SKILL.md)

### 📁 Project Organization Structure

Pre-configured directory structure for organizing your Claude Code projects:

```
├── Assets/      # Project assets (images, designs, etc.)
├── Content/     # Content files and documents
├── Notes/       # Project notes and documentation
├── Prompts/     # AI prompts and templates
├── README/      # Additional documentation
├── Research/    # Research materials and references
├── Strategy/    # Strategy documents and planning
└── Tasks/       # Task management and tracking
```

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/alexss200010/Claude-Code-.git
cd Claude-Code-
```

### 2. Read the Cheat Sheet

Open [`cheat-sheet.md`](cheat-sheet.md) for comprehensive setup and usage instructions.

### 3. Install Custom Skills

```bash
# Install both skills
cp -r project-analyzer commit-helper ~/.claude/skills/

# Or install individually
cp -r project-analyzer ~/.claude/skills/
cp -r commit-helper ~/.claude/skills/
```

### 4. Use the Directory Structure

Copy the directory structure to your own projects:

```bash
# Copy to a new project
cp -r Assets Content Notes Prompts README Research Strategy Tasks /path/to/your/project/
```

## Configuration Examples

### Claude Code Auto-Approval Settings

This repository includes example configuration in `.claude/settings.local.json`:

```json
{
  "permissions": {
    "allow": [
      "Bash(git add:*)",
      "Bash(git commit:*)",
      "WebFetch(domain:raw.githubusercontent.com)"
    ]
  }
}
```

### Recommended Settings

For optimal workflow, consider adding to your `~/.claude/settings.json`:

```json
{
  "model": "claude-sonnet-4-5-20250929",
  "autoApprovalSettings": {
    "enabled": true,
    "patterns": [
      "Read(/**)",
      "Bash(npm run lint)",
      "Bash(git log:*)"
    ]
  },
  "statusLine": {
    "enabled": true,
    "template": "{{model}} | {{tokens}}"
  }
}
```

## What is Claude Code?

[Claude Code](https://claude.com/claude-code) is Anthropic's official command-line interface for Claude AI, designed specifically for software engineering tasks. It provides:

- Deep codebase understanding
- Autonomous task execution
- Tool-based file operations
- Git integration
- Custom skill extensibility
- MCP server support

## Contributing

Have improvements or additional skills to share? Contributions are welcome:

1. Fork the repository
2. Create your feature branch
3. Add your improvements or new skills
4. Submit a pull request

## Resources

- [Claude Code Official Docs](https://support.claude.com/en/collections/11415298-claude-code)
- [Anthropic Skills Repository](https://github.com/anthropics/skills)
- [Creating Custom Skills Guide](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [Claude API Documentation](https://docs.anthropic.com/)

## License

This repository is provided as-is for educational and development purposes.

---

**Made with** [Claude Code](https://claude.com/claude-code)
