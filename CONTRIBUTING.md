# Contributing Guidelines

Successfully collaborating on common problems is always an edifying experience that increases the desire to do more. 

## Development Environment

Short of having a poetry environment of your own, you can make use of github's codespaces.

Refer to the [README - Getting Started](../README.md#geting-started) for details.

## Pull Requests

### Before Submitting

Some recommendations to help align your contribution and minimise the eventual back and forth on a PR:

* Engage in an issue thread or in the discussion section.
* Actual code in the form of a minimal PR with a `status:do_not_merge` label is a great tool for generating useful dialogue.

### Which Branch?

* If it's a new feature, or bugfix applicable to the latest code, `devel`
* If it's a bugfix that can't be applied to `devel`, but critical for a release, point it at the release branch (e.g. `release/0.6.x`)

If it is a feature or bugfix that you'd like to see backported to one of the release branches, open a parallel PR for that
release branch or mention that you'd like to see it backported in the original PR's description.

### The Pull Request

Be sure to state clearly in the pull request's **description** (this helps expedite review):

* The motivation, i.e. what problem is this solving.
* A concise summary of what was done (and why if relevant).

### Format, Lint, Type-Check and Test

The repository aims to conform to PEP8, please endeavour to do so. CI will get cranky if you don't ;)

Test against at least one of `py38`, `py310`.

```
# Auto-format your code (if using VSCode, install the ufmt extension)
$ poetry run tox -e format

# Style, Format
$ poetry run tox -e check

# Type-Check
$ poetry run mypy38

# Tests
$ poetry run tox -e py38
```

### Documentation

Documentation is auto-generated as part of the PR process, but if you do wish to make changes and check locally:

Generate the docs, view them from `./docs/html` in a browser.

```
# Install dependencies
$ poetry install --with docs

# Build
$ poetry run make -C docs html
```

On doc dependency changes in `pyproject.toml`, export the requirements for ReadTheDocs.

```
$ poetry export -f requirements.txt --with docs -o docs/requirements.txt
```

### Changelog

* Please update the `Forthcoming` section in the [Changelog](Changelog.rst) with your change and a link to your PR.
* The style should be self-explanatory.
* Do not worry about incrementing the version, releases are handled separately.

### Review

Once submitted, a reviewer will be assigned. You do not need to select. If no-one has self-assigned in a reasonable time window,
feel free to append a *friendly bump* comment to your PR.

### Merging

Once the large button has gone `GREEN`, you or the reviewer may merge the pull request.

## Releasing

If you are interested in seeing your changes make it into a release (sooner rather than later), please make the request via a comment in your PR or in an issue.

## Social Conduct

Be prepared to be tickled by noodly appendages and at all times, be froody.
