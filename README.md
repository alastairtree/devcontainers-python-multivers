# Devcontainers Python Multiverse

This repo contains a sample vscode developer environment with multiple versions of python installed. Really useful if you use WSL and docker and want a development environment with more than one version of python without cluttering up your WSL install.

This project is based on the [Microsoft Python Devcontainer](https://github.com/devcontainers/images/tree/main/src/python) and adds multiple versions of python to the dev container using Pyenv. Pyenv is then added to the PATH of the dev user `vscode` for both bash and zsh shells.

## Quick start

Install Docker Desktop, VS Code, Dev Containers VSCode Extension

Clone/download the repo into WSL.

From WSL open the repo in code:

```
cd /folder/docker-python-multivers
code .
```

Look at .devcontainer/Dockerfile - you can see all the versions of python configured for install. Customise as you wish.

Use the Command Pallet to reopen in container: CTRL-P > Reopen folder in dev containers (or click the popup if it appears)

(One-off) Wait a while! It takes time to install lots of version of python.

Once it has opened create a new terminal window in vscode in either bash or zsh.

list the versions installed and managed by pyenv:

```
pyenv versions
```

And change versions at will using pyenv:

```
python3 --version 
# Python 3.11.1

pyenv shell 3.8
python3 --version 
# Python 3.8.16

# now we are in a pyenv shell, you can use one of many versions using the python3.X shims that are not available by default:
python3.9 --version 
# Python 3.9.2

# back to defaults
pyenv shell --unset
python3 --version 
# Python 3.11.1
```

## Where is pythonX installed?

You can also see where and what the different versions of python3 are installed into the OS:

```
ls /usr/**bin/python3*
```

And the versions installed by pyenv

```
ls ~/.pyenv/versions
```

`$HOME` is `/home/vscode` by default.