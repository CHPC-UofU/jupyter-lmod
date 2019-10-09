# Jupyter Lmod

Jupyter interactive notebook server extension that allows user 
to interact with environment modules before launching kernels.
The extension use Lmod's Python interface to accomplish module
related task like loading, unloading, saving collection, etc.

## requirements

- [jupyter notebook](https://github.com/jupyter/notebook) >= 5.3
- [Lmod](https://github.com/TACC/Lmod) >= 6.0

## CHPC mods

During the pip install the following gets updated: Send2Trash-1.5.0 jupyter-client-5.3.4 jupyter-core-4.6.0 jupyterlmod-1.7.5 notebook-6.0.1 prometheus-client-0.7.1 pyzmq-18.1.0 terminado-0.8.2 tornado-6.0.3

Tornado 6.0.3 breaks the notebook (there's a complaint that a tornado function is missint). Our "fix" was to roll back the updates:
$ pip install tornado==4.5.2 terminado==0.6 jupyter-core==4.3.0 pyzmq==16.0.2 jupyter-client==5.1.0 notebook==5.2.0

and then only update notebook to 5.3.0:
$ pip install notebook==5.3.0

which updates the following: jupyter-client-5.3.4 jupyter-core-4.6.0 notebook-5.3.0 terminado-0.8.2, but tornado stays at the older, unbroken version.

## setup

### install
```
pip install jupyterlmod
```

### jupyterlab

```
jupyter labextension install jupyterlab-lmod
```

## demo

![Jupyter notebook demo](http://i.imgur.com/IP9uUJp.gif)

![JupyterLab demo](https://i.imgur.com/1HDH7iN.gif)
