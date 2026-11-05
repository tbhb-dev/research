# Research

This public repository holds research reports for tbhb-dev work. A report gathers sources and evidence on a question as input to design. It contains only new, clean work. A private counterpart exists for research that can't be public.

## Layout

Each report is a directory under `reports/`, named `r-N-<slug>`. Its main document is `REPORT.md`, and its sources go in the same directory.

## Workflow

Every report lands through a pull request. See [AGENTS.md](AGENTS.md) for the setup and the rules.

## Checks

Bazel runs every gate from tbhb-dev/rules: `bazelisk test //...`.
