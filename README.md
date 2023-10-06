# CodeQL Wrapper Action

This action provides a mechanism for a centrally manageable and configurable wrapper around the CodeQL `init` and `analyze` actions. The use-case this action was originally created to address was automatic extraction and use of `default-codeql-config.yml` code scanning configuration files embedded in custom CodeQL bundles created by the [CodeQL Bundle Action](https://github.com/advanced-security/codeql-bundle-action). As such, running this wrapper action will fail if this configuration file does not exist in the specified bundle.

## License

This project is released under the [MIT License](LICENSE).

The underlying CodeQL CLI, used by the CodeQL Action this wrapper action encapsulates, is licensed under the [GitHub CodeQL Terms and Conditions](https://securitylab.github.com/tools/codeql/license). As such, this action may be used on open source projects hosted on GitHub, and on private repositories that are owned by an organisation with GitHub Advanced Security enabled.

## Usage

This action is designed to be used as a drop-in wrapper compatible with the default `init` and `analyze` actions provided by the [CodeQL Action](https://github.com/github/codeql-action). The `init` action provided by this wrapper action is a drop-in replacement for the default `init` action, and the `analyze` action provided by this wrapper action is a drop-in replacement for the default `analyze` action.

This wrapper is designed to be forked/copied to a centrally managed repository within an organization. Centrally managed customizations (such as specifying a tools URL or custom CodeQL action repository) or pre-/post-steps can then be added by modifying the the `init` and `analyze` actions provided by this wrapper.
