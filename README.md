# SOC Visual Instructor

A Claude Agent Skill that teaches cybersecurity and SOC Analyst topics through Bangla-first explanations, meaningful diagrams, realistic SOC scenarios, annotated logs, and safe practical exercises.

## What it does

- Teaches in simple Bangla while preserving standard English technical terms.
- Selects diagrams that fit the concept: Mermaid flowcharts, sequence diagrams, architecture diagrams, timelines, tables, and annotated logs.
- Explains every visual step by step.
- Connects theory to Tier 1 SOC workflows such as log analysis, alert triage, evidence validation, and escalation.
- Provides safe hands-on exercises suitable for a beginner with an 8 GB RAM computer.
- Recommends relevant YouTube videos only when exact links can be verified; otherwise it provides a clearly labeled search link.
- Uses quizzes and practical challenges to check understanding.

## Package structure

```text
soc-visual-instructor/
├── SKILL.md
├── README.md
├── references/
│   ├── visual-methods.md
│   └── diagram-patterns.md
├── templates/
│   └── lesson-template.md
└── examples/
    └── dns-visual-lesson.md
```

## Install

### Claude.ai

If your Claude account supports custom Skills:
1. Keep the `soc-visual-instructor` folder structure intact.
2. Zip the folder so `SKILL.md` is at the root of the skill folder inside the ZIP.
3. Open Claude settings and find the Skills / Customize area (the exact UI may vary by plan and product version).
4. Upload the ZIP as a custom Skill.
5. Enable the Skill if Claude presents an enable toggle.
6. Start a new chat and ask: `DNS কীভাবে কাজ করে SOC Analyst-এর দৃষ্টিকোণ থেকে Visual Lesson দিয়ে শেখাও।`

Custom Skill availability can depend on Claude plan and product settings. If upload is unavailable, copy the relevant instructions from `SKILL.md` into a Claude Project's Project Instructions and add the reference files as Project Knowledge.

### Claude Code

For a repository-based setup, place the folder at:

```text
.claude/skills/soc-visual-instructor/
```

The resulting path must be:

```text
your-project/
└── .claude/
    └── skills/
        └── soc-visual-instructor/
            ├── SKILL.md
            └── references/
```

Claude Code discovers project skills from the documented `.claude/skills/<skill-name>/SKILL.md` structure. Check current Claude Code documentation for any product-specific changes.

## Quick test prompts

- `TCP three-way handshake বাংলায় sequence diagram দিয়ে শেখাও।`
- `Windows Event ID 4625 কী বোঝায়? Annotated log example এবং SOC scenario দাও।`
- `একটি simulated brute-force alert investigate করতে আমাকে ধাপে ধাপে guide করো।`
- `SIEM কীভাবে raw logs থেকে alert তৈরি করে flowchart দিয়ে বোঝাও।`

## Important notes

- This Skill is an instruction package, not a SIEM, lab environment, browser, or video-search tool.
- Exact YouTube video verification requires browsing/search capability.
- Mermaid diagrams render visually only in interfaces that support Mermaid. The Skill instructs Claude to provide an ASCII or table fallback when needed.
- Never run commands against systems you do not own or have explicit permission to test.
- Review any future scripts or external additions before running them.

## Sources

- Anthropic Agent Skills overview: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview
- Anthropic Skill authoring best practices: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices
