## Description

<!-- What does this pull request change, and why? Link related issues (e.g. "Closes #123"). -->

## Impact on calling repositories

<!--
Every repository of the organization calls these workflows. Tick one box, and describe what callers must change, if anything.
-->

- [ ] No impact: callers only need to bump to the new release.
- [ ] Breaking change: a workflow or job was renamed (required status checks in `platform-management` must be updated), or `inputs` / `secrets` were added, renamed or made required.

## AI usage

<!--
AI contributions are welcome but must be explicit. See CONTRIBUTING.md.
Tick one box. If AI was used, say which model(s) and tool(s), and what for.
-->

- [ ] No AI was used for this pull request.
- [ ] AI was used, and every commit containing AI-produced work ends with a `Co-Authored-By:` trailer naming it.

<!-- Model(s), tool(s) and what they were used for: -->

## Checklist

- [ ] I have reviewed, understood and tested every change in this pull request, and I take responsibility for it.
- [ ] `yamllint .` passes locally.
- [ ] Every third-party action is pinned to a full commit SHA, followed by its version as a comment.
- [ ] `permissions` are kept to the minimum needed, and `actions/checkout` keeps `persist-credentials: false`.
- [ ] `README.md` documents any new or changed workflow.
