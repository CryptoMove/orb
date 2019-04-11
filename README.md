# CryptoMove Tholos CircleCI Orb

Import your secrets stored on CryptoMove Tholos and use them for any command
in your CircleCI builds.

## Installation

```yaml
version: 2.1

orbs:
  tholos: cryptomove/tholos@0.0.9

jobs:
  test:
    docker:
      - image: circleci/node
    steps:
      - checkout
      - tholos/install
      - tholos/run_command:
          step-name: Run tests with env vars from CryptoMove Tholos
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
