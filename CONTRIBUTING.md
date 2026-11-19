# Contribution guidelines

Thank you for taking the time to contribute!

These guidelines apply to every [Diaoul](https://github.com/Diaoul) repository. A repository may add or
refine rules in its own `CONTRIBUTING.md`; when it does, that file takes precedence over this one.

## AI usage policy

> [!IMPORTANT]
> AI-assisted contributions are welcome if they follow this policy. Contributions that don't, including
> undisclosed AI use, will be closed, and repeated cases may get your account blocked.

I recommend that you write your own issues, pull requests and code. If you use AI, these rules are required:

1. **Use a frontier model at high effort.** Code written or debugged with AI must come from a current
   frontier model (the newest, most capable model from a major AI lab) running at high effort or above.
   Smaller, older and local models, and low or medium effort settings, are not accepted for code: they
   produce changes that look right and aren't, and reviewing those costs more time than they save. Editor
   autocomplete of a line or two is exempt.
2. **Disclose it.** Fill in the AI usage disclosure in the pull request template (or add one to your issue)
   with:
   - the model, e.g. `Claude Opus 5.5`
   - the effort level it ran at, e.g. `high`
   - what it did, e.g. wrote the code, wrote the tests, helped debug, drafted the description

   A disclosure without the model and effort level counts as undisclosed.

3. **Own it.** Review every line before you submit, and be ready to explain any of it when asked. You are
   responsible for the contribution, not the tool.
4. **Report the problem, not the fix.** If AI helped write an issue, the issue describes the problem and
   stops there. Don't propose a fix, patch or code change. Put that effort into debugging instead:
   - exact steps to reproduce, and whether it fails every time or only sometimes
   - expected and actual behavior
   - versions, configuration and environment
   - full logs, errors and stack traces
   - what you ruled out, and how
   - where the behavior breaks (a component, code path or commit found by bisecting), stated as an
     observation, not a remedy

   For feature requests, describe the behavior you want, not how to build it.

   Keep what you observed separate from what you inferred, and label anything you haven't verified. A
   suggested fix pushes whoever picks up the issue, person or model, toward one answer before the problem
   is understood. A clean, well-debugged report lets them work out the fix from the evidence.

Example:

> AI usage disclosure: YES - Claude Opus 5.5 (high effort) wrote the implementation and tests and drafted
> this description. I reviewed and tested the change.

A repository may publish a stricter or more detailed AI policy (e.g. in an `AGENTS.md` file); when it does,
that policy takes precedence.

## Issues

Search the issue tracker first: your problem may already be reported, and the discussion may hold a
workaround.

### Bugs

A bug gets fixed once it can be reproduced, so a report needs a **minimal reproduction**: the smallest
configuration, input or code that shows the problem. Preparing one often reveals the cause on its own. An
issue that can't be reproduced and gets no answer to follow-up questions will be closed.

### Features

Describe the behavior you want and the problem it solves. For a large change, open an issue and agree on
the design before writing code; a small one can go straight to a pull request.

### Security vulnerabilities

Don't open a public issue. Follow the [security policy](https://github.com/Diaoul/.github/blob/main/SECURITY.md).

## Pull requests

- Search open and closed pull requests first, so you don't duplicate work.
- Keep each pull request to one change. Add tests when the repository has them, and make sure CI passes.
- Fill in the pull request template and keep its **Requirements** section.
- Don't rewrite history to tidy the branch: a follow-up commit answering review is normal, and it shows
  what was asked and what changed.

### Title

The title follows [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/), which also drives
the version bump under [Semantic Versioning](https://semver.org/spec/v2.0.0.html):

`<type>[(optional scope)][!]: <description>`

- `feat`: a new feature
- `fix`: a bug fix
- `docs`: documentation only
- `style`: formatting, no change in meaning
- `refactor`: neither a fix nor a feature
- `perf`: a performance improvement
- `test`: adding or correcting tests
- `build`: build system or external dependencies
- `ci`: CI configuration and scripts
- `chore`: anything else that doesn't touch source or tests
- `revert`: reverts a previous commit

Add `!` after the type, on `feat` or `fix` only, when the change is not backwards compatible, e.g.
`fix!: rename deprecated config key`.

Only the pull request title has to follow this format, not individual commits.

---

Adapted from the [home-operations contribution guidelines](https://github.com/home-operations/.github/blob/main/CONTRIBUTING.md)
(Apache-2.0): trimmed for a single maintainer.
