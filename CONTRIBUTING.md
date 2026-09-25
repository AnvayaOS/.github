# Contributing to AnvayaOS community defaults

Thank you for your interest in ANVAYA OS. This repository contains
the ANVAYA OS organisation profile and the default community files used by every repository that does not provide its own. It is part of the [AnvayaOS organisation](https://github.com/AnvayaOS).

## Code of Conduct

Everyone taking part is expected to follow the
[Code of Conduct](CODE_OF_CONDUCT.md). Report concerns to info@anvaya.dev.

## Before you start

- For changes to the design of ANVAYA OS, open or discuss an RFC in the
  [rfcs repository](https://github.com/AnvayaOS/rfcs) first.
- Check [anvaya.dev/status](https://anvaya.dev/status) to see what is finished
  and what is not.
- Report security issues privately, as described in [SECURITY.md](SECURITY.md),
  never in a public issue.

## How to contribute

1. Fork the repository and create a branch from `main`.
2. Make a focused change, one topic per pull request.
3. Open a pull request against `main` and describe what changed and why.
4. The maintainer reviews every pull request and is the only person who
   merges into `main`.

## Commits

- Write commit messages in the
  [Conventional Commits](https://www.conventionalcommits.org/) style, for
  example `docs: explain the platform profile`.
- Sign off every commit to certify the
  [Developer Certificate of Origin](https://developercertificate.org/):

  ```
  git commit -s
  ```

  This adds a `Signed-off-by:` line with your name and email.

## Evidence

ANVAYA OS makes no claim it cannot show. If your change affects what the
project says it can do, include the evidence: a test, a boot marker, or a
command that reproduces the result. Keep documentation to what is proven.

## Changelog

Record user-visible changes in [CHANGELOG.md](CHANGELOG.md) under
`[Unreleased]`, using the [Keep a Changelog](https://keepachangelog.com/en/1.1.0/)
headings: Added, Changed, Deprecated, Removed, Fixed and Security.

## Versioning

ANVAYA OS follows [Semantic Versioning 2.0.0](https://semver.org/).
Repositories in the organisation are released together under the nucleus
release version, for example `v1.7.1`. Release candidates use the `-rc.N`
suffix, for example `v1.8.0-rc.1`.

## Licensing of contributions

By contributing, you agree that your contribution is licensed under the same terms as this repository: Apache-2.0 OR MIT, at the user's option.

## Questions

Write to info@anvaya.dev.
