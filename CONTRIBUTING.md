# Contributing to OpenFeature

[![Sign-up](https://img.shields.io/static/v1?label=Sign-up&message=for%20news&color=blue)](https://bit.ly/openfeature-signup)
[![a](https://img.shields.io/badge/slack-%40cncf%2Fopenfeature-brightgreen?style=flat&logo=slack)](https://cloud-native.slack.com/archives/C0344AANLA1)
[![Roadmap](https://img.shields.io/static/v1?label=Roadmap&message=public&color=green)](https://github.com/orgs/open-feature/projects/1)
[![Governance](https://img.shields.io/static/v1?label=Governance&message=bootstrap&color=yellow)](https://github.com/open-feature/governance)
[![Code of Conduct](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](https://github.com/open-feature/.github/blob/main/CODE_OF_CONDUCT.md)

## Contacting us

We hold regular meetings which you can see [here](https://github.com/open-feature/community/#meetings-and-events).

We are also present on the `#openfeature` channel in the [CNCF slack](https://slack.cncf.io/).

## Project governance

Project governance is documented [here](https://github.com/open-feature/community/blob/main/governance-charter.md).

## Repository requirements

We recommend repositories in the project adhere to some security and maintenance guidelines. These are _only guidelines_, and may not be applicable or valuable in all instances. They are primarily inspired by recommendations from the [Cloud Native Security Controls Catalog](https://www.cncf.io/blog/2022/06/07/introduction-to-the-cloud-native-security-controls-catalog/). Adherence to these guidelines may be required for 1.0 artifact releases, at the discretion of the [Technical Steering Committee](https://github.com/open-feature/community/blob/main/governance-charter.md#technical-steering-committee-tsc) and maintainers.

| Requirement                     | Recommended solution(s)                                                                                                                   |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| artifact and image signing      | language-specific tools, [cosign][cosign]                                                                                                 |
| automated publishing            | github actions (with permissions applying principle of least privilege), language-specific tools (Maven, nuget, NPM, etc)                 |
| container, base image scanning  | [snyk][snyk], [trivy][trivy]                                                                                                              |
| code ownership                  | branch protection rules\* and CODEOWNERS files                                                                                            |
| dependency analysis             | [snyk][snyk]                                                                                                                              |
| dependency auto-updates         | [Renovate][renovate]\*\*, [Dependabot][dependabot]                                                                                        |
| fuzzing                         | [ClusterFuzzLite][clusterfuzzlite], [OSS-Fuzz][oss-fuzz]                                                                                  |
| SBOM generation                 | [CycloneDX][cyclonedx], [SPDX][spdx], [syft][syft]                                                                                        |
| static analysis                 | [SonarCloud][sonarcloud], language-specific tools (SpotBugs, eslint)                                                                      |
| unit, integration testing       | github actions (with permissions applying principle of least privilege), language-specific tools (JUnit, Jest, etc), [Cucumber][cucumber] |
| semantic versioning, changelogs | [Semantic Versioning][semantic-versioning], [Conventional Commits][conventional-commits], [Release Please][release-please]\*\*\*          |
| helpful readme file             | See [example README.md](./templates/READMEs/README.md)                                                                                    |

\* Branch protection rules should protect the primary branch (usually `main`) by requiring code review from the appropriate parties (other than the author), usually expressed in a CODEOWNERS file.

\*\* We recommend Renovate over Dependabot because of it's group and auto-merge features.
Additionally, we have an org-wide base config for Renovate.

\*\*\* Release Please isn't strictly necessary, but combined with [Conventional Commits][conventional-commits], it provides a simple yet robust means of generating useful, accurate changelogs and releasing semantically versioned artifacts.

[sonarcloud]: https://www.sonarsource.com/products/sonarcloud/
[snyk]: https://snyk.io/
[trivy]: https://github.com/aquasecurity/trivy
[cosign]: https://github.com/sigstore/cosign-installer
[cyclonedx]: https://cyclonedx.org/tool-center/
[clusterfuzzlite]: https://google.github.io/clusterfuzzlite/
[oss-fuzz]: https://github.com/google/oss-fuzz
[cucumber]: https://cucumber.io/tools/cucumber-open/
[renovate]: https://github.com/apps/renovate
[syft]: https://github.com/anchore/syft
[spdx]: https://spdx.dev/resources/tools/
[dependabot]: https://github.com/dependabot

[conventional-commits]: [https://www.conventionalcommits.org/]
[semantic-versioning]: [https://semver.org/]
[release-please]: [https://github.com/googleapis/release-please]
