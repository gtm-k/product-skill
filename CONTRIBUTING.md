# Contributing to Product Skill

Thank you for your interest in improving this product management skill file. Contributions from the community make this resource better for everyone.

*(New here? The [README](README.md) covers what product-skill is and how to use it. This page is for people who want to understand how it's built, extend it, or contribute.)*

## How it's built

product-skill is deliberately **one lean file** (`SKILL.md`). It opens by telling the AI to do four things on every product question: ask only the clarifying questions that genuinely matter, pick the *single* right framework instead of dumping a menu, lead with a recommendation, and run a blind-spot check sized to the stakes. A short routing section sends each kind of request (prioritization, pricing, metrics, discovery, and so on) to the matching part of the file. Keeping it to one portable file is a design choice: it loads fast, stays readable, and works identically on every platform — no bundle, no scripts, nothing to break when a tool updates.

## Go deeper — PRO modules

The base file handles the everyday job on its own. For a task that needs deep, worked treatment, the user types `Load PRO: <name>` and the AI hands over the exact block to paste — plain text, same on every platform, no install.

| `Load PRO:` | Use when you're… | Paste from |
|---|---|---|
| `pricing` | running a willingness-to-pay study, tiering, or AI/outcome pricing | `pro/pricing.md` |
| `ai-evals` | building a full eval plan, validating an AI judge, or monitoring quality | `pro/ai-evals.md` |
| `positioning` | doing an end-to-end positioning build, sales pitch, or launch plan | `pro/positioning.md` |
| `growth` | designing experiments, growth loops, or a PLG motion | `pro/growth.md` |
| `discovery` | writing interview guides, designing assumption tests, or translating needs to a spec (House of Quality) | `pro/discovery.md` |
| `metrics` | building a North Star + input-metric tree, value-driver tree, or platform-renewal metrics | `pro/metrics.md` |
| `strategy` | writing a strategy doc, business plan, portfolio/project-mix plan, or platform/innovation strategy | `pro/strategy.md` |

If a module isn't loaded, the file tells the AI to hand over the path and offer a clearly-flagged lighter answer from the base file — never to fake the curated depth.

## Customizing it for yourself

It's just a text file — edit it. Add your own frameworks, swap in your company's context and metrics, trim sections you don't use, or fork it for your team. Share-alike under CC BY-SA 4.0 means your version stays open too. Keep the file lean and portable — every addition should carry judgment a model wouldn't volunteer on its own (a when-to-use boundary, a calibration number, an anti-pattern, an opinionated default), not re-explain canon the AI already knows.

## How to Contribute

1. **Fork** this repository
2. **Create a branch** for your changes (`git checkout -b feature/add-framework`)
3. **Make your changes** to `SKILL.md`
4. **Test** your changes by uploading the modified file to an AI assistant and running a few PM scenarios
5. **Submit a Pull Request** with a description of what you changed and why

## What Makes a Good Contribution

- **New frameworks** — Add well-established, widely recognized frameworks with proper attribution (author, source, year)
- **Industry calibration** — Improve or add industry-specific guidance for underrepresented verticals (e.g., gaming, edtech, climate tech, government)
- **Test scenarios** — Add new test scenarios with scores and evaluation notes
- **Template improvements** — Enhance existing communication templates or add new ones
- **Factual corrections** — Fix inaccuracies, outdated information, or misattributed quotes
- **Clarity and structure** — Improve readability without changing substance

## Guidelines

- **Attribution is required.** Every framework, quote, or concept must cite its original author or source.
- **Keep it practical.** This skill file is designed for real-world use, not academic completeness. Every addition should help someone do better product work.
- **Test before submitting.** Upload your modified `SKILL.md` to at least one AI assistant and verify it produces quality output for a relevant PM scenario.
- **Follow existing structure.** Match the heading hierarchy, formatting, and tone of the existing content.
- **No proprietary content.** Do not contribute content from paywalled sources, internal company documents, or materials you don't have rights to share.

## Reporting Issues

If you find an error, outdated information, or have a suggestion but don't want to make the change yourself, [open an issue](../../issues) with:

- A description of the problem or suggestion
- The specific section of `SKILL.md` affected
- A source or reference if applicable

## License

By contributing, you agree that your contributions will be licensed under the same [CC BY-SA 4.0](LICENSE.md) license as the rest of this project.
