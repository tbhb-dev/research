# Agent instructions

This is tbhb-dev/research, the public repository of research reports for tbhb-dev work. It's public and contains only new, clean work. A private counterpart exists for research that can't be public. Never copy content from it into this repository.

## Standing rules

- Everything here is public. Never write a private repository's name, a private host name, tailnet details, an internal URL, or anything from private work. Refer to a machine by its role, such as `test-service` or `public-resolver`.
- Never write a public IP address in a commit, a pull request, or a report. The `public-ipv4` gitleaks rule enforces this.
- Never open credential files, print secrets, or commit secret values. Secrets live in 1Password only.

## Writing a report

Put each report in its own directory, `reports/r-N-<slug>/`, with the report in `REPORT.md`. The number comes from this repository's own counter, R-1, R-2, and so on. @tbhb assigns the number, so don't pick one yourself.

- Preserve source provenance, uncertainty, and historical qualifications.
- Research informs design, and the repository a decision concerns records it. Don't edit another repository's documentation from here.
- Write each Markdown paragraph on one line.

## Commits and pull requests

- Branch first, as `research/r-N-<slug>`. Every change lands through a pull request.
- Use Conventional Commits and a plain `git commit`, without `Signed-off-by` or `Co-authored-by`, and fill every section of `.github/PULL_REQUEST_TEMPLATE.md`.

## Checks

Run `mise install` and `bazelisk run //:bazel_env`, which builds the `.bazel_env/bin` shims the git hooks call, then `prek install`. Every gate is a Bazel test from tbhb-dev/rules, which `bazelisk test //...` runs, and `bazelisk run //:format` rewrites files into their canonical format. The pre-commit hooks run the same gates. To build against a local rules clone, put `common --override_module=tbhb_rules=<path to a rules clone>` in `.bazelrc.user`.
