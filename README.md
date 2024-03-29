<div align="center">

# Setup Plone

[![Action on GH marketplace][marketplace badge]][marketplace] &nbsp;
[![GitHub release][release badge]][latest release] &nbsp;
[![GitHub][LICENSE badge]][LICENSE]

This action set up [Plone](https://plone.org "Plone CMS") and [Python](https://python.org "Python") within a Github workflow to be used in tests.

</div>

## Inputs

### `python-version`

**Required** Python version to be used.

Default value: `3.8`.

### `plone-version`

**Required** Plone version to be used.

Default value: `5.2`.

### `setuptools-version`

**Required** Setupttols version to be used.

Default value: `65.5.0`.

### `additional-eggs`

Additional eggs to be installed. This is useful to pin versions of packages listed on contraints.txt. i.e.: `plone.restapi>=8.13.0`.

Default value: ``.

## Usage

### Setup Plone

Add the a workflow file in your repository: `.github/workflows/test.yml`.

```yml
- name: Setup Plone 6.0.0a1 with Python 3.8
  uses: plone/setup-plone@v1.0.0
  with:
    python-version: '3.8'
    plone-version: '6.0.0a1'

- name: Install addon package, in editable mode, with pip
  run: |
    pip install -e ".[test]" --use-deprecated legacy-resolver

- name: Run tests (located inside src)
  run: |
    zope-testrunner --auto-color --auto-progress --test-path src/
```

## Changes

### v1.2.0 (2022-11-23)

* Add support for `setuptools-version` option [ericof]

### v1.1.0 (2021-11-10)

* Add support for `additional-eggs` option [ericof]

### v1.0.0 (2021-10-29)

* Initial release of plone/setup-plone [ericof]


## About

[Plone CMS](https://plone.org/ "Plone") is the ultimate enterprise CMS.

### Follow us

[![plone on twitter][twitter badge]][twitter]

[twitter badge]: https://img.shields.io/twitter/follow/plone.svg?style=social
[twitter]: https://twitter.com/intent/follow?screen_name=plone
[marketplace badge]: https://img.shields.io/badge/GitHub-Marketplace-lightblue.svg
[marketplace]: https://github.com/marketplace/actions/setup-plone-python
[LICENSE badge]: https://img.shields.io/github/license/plone/setup-plone.svg
[LICENSE]: https://github.com/plone/setup-plone/blob/master/LICENSE
[release badge]: https://img.shields.io/github/release/plone/setup-plone.svg
[latest release]: https://github.com/plone/setup-plone/releases/latest
[star badge]: https://img.shields.io/github/stars/plone/setup-plone.svg?style=social
[star]: https://github.com/plone/setup-plone
[gh profile]: https://github.com/plone
