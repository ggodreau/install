- export an environment's requirements into a text file:

`pip freeze > requirements.txt`

- download all tarballs to a `pkgs` directory, given `requirements.txt`, details [here](https://stackoverflow.com/questions/11091623/python-packages-offline-installation)

`pip download -d ./pkgs -r requirements.txt`

- install locally from a requirements file, with no downloading of packages:

`pip install -f ./src -r ./requirements.txt`
