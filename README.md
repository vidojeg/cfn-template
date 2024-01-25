# Cloudformation Templates

Deploy multiple Cloudformation stacks simultaneously.

## Template style

Each stack must contain the same folder structure:

```
stack-name
├── dev-parameters.json
├── prod-parameters.json
├── stage-parameters.json
└── template.yaml
```

The parameter file must follow this structure:
```
[
    {
        "ParameterKey": "",
        "ParameterValue": ""
    }
]
```

For the deployment procedure use a promotion. To deploy on dev/stage/prod you must create PR to that branch and then merge it after review.

> NOTE: **Be aware of branch naming, because the same naming is used for the env variable!!!**

In addition to lint and template validation, security scans like **checkov** and **trivy** will break a CI when it finds CRITICAL, HIGH, or MEDIUM vulnerabilities.
