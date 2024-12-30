
# YARA-L Rule Upload Tool

This repository contains scripts to automate the process of uploading YARA-L rules to your SecOps instance.

## Prerequisites

* Python 3.6 or later

## Setup

1. **Clone the repository:**

   ```bash
   git clone [https://github.com/ashnaiku/upload_rules.git](https://github.com/ashnaiku/upload_rules.git)
   ```

2. **Create a Python virtual environment:**

   ```bash
   python -m venv ENV_NAME 
   ```

3. **Activate the virtual environment:**

   ```bash
   # On Linux/macOS:
   source ENV_NAME/bin/activate

   # On Windows:
   ENV_NAME\Scripts\activate
   ```

4. **Install the required Python libraries:**

   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Copy YARA-L rules to a local folder:**

   ```bash
   python3 copy_rules2localfolder.py 
   ```

   This script copies all YARA-L rule files from the [chronicle/detection-rules](https://github.com/chronicle/detection-rules.git) repository to a local folder named `localtmp`. This repository houses a collection of pre-built YARA rules.

2. **Upload YARA-L rules to SecOps:**

   You will need a `<BACKSTORY_CREDENTIALS_FILE>` to run this script. This file can be obtained from the Malachite project.

   **Compare local rules with SecOps rules (dry run):**

   ```bash
   python3 uploadrules.py -c <BACKSTORY_CREDENTIALS_FILE>
   ```

   This command compares the local YARA-L rules with the rules already existing in your SecOps instance. It **does not** upload any files. It is recommended to run this command before actually uploading the rules to identify any potential conflicts or issues.

   **Upload YARA-L rules to SecOps:**

   ```bash
   python3 uploadrules.py -c <BACKSTORY_CREDENTIALS_FILE> -m
   ```

   This command uploads all YARA-L rule files from the `localtmp` folder to your SecOps instance.

3. **Confirmation:**

   After uploading the rules, log in to your SecOps instance and confirm that all the YARA-L rules are present.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request if you have any suggestions or improvements.
```
