# Installing Waylon Skills for OpenCode

## Prerequisites

- [OpenCode.ai](https://opencode.ai) installed
- Git installed

## Installation Steps

### 1. Clone Skills Repository

```bash
git clone git@github.com:zwlcoding/skills.git ~/.config/opencode/skills/zwlcoding-skills
```

### 2. Configure OpenCode Skills Directory

OpenCode automatically discovers skills from these locations:

- Project config: `.opencode/skills/<name>/SKILL.md`
- Global config: `~/.config/opencode/skills/<name>/SKILL.md`
- Project Claude-compatible: `.claude/skills/<name>/SKILL.md`
- Global Claude-compatible: `~/.claude/skills/<name>/SKILL.md`

For global usage, skills will be automatically discovered from `~/.config/opencode/skills/zwlcoding-skills/ssr-tanstack-strapi/SKILL.md`

### 3. Add Skills to Your Project (Optional)

For project-specific usage, copy skills to your project:

```bash
mkdir -p .opencode/skills
cp -r ~/.config/opencode/skills/zwlcoding-skills/* .opencode/skills/
```

### 4. Restart OpenCode

Restart OpenCode to ensure all skills are loaded.

## Usage

### Available Skills

Currently included:
- `ssr-tanstack-strapi`: Use when working with SSR, TanStack Query, and Strapi integrations

### Loading Skills

Use OpenCode's native `skill` tool:

```bash
use skill tool to load ssr-tanstack-strapi
```

Or simply ask OpenCode to use the skill by name.

Check available skills with:
```bash
skill tool to list skills
```

### Adding New Skills

To add more skills in the future:

#### Method 1: Add to Repository
```bash
cd ~/.config/opencode/skills/zwlcoding-skills
git pull origin main  # Get latest skills
```

#### Method 2: Add Personally
Create new skills in your project:

```bash
mkdir -p .opencode/skills/new-skill
```

Create `.opencode/skills/new-skill/SKILL.md`:

```markdown
---
name: new-skill
description: Use when [condition] - [what it does]
---

# New Skill

[Your skill content here]
```

#### Method 3: Add Globally
Add to your personal skills directory:

```bash
mkdir -p ~/.config/opencode/skills/new-skill
```

## Skills Priority Order

1. **Project skills** (`.opencode/skills/`) - Highest priority
2. **Global skills** (`~/.config/opencode/skills/`) - Medium priority  
3. **Claude-compatible skills** (`.claude/skills/`, `~/.claude/skills/`) - Fallback

## Updating Skills

```bash
# Update all skills
cd ~/.config/opencode/skills/zwlcoding-skills
git pull origin main

# Copy updated skills to project if needed
cp -r ~/.config/opencode/skills/zwlcoding-skills/* .opencode/skills/
```

## Troubleshooting

### Skills not found

1. Check if skills are loaded: `ls -l ~/.config/opencode/skills/zwlcoding-skills`
2. Verify skill files exist and have correct SKILL.md format
3. Check that skill names match directory names (e.g., `ssr-tanstack-strapi` directory)
4. Use `skill` tool to list available skills
5. Check OpenCode logs for loading errors

### Specific skill not working

1. Verify the skill directory contains a `SKILL.md` file
2. Check the skill metadata (name and description) is properly formatted
3. Ensure skill content follows OpenCode skill standards

### Tool Mapping

When skills reference tools not available in OpenCode:
- `TodoWrite` → Use task planning tools or create todo lists manually
- `Task` with subagents → Use `@mention` syntax for parallel work
- Other tools → Use OpenCode's native tool equivalents

## Contributing

1. Fork the repository
2. Create a new skill in appropriate directory
3. Follow the skill format in existing skills
4. Submit a pull request

## Getting Help

- Report issues: https://github.com/zwlcoding/skills/issues
- Documentation: See individual skill files for detailed usage