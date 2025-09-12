# AGENTS

This repository provides an Ansible collection for Cisco Small Business switches. Follow these guidelines when contributing.

## Repository layout
- Place the collection inside `ansible_collections/community/ciscosmb` when developing so `ansible-test` can locate the source tree.
- Add changelog fragments for user visible changes under `changelogs/fragments` using the `.keep` template as a starting point.

## Development environment
- Use Python 3.6-3.12 in a virtual environment.
- Install dependencies:
  ```bash
  pip install ansible
  pip install -r requirements-dev.txt
  pip install -r tests/unit/requirements.txt
  ```

## Testing
Run the test suite before committing:
```bash
ansible-test sanity --docker  # use --local if Docker is not available
ansible-test units  --docker  # use the same METHOD and optional PY flags
```
These commands are described in the README's testing section and ensure that sanity checks and unit tests pass.

## Release
For releases, update version in `galaxy.yml`, create changelog fragments, and regenerate `CHANGELOG.rst` using `antsibull-changelog`.

