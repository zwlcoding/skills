# Installing Skills for OpenCode

## Prerequisites

- [OpenCode.ai](https://opencode.ai) installed
- Git installed

## Installation Steps

### 1. Clone Skills Repository

```bash
# Clone to a temporary location
git clone git@github.com:zwlcoding/skills.git /tmp/zwlcoding-skills
```

### 2. Install Skills

OpenCode discovers skills from `~/.config/opencode/skills/<skill-name>/SKILL.md`. You need to copy or symlink each skill individually:

**Option A: Copy skills (recommended)**
```bash
# Create skills directory if not exists
mkdir -p ~/.config/opencode/skills

# Copy all skills from the repository
cp -r /tmp/zwlcoding-skills/ssr-tanstack-strapi ~/.config/opencode/skills/

# Clean up temporary clone
rm -rf /tmp/zwlcoding-skills
```

**Option B: Create symbolic links (for easy updates)**
```bash
# Create skills directory if not exists
mkdir -p ~/.config/opencode/skills

# Create symlinks for each skill
ln -s /tmp/zwlcoding-skills/ssr-tanstack-strapi ~/.config/opencode/skills/ssr-tanstack-strapi

# Keep the repository for future updates
# Repository remains at /tmp/zwlcoding-skills or move to permanent location
```

### 3. Verify Installation

Check that skills are in the correct location:

```bash
ls -la ~/.config/opencode/skills/
# Should show: ssr-tanstack-strapi/

ls -la ~/.config/opencode/skills/ssr-tanstack-strapi/
# Should show: SKILL.md
```

### 4. Restart OpenCode

Restart OpenCode to load the newly installed skills.

## Usage

### Available Skills

Currently included:
- `ssr-tanstack-strapi`: Use when working with SSR, TanStack Query, and Strapi integrations

### Loading Skills

Use OpenCode's native `skill` tool:

```bash
use skill tool to load ssr-tanstack-strapi
```

Or simply ask OpenCode:
```
Use the ssr-tanstack-strapi skill to help me with my project
```

Check available skills with:
```bash
skill tool to list skills
```

## Adding Skills to Your Project

For project-specific usage, copy skills to your project:

```bash
mkdir -p .opencode/skills
cp -r ~/.config/opencode/skills/ssr-tanstack-strapi .opencode/skills/
```

## Updating Skills

### If you used Option A (copy):
```bash
# Re-clone and re-copy
git clone git@github.com:zwlcoding/skills.git /tmp/zwlcoding-skills
rm -rf ~/.config/opencode/skills/ssr-tanstack-strapi
cp -r /tmp/zwlcoding-skills/ssr-tanstack-strapi ~/.config/opencode/skills/
rm -rf /tmp/zwlcoding-skills
```

### If you used Option B (symlink):
```bash
# Just pull updates
cd /path/to/zwlcoding-skills
git pull origin main
```

## Skills Priority Order

OpenCode loads skills in this priority order:
1. **Project skills** (`.opencode/skills/`) - Highest priority
2. **Global skills** (`~/.config/opencode/skills/`) - Medium priority  
3. **Claude-compatible skills** (`.claude/skills/`, `~/.claude/skills/`) - Fallback

## Troubleshooting

### Skills not found

1. **Check skill location:**
   ```bash
   ls ~/.config/opencode/skills/
   ```
   Each skill should be a direct subdirectory, not nested.

2. **Verify SKILL.md exists:**
   ```bash
   ls ~/.config/opencode/skills/ssr-tanstack-strapi/SKILL.md
   ```

3. **Check skill format:**
   - `SKILL.md` must be in ALL CAPS
   - Must have frontmatter with `name` and `description`
   - Directory name must match skill name in frontmatter

4. **Restart OpenCode** after installing skills

### Common Mistakes

❌ **Wrong:** Nested directory structure
```
~/.config/opencode/skills/zwlcoding-skills/ssr-tanstack-strapi/SKILL.md
```

✅ **Correct:** Flat directory structure
```
~/.config/opencode/skills/ssr-tanstack-strapi/SKILL.md
```

## Contributing

1. Fork the repository
2. Create a new skill directory with `SKILL.md`
3. Follow the skill format in existing skills
4. Submit a pull request

## Getting Help

- Report issues: https://github.com/zwlcoding/skills/issues
- Documentation: See individual skill files for detailed usage