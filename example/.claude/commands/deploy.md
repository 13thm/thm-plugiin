# /project:deploy

Project deployment command.

## Description

Coordinates the deployment process for the current project.

## Usage

```
/project:deploy [environment]
```

## Parameters

- `environment`: Target environment (dev, staging, prod)
- Defaults to staging if not specified

## Deployment Steps

1. Pre-deployment checks
2. Run tests
3. Build artifacts
4. Deploy to target environment
5. Smoke tests
6. Health check verification

## Examples

```
/project:deploy dev
/project:deploy staging
/project:deploy prod
```

## Notes

- Requires clean working directory
- Prompts for confirmation before prod部署
- Creates deployment rollback plan
