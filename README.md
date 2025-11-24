# Github action to export environment variables
Github Actions only has a fairly limited support for environment specific workflow variables. You can configure them as secrets but these are not versioned and also masked in the workflow logs. 

This Github Action aims to provide a simple implementation for using environment variables in workflows.

> **Warning**
> Do not put secrets such as passwords or access tokens in the environment file. You should keep these as secrets in Github or, even better, in the application keyvault of your landing zone.


## Contributors
* Owner Me (Amine)
* Contributors - feel free.
## Parameters
The following parameters are supported:

| Parameter | Required | Description |
|-----------|----------|-------------|
| environment-name | Yes | An environment name that matches an `<environment-name>.env` file in the `environment-file-path` folder. Usually this name matches the [Github Environment](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment) you are deploying to. |
| environment-file-path | No | Directory containing the environment files. Defaults to `.github/workflows/env` |

## Usage
In your repo, create `<environment-name>.env` files per environment in `.github/workflows/env` directory, e.g.:

- `prod.env`
- `nonprod.env`


Each env file must contain the NON SECRET variables you want to export on separate lines, e.g.:
