# Skill Builder - Development Workspace

A development workspace for building new Claude Code skills with all necessary context, iteration history, and background documentation.

## Purpose

This directory serves as a **development lab for creating NEW skills**. It contains all the research, context, and iteration history needed to build high-quality Claude Code skills. Once skills are ready for deployment, they move to `~/.claude/skills` where they are maintained as production assets.

## Repository Status

**Active Development Workspace** - Used for building new skills and documenting the development process.

**GitHub Repository**: [JHaugaard/skill-builder](https://github.com/JHaugaard/skill-builder)

---

## Skills Developed Here

### Deployed Skills (Now maintained in ~/.claude/skills)

The following skills were built in this workspace and have been deployed to production. **Do NOT update these skills here.** All ongoing maintenance happens in `~/.claude/skills`.

#### 1. deployment-advisor
- **Formerly**: hosting-advisor
- **Purpose**: Recommend hosting strategy based on tech stack and project needs
- **Status**: Deployed - maintain in ~/.claude/skills
- **Built**: November 2025

#### 2. project-spinup
- **Formerly**: project-starter
- **Purpose**: Generate complete project foundations with personalized setup
- **Status**: Deployed - maintain in ~/.claude/skills
- **Built**: November 2025

#### 3. tech-stack-advisor
- **Purpose**: Analyze requirements and recommend appropriate technology stacks
- **Status**: Deployed - maintain in ~/.claude/skills
- **Built**: November 2025

#### 4. project-brief-writer
- **Purpose**: Create comprehensive PRD documents from project ideas
- **Status**: Deployed - maintain in ~/.claude/skills
- **Built**: November 2025

---

## Workflow Pattern

### Building New Skills (Work happens HERE)

```bash
# 1. Start development in skill-builder
cd /Volumes/dev/develop/skill-builder/

# 2. Create new skill directory
mkdir new-skill-name

# 3. Develop skill with all context available
# - Use background-docs/ for reference
# - Iterate with Claude Code
# - Test and refine

# 4. When ready for deployment, copy to production
cp -R new-skill-name /Users/john/.claude/skills/

# 5. Deploy to GitHub (from ~/.claude/skills)
cd /Users/john/.claude/skills
git add new-skill-name/
git commit -m "Add new-skill-name to skills suite"
git push origin main

# 6. The skill now lives in ~/.claude/skills
# Keep the version here as historical archive
```

### Maintaining Deployed Skills (Work happens in ~/.claude/skills)

```bash
# IMPORTANT: All updates to deployed skills happen in ~/.claude/skills
cd /Users/john/.claude/skills

# Make changes to skill files
# Edit deployment-advisor/SKILL.md (or any other skill)

# Commit and push changes
git add deployment-advisor/
git commit -m "Update deployment-advisor: add new pattern"
git push origin main

# Sync to Mac Mini
# (On Mac Mini)
cd /Users/john/.claude/skills
git pull origin main
```

**NEVER sync changes back from ~/.claude/skills to skill-builder**

---

## Directory Structure

```
skill-builder/
├── README.md                    # This file
├── repo-update.md              # Guide for syncing skills (gitignored)
├── HANDOFF-DOCUMENTATION.md    # Session continuity system
├── claude-code-agent-skills.md # Reference documentation
│
├── background-docs/            # Context and research
│   ├── claude-background.md
│   ├── deployment-patterns.md
│   └── ... (other reference docs)
│
├── deployment-advisor/         # ARCHIVED - deployed skill
│   └── SKILL.md
│
├── project-spinup/            # ARCHIVED - deployed skill
│   ├── SKILL.md
│   ├── EXAMPLES.md
│   └── QUICK_REFERENCE.md
│
├── tech-stack-advisor/        # ARCHIVED - deployed skill
│   └── SKILL.md
│
└── project-brief-writer/      # ARCHIVED - deployed skill
    └── SKILL.md
```

---

## Two Repository System

### This Repository (skill-builder)
- **Purpose**: Development workspace for NEW skills
- **Location**: `/Volumes/dev/develop/skill-builder`
- **GitHub**: [JHaugaard/skill-builder](https://github.com/JHaugaard/skill-builder)
- **Updates**: Only when building new skills
- **Contains**: Development history, context, background docs

### Production Repository (claude-skills)
- **Purpose**: Deployed, production-ready skills
- **Location**: `/Users/john/.claude/skills` (both machines)
- **GitHub**: [JHaugaard/claude-skills](https://github.com/JHaugaard/claude-skills)
- **Updates**: All ongoing skill maintenance
- **Contains**: Only final SKILL.md files (clean)

---

## Why This Pattern Works

### Context Separation
- **Building phase**: Needs extensive context, research, iteration (happens here)
- **Maintenance phase**: Needs focused updates to self-contained skills (happens in ~/.claude/skills)

### Single Source of Truth
- **New skills**: Built here, then deployed
- **Deployed skills**: SSOT is ~/.claude/skills
- **One-way flow**: skill-builder → ~/.claude/skills (never reverse)

### Skills Are Self-Documenting
Each SKILL.md file is comprehensive (400-800 lines) and contains:
- Complete purpose and usage instructions
- Workflow and decision frameworks
- Examples and patterns
- Everything Claude needs to understand and refine it

The background-docs were scaffolding for building; the final skills don't need them for refinements.

---

## Key Files & Documentation

### repo-update.md (gitignored)
Step-by-step guide for syncing skills between machines:
- Part 1: Update skills on MacBook
- Part 2: Set up skills on Mac Mini
- Part 3: Future workflow for updates

### HANDOFF-DOCUMENTATION.md
System for maintaining session continuity when working with Claude Code across multiple sessions.

### background-docs/
Research and context files used during skill development:
- Reference documentation
- Design patterns
- Technical requirements
- Infrastructure specifications

---

## Important Reminders

### DO:
- ✅ Build new skills in this directory
- ✅ Use background-docs/ for context and research
- ✅ Copy completed skills to ~/.claude/skills for deployment
- ✅ Maintain deployed skills in ~/.claude/skills
- ✅ Keep archived versions here for historical reference
- ✅ Commit new skill development work to this repo

### DON'T:
- ❌ Update deployed skills in this directory
- ❌ Sync changes from ~/.claude/skills back to here
- ❌ Use this directory for skill maintenance/refinements
- ❌ Confuse development workspace with production deployment

---

## Getting Started with a New Skill

1. **Brainstorm and research** the skill concept
2. **Create a new directory** in skill-builder/
3. **Start with SKILL.md** following the established pattern
4. **Iterate with Claude Code** using all available context
5. **Test the skill** in Claude Code
6. **When ready**, copy to ~/.claude/skills and deploy
7. **Archive the development version** here for reference

---

## Related Resources

### Claude Code Skills Documentation
- [Official Claude Code Docs](https://docs.claude.com/en/docs/claude-code)
- Skills guide in background-docs/

### Your Infrastructure Context
- **Hosting**: Hostinger VPS (Docker-based)
- **Self-hosted**: Supabase, PostgreSQL, n8n, Ollama, Redis, Nginx, Wiki.js
- **DNS**: Cloudflare
- **File Storage**: Backblaze B2
- **Development**: Heavy reliance on Claude Code

---

## Version History

**v1.0** (November 2025)
- Initial skill-builder workspace setup
- Developed 4 core skills for project workflow
- Established two-repository pattern
- Created deployment workflow

---

## Notes

This README documents the pattern and workflow established through the development of the first four skills. The approach balances:
- Detailed context for building (here)
- Clean deployment for production (~/.claude/skills)
- Clear separation of development vs. maintenance phases
- Sustainable long-term workflow for hobbyist development

As you build more skills, this pattern will continue to serve you well. Each skill built here adds to your understanding and capability while maintaining a clean, manageable production environment.
