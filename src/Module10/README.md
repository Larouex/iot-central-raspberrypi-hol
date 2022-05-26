# IoT Central Device Training
## Module 10 - Connecting to Azure IoT Central (Python SDK)

* Navigate to Module10 directory
* Run the following commands...

```
pip3 install -r requirements.txt
```

# STOP - Instruction Time


* Run the following command...

```
python3 ./iot-central-sample.py
```

### Install the Requirements for the Virtual Environment and Python
**NOTE: This is the steps for Powershell on Windows**

This next set of steps are all executed from the command line and will result in a virtual environment that supports the running of the Saluminator&reg; scripts and modifications, etc.

First, open a powershell terminal in Visual Studio Code and set the powershell execution policy to allow scripts...

```ps1
Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser
```

Next, install the Python Virtual Environment...

```ps1
python -m pip install --user virtualenv
```

Create the virtual environment for the software..

```ps1
python -m venv ./.iotc-venv/dev
```

and then start the virtual environment..

```ps1
.\.iotc-venv\dev\Scripts\Activate.ps1
```

Install the requirements...
```ps1
python -m pip install -r requirements.txt
```

Verify the Environment...
```ps1
cd src
python test-verify-env-dev.py
```

You will see something similar to the output below...
```ps1
(Config) SUCCESS: Loaded the Configuration File (config.json)!
(DeviceCache) SUCCESS: Loaded the Device Cache File (devicecache.json)!
(Secrets) SUCCESS: Loaded the Secrets File (secrets.json)!
```
**NOTE:** You can examine the contents of the various json files by adding the --verbose option to the test-verify-env-dev.py script.

#### BASH INSTRUCTIONS

Open a bash terminal in Visual Studio Code and install the Python Virtual Environment support...

```bash
python -m pip install --user virtualenv
```

Create the virtual environment for the Saluminator&reg; software..

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

Verify the Environment...
```bash
cd src
python test-verify-env-dev.py
```

You will see something similar to the output below...
```ps1
(Config) SUCCESS: Loaded the Configuration File (config.json)!
(DeviceCache) SUCCESS: Loaded the Device Cache File (devicecache.json)!
(Secrets) SUCCESS: Loaded the Secrets File (secrets.json)!
```
**NOTE:** You can examine the contents of the various json files by adding the --verbose option to the test-verify-env-dev.py script.

**Congratulations!** Your system is configured. Next, let's setup the environment on the Raspberry Pi.


## [Module 11 - Device Authentication Types (SaS, Certs, TPM and IR Certs)](../Module11/README.md)