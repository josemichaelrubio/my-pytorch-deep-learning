# Updating & Installing requirements.txt

**NOTE**: since we are running a Conda environment, start will with these steps first: [environment-yml_cheatsheet.md](enironment-yml_cheatsheet.md).

Remember to back up your current environment before performing these operations, especially if you’re working on critical projects. This way, you can restore your environment if needed.

## Creating/ Updatng requirements.txt

Using conda: If you’re using Conda as your package manager, you can list your dependencies with:

    conda list -e > requirements.txt

## Installing Dependencies from requirements.txt

To use a requirements.txt file to reinstall dependencies in your Python environment, you can follow these steps:

1. Open your terminal or command prompt and navigate to the directory where your requirements.txt file is located.
2. Activate your virtual environment if you are using one. This ensures that the dependencies are installed in the correct environment.
3. Run the following command to reinstall all the dependencies listed in your requirements.txt file:

        pip install -r requirements.txt

    * This command will install the exact versions of the packages listed in your requirements.txt file.
4. If you want to upgrade packages to their latest versions while installing, you can use the --upgrade flag:

        pip install --upgrade -r requirements.txt

    * This will upgrade all the packages to the latest versions available, while still respecting the version constraints specified in your requirements.txt file.
5. For packages installed from a VCS (like GitHub), if you’ve made changes and pushed them to the repository, you might need to force reinstall to get the latest version. You can do this by adding the `--force-reinstall` flag:

        pip install --upgrade --force-reinstall -r requirements.txt`

    * This will force pip to reinstall the packages even if they are already installed in the environment1.
