# Renovate Workflow

This repository contains a GitHub Actions workflow for using [Renovate](https://renovatebot.com/) to easily update dependencies within your organization. The setup is simple and straightforward, making it easy to keep your dependencies up-to-date and secure.

## Usage

The workflow can be triggered in two ways:
1. On demand, by manually dispatching the workflow and specifying the desired log level.
2. On a schedule, by configuring a cron schedule.

## Inputs

The workflow has the following input:

- `logLevel`: Renovate log levels are used to control the amount of detail that is output in the Renovate log files. Log levels range from fatal (no detail) to debug (most detail).

## Workflow Configuration

The workflow is defined in the `main.yml` file and contains the following steps:
1. Checkout: checkouts the repository to the runner.
2. Request a Github token: request a Github token using `jwenz723/github-app-installation-token@v0.0.4` action.
3. Self-hosted Renovate: runs the renovate using `renovatebot/github-action@v34.82.0` action.

## Secrets

The following secrets are required to be added to the repository for the workflow to run correctly:
- `APP_ID`
- `CLIENT_ID`
- `CLIENT_SECRET`
- `INSTALLATION_ID`
- `PRIVATE_KEY`

## Note

It is mandatory to have `renovate.json` file in the root of the repository with the configuration required by renovate.

## Additional resources

- [Renovate Documentation](https://renovatebot.com/docs)
- [GitHub Actions](https://docs.github.com/en/actions)
- [jwenz723/github-app-installation-token](https://github.com/jwenz723/github-app-installation-token)
- [renovatebot/github-action](https://github.com/renovatebot/github-action)

You can use this as a template and customize according to your or organization use case.
