# RapiDAST

![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/redhatproductsecurity/rapidast/run-tests.yml?branch=development&logo=github&label=CI) ![GitHub License](https://img.shields.io/github/license/redhatproductsecurity/rapidast)

RapiDAST (Rapid DAST) is an open-source security testing tool that automates DAST ([Dynamic Application Security Testing](https://owasp.org/www-project-devsecops-guideline/latest/02b-Dynamic-Application-Security-Testing)) and streamlines the integration of security testing into development workflows. It is designed to help Developers and/or QA engineers rapidly and effectively identify low-hanging security vulnerabilities in your applications, ideally in CI/CD pipelines. RapiDAST is for organizations implementing DevSecOps with a shift-left approach.

RapiDAST provides:

- Automated HTTP/API security scanning leveraging ZAP
- Automated LLM AI scanning leveraging Garak
- Kubernetes operator scanning leveraging OOBTKUBE
- Automated vulnerability scanning using Nessus (requires a Nessus instance)
- Command-line execution with yaml configuration, suitable for integration in [CI/CD pipelines](./examples/)
- Ability to run automated DAST scanning with pre-built or custom container images
- HTML, JSON and XML report generation
- Integration with Google Cloud Storage and [OWASP DefectDojo](https://owasp.org/www-project-defectdojo/)

RapiDAST is for testing purposes, and should not be used on production systems.

## Deprecation Notice

**Podman Mode Deprecation**
The `podman` [execution environment](./docs/README.md#choosing-the-execution-environment) is deprecated and will be removed in version **2.12**

If you are using `podman` fpr the `container.type` option, please migrate to `none` before updating to version 2.12.

## Quickstart

1. Create a minimal config file for the target application, see [Configuration](#configuration) section for details
2. Run RapiDAST with the config file in a container

```sh
$ podman run -v ./config.yaml:/opt/rapidast/config/config.yaml:Z quay.io/redhatproductsecurity/rapidast:latest
```

## Documentation

See the [User Guide](https://redhatproductsecurity.github.io/rapidast/) for more information.

RapiDAST is extensible by adding your own scanner.

See the [Developer guide](https://redhatproductsecurity.github.io/rapidast/#/DEVELOPER-GUIDE)

## Contributing

Contribution to the project is more than welcome.

See [CONTRIBUTING.md](./CONTRIBUTING.md)
