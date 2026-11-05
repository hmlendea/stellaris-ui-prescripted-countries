# Documentation Maintenance

## Maintenance Principles

- Documentation lives in `docs/` and mirrors repository structure.
- Every code/data change requires corresponding doc update.
- Docs are reviewed in PRs alongside code changes.
- Outdated docs are treated as bugs.

## Update Triggers

| Trigger | Required Doc Updates |
|---------|---------------------|
| New empire added | Country definitions, data model, repository structure, invariants, quick start |
| Empire modified | Country definitions, data model, change guide |
| Empire removed | Country definitions, data model, repository structure, invariants, change guide (MAJOR) |
| Localisation changed | Localisation, data model, FAQ |
| Stellaris version updated | Mod descriptor, architecture, change guide, testing |
| Dependency updated | Dependencies, integrations, change guide |
| Bug fix | Troubleshooting, error handling, FAQ |

## Review Checklist

- [ ] All cross-references valid (no broken links)
- [ ] Version numbers consistent across docs
- [ ] Code/file examples match current repository
- [ ] Mermaid diagrams render correctly
- [ ] Tables complete and accurate
- [ ] No stale "TODO" or "FIXME" comments
- [ ] Related documentation links updated

## Versioning

Documentation version tracks mod version. No separate versioning.

## Tools

- Markdown linting: `markdownlint` (recommended)
- Link checking: `markdown-link-check` (recommended)
- Mermaid preview: VS Code Markdown Preview Mermaid Support

## Contribution

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for doc contribution guidelines.

## Related Documentation

- [Change guide](../change-guide.md)
- [Repository structure](../repository-structure.md)
- [Architecture](../architecture.md)