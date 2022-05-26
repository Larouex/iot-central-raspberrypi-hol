# IoT Central Device Training
## Module 10 - Connecting to Azure IoT Central (Python SDK)

* Navigate to Module10 directory
* Open a bash terminal in Visual Studio Code and install the Python Virtual Environment support...

```bash
python -m pip install --user virtualenv
```

Create the virtual environment for the software..

```bash
python -m venv ./.iotc-venv/dev
```

and then start the virtual environment..

```bash
. ./.iotc-venv/dev/bin/activate
```

Install the requirements...
```bash
python -m pip install -r requirements.txt
```

Create our Secrets File

```bash
cp secrets_template.json secrets.json
```

Verify the Environment...
```bash
python test-verify-env-dev.py
```

You will see something similar to the output below...
```ps1
(Config) SUCCESS: Loaded the Configuration File (config.json)!
(DeviceCache) SUCCESS: Loaded the Device Cache File (devicecache.json)!
(Secrets) SUCCESS: Loaded the Secrets File (secrets.json)!
```
**NOTE:** You can examine the contents of the various json files by adding the --verbose option to the test-verify-env-dev.py script.

**Congratulations!** Your Python enviroment on the Raspberry Pi is configured.

# STOP - It's Instruction Time!

Secrets File Overview

Provision Device
```bash
python provisiondevice.py -v -r 1 -n 1
```

## [Module 11 - Device Authentication Types (SaS, Certs, TPM and IR Certs)](../Module11/README.md)