# CryptoMove CircleCI Orb

Import your secrets stored on CryptoMove cryptomove and use them for any command
in your CircleCI builds.

## Installation

```yaml
version: 2.1

orbs:
  cryptomove: cryptomove/cryptomove@0.0.12

jobs:
  test:
    docker:
      - image: circleci/node
    steps:
      - checkout
      - cryptomove/install
      - cryptomove/run_command:
          step-name: Run tests with env vars from CryptoMove cryptomove
          command: yarn test

workflows:
  version: 2
  test:
    jobs:
      - run_test
```

In the example above, we are installing our orb, and invoking the `yarn test`
command with your keys and secret values from CryptoMove sourced as
environment variables.

## Legal

Copyright 2019, CryptoMove Inc. Distributed under the [MIT License](https://opensource.org/licenses/MIT).
