# Skills Repository

A collection of OpenCode agent skills for software development.

## 📦 Available Skills

### ssr-tanstack-strapi
Build SSR applications with TanStack Start and Strapi CMS. Use when creating content-driven websites with server-side rendering, SEO requirements, and headless CMS integration.

**Features:**
- Monorepo setup (pnpm workspaces)
- TanStack Query integration
- Type-safe API clients
- Production-ready patterns
- SEO optimization
- Image handling
- Search & filtering

## 🚀 Quick Start

### One-Line Installation

```
Fetch and follow instructions from https://raw.githubusercontent.com/zwlcoding/skills/refs/heads/main/INSTALL.md
```

### Installation

### Usage

1. **List available skills:**
   ```
   use skill tool to list skills
   ```

2. **Load a specific skill:**
   ```
   use skill tool to load ssr-tanstack-strapi
   ```

3. **Or simply ask OpenCode:**
   ```
   Help me build an SSR app with TanStack and Strapi
   ```

## 📁 Project Structure

```
skills/
├── ssr-tanstack-strapi/     # SSR + TanStack + Strapi skill
│   └── SKILL.md
├── INSTALL.md               # Installation guide
└── README.md               # This file
```

## 🛠️ Adding New Skills

To add a new skill:

1. Create a new directory: `mkdir new-skill-name`
2. Add `SKILL.md` with proper frontmatter:
   ```yaml
   ---
   name: new-skill-name
   description: Brief description of when to use this skill
   ---
   ```
3. Write your skill content in Markdown
4. Commit and push

## 📚 Skill Format

Each skill must follow OpenCode's SKILL.md format:

```markdown
---
name: skill-name
description: When to use this skill - what it does
---

# Skill Title

## When to Use

- Condition 1
- Condition 2

## Content

Your skill content here...
```

## 🔧 Development

### Project Setup

```bash
# Clone repository
git clone git@github.com:zwlcoding/skills.git
cd skills

# Make changes to skills
# ...

# Commit and push
git add .
git commit -m "Add new skill: xxx"
git push origin main
```

### Skill Priority

OpenCode loads skills in this priority order:
1. Project skills (`.opencode/skills/`)
2. Global skills (`~/.config/opencode/skills/`)
3. Claude-compatible skills (`.claude/skills/`)

## 📝 Contributing

1. Fork the repository
2. Create your skill directory
3. Follow the SKILL.md format
4. Test your skill with OpenCode
5. Submit a pull request

## 🐛 Troubleshooting

**Skills not loading?**
- Check that `SKILL.md` is in all caps
- Verify frontmatter includes `name` and `description`
- Ensure skill names are unique
- Check OpenCode logs for errors

**Skill not working?**
- Verify the directory name matches the skill name
- Check that description is 1-1024 characters
- Ensure name follows pattern: `^[a-z0-9]+(-[a-z0-9]+)*$`

## 📄 License

MIT License - see individual skill files for details.

## 🔗 Links

- [OpenCode Documentation](https://opencode.ai/docs/)
- [OpenCode Skills Guide](https://opencode.ai/docs/skills/)
- [Issues](https://github.com/zwlcoding/skills/issues)

---

Built with ❤️ for the OpenCode community.