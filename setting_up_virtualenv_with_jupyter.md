# Getting 
> Additional information or tagline

### Create new virtual environment

```shell
python3 -m venv <environment_name>
```

### Activate virtual environment

```shell
<environment_name>/bin/activate
```
where  `environment_name` is the name that you specify

### Install IPythonKernel

```shell
pip3 install ipykernel
```

### Point JupyterHub to new environment

Make new directory called kernels in `/home/<username>/.local/share/jupyter`

```shell
mkdir /home/<username>/.local/share/jupyter/kernel
```
Create new file called in `/home/<username>/.local/share/jupyter/kernel` called `kernel.json`

```shell
vi /home/<username>/.local/share/jupyter/kernel/kernel.json
```

Then copy/paste the following code replacing `username` and `environment_name`

```shell
{
"argv": [
  "/home/<username>/<environment_name>/bin/python",
  "-m",
  "ipykernel_launcher",
  "-f",
  "{connection_file}"
],
"display_name": "<environment_name>",
"language": "python"
}
```
Save the file `:w!` then quit `:q!`

# Reload JupyterHub
