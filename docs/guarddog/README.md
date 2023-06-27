# [GuardDog](https://github.com/DataDog/guarddog/) Guide

Key Features:

- Support for versioning files such as requirements.txt and package.json, providing enhanced control and compatibility.
- Low false-positive rate, ensuring accurate identification of potential threats.
- Integration of Semgrep, allowing users to customize and fine-tune analyzer rules according to their needs.
- Seamless integration with continuous integration (CI) tools, facilitating automated security checks.

## Testing Environment

The following testing environment was used:

| **Type**                                                 | **Version**                  |
|----------------------------------------------------------|------------------------------|
| Operating System                                         | Debian GNU/Linux 10 (buster) |
| [Docker](https://docs.docker.com/engine/install/debian/) |                       24.0.2 |

## Installation and Analysis Steps

To run GuardDog analysis, follow these steps:

1. Mask the `guarddog` command by creating an alias:
   ```
   alias guarddog='docker run -v .:/tmp --rm ghcr.io/datadog/guarddog'
   ```
   This alias allows you to execute GuardDog commands conveniently.
   
2. Navigate to the "codebase" directory using the command:
   ```
   cd /path/to/example-malicious-package-detector/codebase/
   ```
   Ensure you are in the correct directory before proceeding with the analysis.

3. Run the analysis using the following command:
   ```
   guarddog pypi verify /tmp/Senginta.py/requirements.txt
   ```
   Note that `/tmp` is used as a path prefix. This is because the current directory is mounted to the `/tmp` directory in the first step.

By following these steps, you will be able to install GuardDog, set up the necessary aliases, and perform third-party package analysis effectively on your codebase.
