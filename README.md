# ansible-role-rhacm

This Ansible role deploys `Red Hat Advanced Cluster Management for Kubernetes` operator.

## Requirements

* [Check Red Hat OpenShift Container Platform Compatibility](https://access.redhat.com/support/policy/updates/advanced-cluster-management)

## Role Variables

* `install.yml`

| Variable          | Description                                                          | Default                   |
|-------------------|----------------------------------------------------------------------|---------------------------|
| `rhacm_namespace` | Set the target namespace where the operator will be installed.       | `open-cluster-management` |
| `rhacm_channel`   | Set the subscription channel for the operator (e.g., `release-2.15`) | ''                        |
| `rhacm_version`   | Set the specific operator version to be deployed (e.g., `2.15.1`)    | ''                        |

* `configure.yml`

| Variable                | Description                                                                    | Default    |
|-------------------------|--------------------------------------------------------------------------------|------------|
| `rhacm_install_profile` | Set the deployment type (e.g., `minimal` for lab or `standard` for production) | `standard` |

* `uninstall.yml`

| Variable                     | Description                                                                | Default                           |
|------------------------------|----------------------------------------------------------------------------|-----------------------------------|
| `rhacm_namespaces_to_delete` | Set the list of namespaces to be deleted during the uninstallation process | `[open-cluster-management, hive]` |

## Getting Started

For detailed installation steps, please refer to the **[usage guide](USAGE.md)**.

## Development

Interested in the roadmap? Check the **[to-do list](TODO.md)**.

## License

This project is [MIT](LICENSE) licensed.
