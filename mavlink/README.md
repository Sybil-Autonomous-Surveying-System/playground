# Getting Started with Mavlink

## For the standard dialect:

```bash
pip install pymavlink
```

## To get started on creating our own dialect:

Commands to be executed from this directory (`[root of repo]/mavlink`) on debian based linux distro (I'm doing it in WSL on Windows).

Based on the [getting started guide](https://mavlink.io/en/getting_started/):

1. Install Python 3.3+
1. Create and activate a new virtual environment.

    ```bash
    python3 -m venv mavlink-env
    source mavlink-env/bin/activate
    ```

1. Install dependencies.

    ```bash
    pip3 install -r requirements.txt
    ```

1. Clone our fork of the [mavlink repo](https://github.com/Sybil-Autonomous-Surveying-System/mavlink).

   ```bash
   git clone https://github.com/Sybil-Autonomous-Surveying-System/mavlink.git --recursive
   ```

1. Set `PYTHONPATH` to the root of the repo you cloned in the previous step.

    ```bash
    PYTHONPATH=$(pwd)/mavlink
    ```

1. Generate the `common` dialect.

    ```bash
    python3 -m pymavlink.tools.mavgen --lang=Python --wire-protocol=2.0 --output=generated/mavlink_common mavlink/message_definitions/v1.0/common.xml
    ```
