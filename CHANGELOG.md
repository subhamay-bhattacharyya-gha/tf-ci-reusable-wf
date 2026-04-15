# [1.2.0](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/compare/v1.1.0...v1.2.0) (2026-04-15)


### Bug Fixes

* pass TF_TOKEN_app_terraform_io to Export Plan step for HCP backend auth ([99737f1](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/99737f18af068a2e497182ee2c8cc6e4a01bd1b5))


### Features

* add Checkov report summarization step to CI workflow ([173fafe](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/173fafe6820ebc738524d4d6099f734e08582df0))
* add environment variable to enforce Node.js version for JavaScript actions ([24079bf](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/24079bf8fc67b5a3a3818241177cd6c64eb669b8))
* add iac-framework input to Checkov scan job for Terraform plan ([0ef3a93](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/0ef3a93aae08cd773c8a2406537c9e158d7dde65))
* add placeholder jobs for YOR tagging and Checkov scan in CI workflow ([ad30834](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/ad30834ba02ba38094dc23f25edcda1e7b9e07c5))
* add security-events permission for Checkov scan job ([211b8c3](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/211b8c3963b77ce35712d6043d62ac3375163d42))
* add security-events permission for Checkov scan job ([7194dc3](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/7194dc38cb2ebb4f4a53db7ea4c94bc5c29df5a1))
* enhance CI workflow with environment input and update README for variable usage ([b734ef9](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/b734ef9f5fe39e90e2a4eae345e61c338da32cc6))
* export Git context as environment variables for Terraform ([e393b77](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/e393b77dbbdd898039dd75838a406884a09bd69b))
* implement Checkov scan in CI workflow ([b5a13ca](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/b5a13ca87ac1a9e47a854b6609b92fdc6de3c977))
* implement YOR tagging step in Checkov scan job ([3390a96](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/3390a9629591c3e5e809361e61993097b50c134a))
* remove release-tag input from Checkov scan job ([073f7ab](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/073f7ab599031bcf34535e4e6f25c31a93d18655))
* remove YOR tagging step from CI workflow ([9b3b3c5](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/9b3b3c5d434876826bff07efaf8d6e3c66aebb4d))
* restructure Checkov scan job to include Terraform plan export and download steps ([020da09](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/020da09742bc86ecfee4b0c2422919b524648c55))
* update Checkov scan action to use dynamic release tag ([dfb9269](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/dfb92698192199f02d36d9232de4430cc948f32a))
* update Checkov scan action to use the main branch ([5f05d0e](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/5f05d0e072dd90246038fea93d47bec2640d4eae))
* update Checkov scan job to use dynamic release tag from GitHub reference ([6d12598](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/6d12598fc00410f6e86dcce15c3f6c5d858427f1))
* update Checkov scan job to use latest versions of upload and download artifact actions ([0a15c3d](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/0a15c3d3a399d3c076cc68fd5eadb08391d81497))
* update Checkov scan job to use plan file path instead of IAC framework ([e68c2a0](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/e68c2a0d109c6a13a6507ca91cdb0a20870a92ee))
* update CODEOWNERS to reflect new team ownership ([4053a18](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/4053a1861330838ede65fa361b0db6ffee0773e2))
* update download-artifact action to version 8 in Checkov scan job ([9d6d375](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/9d6d3750be9e06b1d1adb7081ed118b83dbcfe29))
* update iac-dir path to use dynamic cloud provider in Checkov scan job ([75412a0](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/75412a05615fc3cebcdd9e73da27df827b017a27))
* update Terraform Plan action to use feature branch for plan summary ([af025e3](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/af025e3a9e93c7f860cf11b6dcf5a210cbf4edde))
* update Terraform Plan action to use specific version and remove JSON export step ([50e22d9](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/50e22d9bd2eb11166cdf6fe80178cc3ead522afe))
* update tf-plan-action to use the main branch and enhance Code of Conduct for inclusivity ([71c9493](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/71c949358dc807bf984eca1e81cb8a2367df3198))
* update tf-validate-action to use a specific feature branch ([9a9c928](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/9a9c92898ad52d8ac728da3a450c6f1ab0cffb0c))
* update tf-validate-action to use the main branch ([2b7a064](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/2b7a064ec58db2722ce2136723eaf62a0012156c))

# [1.1.0](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/compare/v1.0.3...v1.1.0) (2026-02-26)


### Features

* add S3 backend inputs and enhance validation ([adcdfa7](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/adcdfa798c40abbdfd5027da20cfe7ff988c4fd9))
* update tf-plan-action to feature branch for platform support ([a9c2764](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/a9c27641cf120e3cfbc67cd12dc0ae0edb7cc170))

## [1.0.3](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/compare/v1.0.2...v1.0.3) (2026-01-23)


### Bug Fixes

* update terraform plan action to use main branch ([06b0131](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/06b01316fd286768bee7cbed1e741d0bf114e12b))

## [1.0.2](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/compare/v1.0.1...v1.0.2) (2026-01-08)


### Bug Fixes

* update Node.js version and correct package name in package-lock.json ([1982e9b](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/1982e9b68f7df4dffbd769049c5d1052dd7ac32e))

## [1.0.1](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/compare/v1.0.0...v1.0.1) (2025-07-11)


### Bug Fixes

* add environment input to check-environments job ([cc7cf0a](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/cc7cf0a4295f186b3646160473f439a8987f9aad))
* add org-short-name and region inputs to check-environments-action ([6411451](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/641145160c6b036f71af01aa77d93c4ec7a1ddfc))
* update action branches in CI workflow to correct references ([7f7bb54](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/7f7bb544eb8365af5c13612815d9f00a110277b7))
* update branch-issue-action to use feature/GHA-0008-rename-environments ([93eb2ce](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/93eb2ceef117cbea75eb50b31fb45849a4e4b096))
* update check-environments-action to use main branch ([587d161](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/587d161a548b062932b783f787bbca7f252972b0))
* update check-environments-action to use main branch ([6ea39c0](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/6ea39c0ca1dfb940ba4e197bbdc375223cea6a6a))
* update check-environments-action to use specific commit hash ([2b01bd9](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/2b01bd9f99d5a95429314d7c3aacafacf321300d))
* update check-environments-action to use variables for org and region ([82af0bd](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/82af0bd3a28af3ee1c0e41f7f059a39996dab221))
* update check-environments-action to use version v1.1.0 ([c1b47c3](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/c1b47c336e05ed41c640e6fa33448711956a569e))
* update S3 bucket variable name and change create-pull-request to create-release step ([6f0f067](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/6f0f0679f5a9a436db6f9214e98e4407ed4ec809))
* update S3 bucket variable name in terraform validate action ([4d90875](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/4d90875b4075d22021aa5e057e0f56da67722da2))

# 1.0.0 (2025-06-20)


### Features

* add reusable Terraform CI/CD workflow and update documentation ([32d4341](https://github.com/subhamay-bhattacharyya-gha/tf-ci-reusable-wf/commit/32d4341bd1d49a890e25110d259f479968d39e73))

# Changelog

All notable changes to this project will be documented in this file.
