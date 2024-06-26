# Lerna issue example

Issue: Lerna 8 doesn't work if pnpm contains an exclusion in `pnpm-workspace.yaml`. For https://github.com/lerna/lerna/issues/3964

Happens in version 8.0.0+. The latest version 7 is good.

Happens with any exclusion rule, not just the one specified in the repo.

Steps to reproduce:

1. Run `pnpm install`, by default it will install latest version 8.
2. Run `pnpm exec lerna list`, it will report 0 package found.
3. Comment out the exclusion line from `pnpm-workspace.yaml` and run `pnpm exec lerna list` again.
4. It reports 2 packages found.

To validate with lerna 7, run `pnpm install -w lerna@7`, then repeat step 2 to 4 above. In both cases it will report 2 packages found.
