# [OSSGadget](https://github.com/microsoft/OSSGadget) Guide

Key Features:

- The only one that supports many popular languages and registries
- High false-positive rate
- Well-designed for developers' home tooling to perform low-level tasks, such as downloading it, performing basic analyses on it, or estimating its health

## Testing Environment

The following testing environment was used:

| **Type**                                                 | **Version**                  |
|----------------------------------------------------------|------------------------------|
| Operating System                                         | Debian GNU/Linux 10 (buster) |
| [Docker](https://docs.docker.com/engine/install/debian/) |                       24.0.2 |

## Installation and Analysis Steps

To run OSSGadget analysis, follow these steps:

1. Clone the OSSGadget repository by executing the following command:
   ```
   git clone https://github.com/microsoft/OSSGadget
   ```
   This will fetch the OSSGadget source code to your local machine.

2. Navigate to the OSSGadget directory:
   ```
   cd /path/to/OSSGadget
   ```
   Ensure you are in the correct directory before proceeding.

3. Build the application into a container image:
   ```
   docker build -t ossgadget .
   ```
   This command will create the OSSGadget container image.

4. Mask the `ossgadget` command by creating an alias:
   ```
   alias ossgadget='docker run -v .:/tmp/app --rm ossgadget'
   ```
   This alias allows you to conveniently execute OSSGadget commands.

5. Perform a backdoor detection analysis on the Senginta.py library using the following command:
   ```
   ossgadget oss-detect-backdoor pkg:pypi/senginta
   ```
   You can explore other analysis tools provided by OSSGadget [here](https://github.com/microsoft/OSSGadget#included-tools).

By following these steps, you will be able to install OSSGadget, set up the necessary aliases, and perform various low-level analyses on packages with ease.
