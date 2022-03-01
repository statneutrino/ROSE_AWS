# ROSE

## Risk of Supply Events model repository for SEW or ROSE

### Installation Prerequisites

1. Download COIN-OR optimiser from the following link: https://www.coin-or.org/download/binary/CoinAll/COIN-OR-1.7.4-win32-msvc11.zip
2. Extract the files and save them somewhere on your local machine
3. Within the extracted files, find the folder path: *COIN-OR-1.7.4-win32-msvc11\COIN-OR\win32-msvc11\bin*. Add this folder to the systems path environment variable.
4. Install miniconda for Windows - you can do this at https://conda.io/miniconda.html
5. Can also be used with Gurobi

### Installing Python Dependencies

1. unzip `packages.zip` (contained within folder)
2. Run `pip install --no-index --find-links file:///[absolute/path/to/rose/packages] -r requirements.txt`
    [absolute/path/to/rose/packages] -> This bit needs to change
3. Successfully deployed in SEW laptop in Oct 2019


### Generating Python Packages ZIP

To generate the file used in the command above, use the `make_package.py` script, as below.

    poetry run python make_package.py

This will:

* Download all files that pass the `ONLY_ACCEPT` filter (this is to avoid massive wheels).
* Create a PEP 503 compliant ZIP archive called `packages.zip` based on the latest poetry lock file, found in `poetry.lock`. You can then use this file in the command as above.
* Alter `requirements.txt` to contain the list of the above.

N.B. - you will need to do this on an internet connected machine, then transfer the file to wherever.
