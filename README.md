# Ruby Skill — Structural Decomposition × Meaning Verification

**Take any artifact — code, document, or content — and elevate it to a beautiful higher-level design.**

Ruby Skill (러비스킬) fuses two of the most powerful analytical traditions in Western philosophy into a single, actionable pipeline. Bertrand Russell's logical atomism provides the structural scalpel; Ludwig Wittgenstein's meaning-in-use philosophy provides the semantic filter. Together, they catch what neither can alone: structure without meaning ("technically correct but nobody uses it") and meaning without structure ("intuitive but fragile").

## Why This Exists

Most review tools optimize for one dimension — linting catches syntax, style guides catch formatting, peer review catches logic gaps. But none of them answer the deeper question: **Is this artifact as beautiful as it could be?**

Beauty here isn't aesthetic preference. It's a precise definition: **minimum structure for maximum meaning, relative to purpose.** Ruby Skill operationalizes this definition through a 5-phase pipeline that decomposes, verifies, judges, and reconstructs.

## What It Does

### Three Modes

| Mode | Trigger | Output |
|------|---------|--------|
| **Diagnose** | "Decompose this", "Analyze this" | Atomic decomposition → Mapping table → 6-axis diagnosis |
| **Evaluate** | "Evaluate this", "Review this" | Diagnosis + Dual verification (Russell + Wittgenstein) + Bottleneck identification |
| **Elevate** | "Elevate this", "Make this beautiful" | Full pipeline → Concrete upper-level design proposal (default mode) |

### The Pipeline

1. **Domain Detection** — Automatically identifies whether the input is code, document, content, or hybrid, and loads the appropriate adapter.

2. **Russell Decomposition** — Breaks the artifact into irreducible atomic units. Tags abstraction levels. Surfaces hidden assumptions. Marks unnecessary abstractions for removal. Outputs a complete mapping table (original element → decomposed result, zero omissions).

3. **Wittgenstein Verification** — Takes every row of the mapping table through 5 meaning checks: structural isomorphism (Picture Theory), contextual consistency (Language Games), convention alignment (Rule Following), audience fit (Form of Life), and shareability (Private Language). Structure can pass while meaning fails.

4. **6-Axis Judgment** — Scores the artifact on Purpose, Direction, Coherence, Minimality, Extensibility, and Fitness-for-Use. Identifies the bottleneck axis that constrains overall quality.

5. **Upper-Level Design** — Proposes concrete improvements targeting the bottleneck axis. Includes a mandatory Detail Preservation Matrix (every original element tracked: kept / transformed / removed + rationale) and side-by-side Before/After comparisons using actual excerpts, not abstract directions.

6. **Self-Verification** — Re-checks the proposal through both Russell decomposition and Wittgenstein verification. Confirms no details were lost and the design is implementable.

## When to Use It

- **Code review** — When you want more than "this function is too long." Ruby Skill identifies *why* the architecture is suboptimal and proposes a structurally sound, semantically meaningful alternative.
- **Document restructuring** — Reports, proposals, documentation that *works* but feels scattered or bloated. The pipeline finds the minimal structure that preserves all meaning.
- **Content elevation** — Blog posts, newsletters, educational material where the ideas are good but the presentation doesn't match. Decompose the content, verify the meaning survives, rebuild it beautifully.
- **Architecture decisions** — When you need a rigorous framework to evaluate whether a design is genuinely elegant or just familiar.

## What's Inside

```
ruby-skill/
├── SKILL.md                          # Hub — pipeline, rules, modes, gotchas
└── references/
    ├── russell-frame.md              # Deep-researched Russell philosophy → practical decomposition tools
    ├── wittgenstein-frame.md         # Deep-researched Wittgenstein philosophy → meaning verification tools
    ├── beauty-criteria.md            # 6-axis evaluation system + L0–L4 beauty levels
    └── domain-adapters.md            # Coding / Document / Content / Hybrid detection & adaptation
```

Each reference file is a standalone deep-research document — not a summary, but a working translation of philosophical frameworks into executable checklists and decision criteria.

## Hard Rules

1. **Zero detail loss** — Every element in the original must appear in the mapping table. Missing an element invalidates the entire analysis.
2. **Mapping table first** — No evaluation begins without a complete original → decomposed mapping.
3. **No silent deletion** — Removing an element requires explicit justification. Deleted items move to `_archive`, never vanish.
4. **Dual verification mandatory** — Passing Russell's structural check is necessary but not sufficient. Wittgenstein's meaning check must also pass.

## License

MIT
