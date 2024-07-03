# Update Pip & Upgrade Packages

## 0. Check Compatibility of Package Upgrades

Remember to check the compatibility of your projects with the upgraded packages, as some upgrades might introduce breaking changes. Always ensure you have a backup of your current environment before proceeding with bulk upgrades.

List all outdated packages:

    `pip list --outdated`

It’s also a good practice to perform these upgrades in a virtual environment to avoid affecting other projects or system-wide settings12.

## 1. Update pip

Open terminal to the virtual environment then type this: 

    `python -m pip install --upgrade pip`

## 2. Upgade all packages

Depending on your **pip version**, use the corresponding command:

* ***Older than*** **22.3**:

        `pip list --outdated --format=freeze | grep -v '^-e' | cut -d = -f 1 | xargs -n1 pip install -U`

* ***Newer than or equal*** to **22.3**:

        `pip --disable-pip-version-check list --outdated --format=json | python -c "import json, sys; print('\n'.join([x['name'] for x in json.load(sys.stdin)]))" | xargs -n1 pip install -U`

Reason for split: for pip version 22.3 and after, the `--outdated` and `--format=freeze` options are mutually exclusive, you would use a Python script to parse the JSON output