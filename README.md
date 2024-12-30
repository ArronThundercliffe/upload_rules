Markdown

# YARA-L Rule Upload Tool

This repository contains scripts to automate the process of uploading YARA-L rules to your SecOps instance.

## Prerequisites

* Python 3.6 or later

## Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ashnaiku/upload_rules.git

Create a Python virtual environment:

Bash

python -m venv ENV_NAME 
Activate the virtual environment:

Bash

# On Linux/macOS:
source ENV_NAME/bin/activate

# On Windows:
ENV_NAME\Scripts\activate
Install the required Python libraries:

Bash

pip install -r requirements.txt
Usage
1. Copy YARA-L rules to a local folder
Bash

python3 copy_rules2localfolder.py 
This script copies all YARA-L rule files from the chronicle/detection-rules repository to a local folder named localtmp. This repository houses a collection of pre-built YARA rules.

2. Upload YARA-L rules to SecOps
You will need a <BACKSTORY_CREDENTIALS_FILE> to run this script. This file can be obtained from the Malachite project.

Compare local rules with SecOps rules (dry run):

Bash

python3 uploadrules.py -c <BACKSTORY_CREDENTIALS_FILE>
This command compares the local YARA-L rules with the rules already existing in your SecOps instance. It does not upload any files. It is recommended to run this command before actually uploading the rules to identify any potential conflicts or issues.

Upload YARA-L rules to SecOps:

Bash

python3 uploadrules.py -c <BACKSTORY_CREDENTIALS_FILE> -m
This command uploads all YARA-L rule files from the localtmp folder to your SecOps instance.

3. Confirmation
After uploading the rules, log in to your SecOps instance and confirm that all the YARA-L rules are present.

Contributing
Contributions are welcome! Please open an issue or submit a pull request if you have any suggestions or improvements. 1    
 1. 
github.com
github.com


**Explanation of the README:**

* **Clear Title and Description:** The README starts with a clear title and a brief description of the project's purpose.
* **Prerequisites:** It lists any prerequisites, like Python version, that are needed to use the scripts.
* **Step-by-Step Setup:**  It provides clear and concise instructions on how to set up the environment, including cloning the repository, creating a virtual environment, and installing dependencies.
* **Detailed Usage:** It explains how to use each script with clear commands and explanations of the options (`-c`, `-m`).
* **Links to External Resources:** It links to the `chronicle/detection-rules` repository for easy access.
* **Contribution Guidelines:** It encourages contributions and provides guidance on how to contribute.

This README provides all the necessary information for someone to understand, set up, and use your YARA-L rule upload tool effectively. Remember to replace `your-username` and `your-repo-name` with your actual GitHub username and repository name.
