# 33657

[![CircleCI](https://dl.circleci.com/status-badge/img/gh/yanns/circleci-executors/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/yanns/circleci-executors/tree/main)

## Current behavior

When using yaml aliases, no pull requests are opened to update the docker image used for the CircleCI executor.

```
aliases:
  - &working_directory ~/circleci-executors

executors:
  rust-docker:
    docker:
      - image: cimg/rust:1.82.0
    working_directory: *working_directory
```

(version 1.82.0 is outdated: https://circleci.com/developer/images/image/cimg/rust)

## Expected behavior

A pull request should be opened to update the docker image used for the CircleCI executor.

```
aliases:
  - &working_directory ~/circleci-executors

executors:
  rust-docker:
    docker:
      - image: cimg/rust:1.84.1
    working_directory: *working_directory
```

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/33657
