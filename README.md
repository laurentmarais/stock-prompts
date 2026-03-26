# stock-prompts

This repository stores reusable prompts and dated markdown outputs for a small stock-research workflow.

The workflow is built around three related tasks:

- producing a short-term global macro outlook,
- turning that macro view into a conservative swing-trade shortlist,
- identifying early momentum setups using public market signals.

The repo is lightweight by design. There are no scripts or data pipelines here. The main assets are the prompt templates and the generated research snapshots.

## What Is In This Repo

### Prompt templates

The prompts folder contains the source prompts used to generate each type of report:

- prompts/prompt_macro_economy.txt
- prompts/prompt_stocks_macro.txt
- prompts/prompt_stocks_momentum.txt

These prompt files define the structure, filters, and writing style for each output.

### Current dated outputs

The root of the repo contains dated markdown snapshots, including:

- global_economic_outlook_20260325.md
- fast_swing_stocks20260325.md
- momentum_stocks_20260325.md

These files are point-in-time research notes, not live models. They reflect the assumptions, market backdrop, and screening judgments that applied on the date shown in each file.

### Archived versions

The old folder keeps earlier non-dated or prior versions of the same research streams:

- old/global_economic_outlook.md
- old/fast_swing_stocks.md

Use these for comparison when you want to track how the thesis or shortlist changed across refreshes.

## Repository Structure

```text
.
├── README.md
├── fast_swing_stocks20260325.md
├── global_economic_outlook_20260325.md
├── momentum_stocks_20260325.md
├── old/
│   ├── fast_swing_stocks.md
│   └── global_economic_outlook.md
└── prompts/
    ├── prompt_macro_economy.txt
    ├── prompt_stocks_macro.txt
    └── prompt_stocks_momentum.txt
```

## Workflow

The intended sequence is:

1. Generate the macro view.
2. Use that macro view as the top-down filter for conservative swing-trade candidates.
3. Run a separate momentum scan for early attention shifts and catalyst-driven setups.

In practice:

1. Start with prompts/prompt_macro_economy.txt to produce the next global outlook.
2. Feed that outlook into prompts/prompt_stocks_macro.txt to build the resilient swing-trade shortlist.
3. Run prompts/prompt_stocks_momentum.txt to build a separate momentum watchlist based on public signals such as catalyst timing, volume expansion, and relative strength.

This separation matters:

- the macro prompt is top-down,
- the fast swing prompt is valuation and resilience driven,
- the momentum prompt is tape, catalyst, and attention driven.

## How To Use This Repo

### Option 1: Use the prompts directly in ChatGPT or Copilot

1. Open the prompt file you want to use.
2. Paste its contents into your model of choice.
3. If needed, attach or reference the latest macro output before running the stock screens.
4. Save the result as a new dated markdown file in the repo root.

Suggested cadence:

- update the macro outlook when the market regime changes or at least weekly,
- refresh the fast swing screen after the macro note changes,
- refresh the momentum screen more frequently when catalysts or volume patterns shift.

### Option 2: Use the repo as a research log

You can also treat the repository as a versioned notebook of market views:

- keep each refresh as a dated markdown snapshot,
- preserve older files instead of overwriting them,
- compare how the shortlists evolve as macro conditions change.

## Output Conventions

Most output files follow the same general pattern:

- title and date,
- scope and filtering logic,
- primary candidates in a markdown table,
- closest matches or watchlist names,
- short notes and method section.

This makes it easier to compare one refresh against the next without re-learning the format each time.

## What The Prompts Optimize For

### Global macro outlook

Focuses on:

- market-relevant geopolitics,
- central-bank and rate expectations,
- inflation, yields, and growth,
- regional differences across major markets,
- sector implications for the next month.

### Fast swing stocks

Focuses on:

- profitable companies,
- smaller-cap names,
- valuation support through tangible asset value or a close equivalent,
- conservative discounted cash flow support,
- resilience under the stated macro backdrop.

### Momentum stocks

Focuses on:

- dated upcoming catalysts,
- early accumulation and volume expansion,
- relative strength before a full breakout,
- adequate liquidity,
- avoiding promotion-driven or structurally fragile names.

## Limitations

- This repo does not fetch market data automatically.
- Outputs depend on the quality and freshness of the underlying model inputs.
- The research is a screening and idea-generation tool, not a trading system.
- The files are not investment advice and should be validated with current market data before use.

## Maintaining The Repo

If you keep using this workflow, the cleanest maintenance pattern is:

1. Leave prompt files stable unless you want to change the methodology.
2. Add new dated markdown outputs for each refresh.
3. Move older reference files into old only when you want to preserve historical context without cluttering the root.
4. Use git history to review how prompt wording changes affected the outputs over time.

## Future Improvements

If you want to expand the repo later, sensible additions would be:

- a consistent file-naming convention for dated outputs,
- a changelog of prompt revisions,
- a template for weekly refreshes,
- a simple script or Makefile to scaffold new dated output files.