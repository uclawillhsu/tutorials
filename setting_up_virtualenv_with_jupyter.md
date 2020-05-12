# Getting started with a new virtual environment in JupyterHub
> Create a new virtual environment then associate with JuypterHub instance

### Create new virtual environment

```shell
python3 -m venv <environment_name>
```

### Activate virtual environment

```shell
source <environment_name>/bin/activate
```
where  `environment_name` is the name that you specify

### Install IPythonKernel

```shell
pip3 install ipykernel
```

### Point JupyterHub to new environment

Make new directory called `kernels` in `/home/<username>/.local/share/jupyter`

```shell
mkdir /home/<username>/.local/share/jupyter/kernels/<environment_name>
```
Create new file called in `/home/<username>/.local/share/jupyter/kernels/<environment_name>` called `kernel.json`

```shell
vi /home/<username>/.local/share/jupyter/kernels/<environment_name>/kernel.json
```

Then copy/paste the following code replacing `path_to_virtual_environment` with the path to your virtual environment

```shell
{
"argv": [
  "/<path_to_virtual_environment>/bin/python",
  "-m",
  "ipykernel",
  "-f",
  "{connection_file}"
],
"display_name": "<environment_name>",
"language": "python"
}
```
Save the file `:w!` then quit `:q!`

Reload JupyterHub
