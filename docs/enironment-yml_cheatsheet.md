# environment.yml Cheatsheet

Remember to back up your current environment before performing these operations, especially if you’re working on critical projects. This way, you can restore your environment if needed.

## Why environment.yml

The environment.yml file serves a similar purpose as requirements.txt but is more comprehensive. It can include not only package versions but also channels from which to install them, and it can specify non-Python libraries that may be required.

It’s specific to Conda and can manage packages from languages other than Python.
It can specify the Python version, Conda channels, and even non-Python dependencies, making it more comprehensive.
It’s ideal for projects that require a consistent cross-platform environment or when using packages that have complex dependencies.

## Why requirements.txt

However, if you have a requirements.txt file that includes Python packages not listed in the environment.yml, or if you’re collaborating with others who use pip instead of Conda, you might still need to use it.

It’s a standard for Python packages and is used with pip, which is Python’s package installer.
It’s simple and widely used in the Python community, especially for applications that are exclusively Python without dependencies on external non-Python libraries.
It’s suitable for projects where all contributors use pip and virtual environments.

## Importing Dependcies

1. Open the terminal and `cd` into the directory you wish to have the Conda environment

2. Create a new Conda environment within your current directory:

        conda env create -f /envs/environment.yml

3. Install remaining packages:

        pip install -r requirements.txt

4. Activate virtual environment:

        conda activate .conda

    * Remember to change the environment name `.conda` to the name indicated in the environment.yml file.

## Exporting and Updating the Conda Environment

The purpose to export a Conda environment to a .yml file is for reproducibility, portability, and convience. It ensures that a project runs consistently across different machines and operating systems. It’s a best practice for managing project dependencies in a systematic and maintainable way, thus always having the environment.yml file updated.

To export or update the environment.yml file, we use the same command which will create a new file if it doesnt exist or erase then write over the existing file:

    conda env export > envs/environment.yml

And for the requirements.txt:

    conda list -e > requirements.txt

## Updating Conda and it's packages

First, update Conda itself:

    conda update -n base conda

Then, update all the packages that Conda manages:

    conda update --all

## More documentation on requirement.txt

If you need more info on importing and exporting the requirements.txt file, go here: [Update_Install_requirements-txt.md](Update_Install_requirements-txt.md)
