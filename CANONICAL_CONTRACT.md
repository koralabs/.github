# .github canonical contract

## Purpose and authority

I am the organization `.github` repository. I exist only so that `profile/README.md` is shown as the overview page of the GitHub organization. I have no code, no secrets, no deploys and no tests beyond a Markdown lint. If I were removed, only the org landing text would disappear. Ecosystem rules: `../AGENTS.md`. The enclave holds the two policy files and the profile page, because that page is the one public statement made in the organization's name.

## Invariants (must never be violated)

1. The profile page contains no secrets, credentials, private contact details or links that expose non-public systems. Today it holds one link to the internal wiki page; that is a link only, and the wiki itself must stay access-controlled. (No automated check; I read the file.)
2. The profile page makes no claim that is false for the ecosystem: no contract address, price, policy id or promise of behaviour is written there. If one is added it must match the chain and the product docs. (Convention only.)
3. Markdown is valid: heading order, link syntax, no empty links, closed code fences. (`.github/workflows/pr-tests.yml` runs `markdownlint` on `README.md` and `profile/README.md` for every PR and master push.)

## Boundaries and known limits

- The lint disables line-length, first-line-heading, heading-spacing, list-spacing and trailing-space rules, so it checks structure, not content.
- No test or check detects a secret or a wrong fact on the page.
- The page links to a wiki in a separate organization (`adahandle/adahandle-internal`); I do not control its access settings.

## Refactors needed to enforce this

- Add a secret-pattern scan and a link allow-list check to the existing lint workflow.
- None else; the repo is correctly tiny.
