# gha-runner
![PyPI - Version](https://img.shields.io/pypi/v/gha-runner)

> [!NOTE]
> **Open-Athena fork of [omsf/gha-runner](https://github.com/omsf/gha-runner).**
> This fork exists to back [Open-Athena/ec2-gha](https://github.com/Open-Athena/ec2-gha),
> which pins `gha_runner @ git+…/Open-Athena/gha-runner.git@v1`. It carries two patches
> not yet upstreamed:
> - **Multiple runners per instance** — `start_runner_instances`/`stop_runner_instances`
>   accept list-valued labels, so `ec2-gha`'s `runners_per_instance > 1` doesn't time out
>   waiting for registration.
> - **`PublicDnsName` logging** — the "Instance(s) ready" launch line includes each
>   instance's public DNS, easing SSH debugging.
>
> The `v1` branch tracks `omsf/gha-runner` merged with these patches (see `rw/upstream-merge`).
> Ideally both land upstream and the fork retires.

A simple library for building infrastructure provisioning GitHub Actions via Docker in Python. This project provides scaffolds for starting and stopping cloud instances and all the required interactions to register with the GitHub API. Additionally, we provide some helper functions for environment variable parsing and GitHub Actions native logging.

Documentation for GHA Runner may be found at: [https://gha-runner.readthedocs.io/en/latest/aws/](https://gha-runner.readthedocs.io/en/latest/aws/)

## Implementations
- [ec2-gha-runner](https://github.com/omsf/ec2-gha-runner) and [stop-aws-gha-runner](https://github.com/omsf/stop-aws-gha-runner) (to see this in action take a look at the example used on [AWS](docs/aws.md))

## Acknowledgements
This action was heavily inspired by the [ec2-github-runner](https://github.com/machulav/ec2-github-runner). This library takes much of its inspiration around architecture from the `ec2-github-runner` itself. Thank you to the authors of that action for providing a solid foundation to build upon.
