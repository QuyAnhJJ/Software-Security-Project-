# Software-Security-Project-
1.Slither
How to install
Note
Slither requires Python 3.8+. If you're not going to use one of the supported compilation frameworks, you need solc, the Solidity compiler; we recommend using solc-select to conveniently switch between solc versions.

Using Pip
python3 -m pip install slither-analyzer

Using Git
git clone https://github.com/crytic/slither.git && cd slither
python3 -m pip install .

We recommend using a Python virtual environment, as detailed in the Developer Installation Instructions, if you prefer to install Slither via git.

Using Docker
Use the eth-security-toolbox docker image. It includes all of our security tools and every major version of Solidity in a single image. /home/share will be mounted to /share in the container.

docker pull trailofbits/eth-security-toolbox
To share a directory in the container:

docker run -it -v /home/share:/share trailofbits/eth-security-toolbox
Integration
For GitHub action integration, use slither-action.
For pre-commit integration, use (replace $GIT_TAG with real tag)
- repo: https://github.com/crytic/slither
  rev: $GIT_TAG
  hooks:
    - id: slither
To generate a Markdown report, use slither [target] --checklist.
To generate a Markdown with GitHub source code highlighting, use slither [target] --checklist --markdown-root https://github.com/ORG/REPO/blob/COMMIT/ (replace ORG, REPO, COMMIT)

- Usage
Run python -m slither path/to/repo

2.C4udit
Installation
First you need to have the Go toolchain installed. You can find instruction here.

Then install c4udit with:

$ go install github.com/byterocket/c4udit@latest
Usage 
Run c4udit path/to/file 

3.Mythril
Installation and setup
Get it with Docker:

$ docker pull mythril/myth
Install from Pypi (Python 3.7-3.10):

$ pip3 install mythril
See the docs for more detailed instructions.

Usage
Run myth analyze path/to/file 
