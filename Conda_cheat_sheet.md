### Conda stuff I never remember

`conda info --envs`         List environments
`conda activate [environment name]` Activate an existing environment
`conda list`  List packages in an environment

#### Using Jupyterlab
* Installation `conda install jupyterlab` (in base environment)
* Linking to a conda environment:
```
$ conda activate cenv
(cenv)$ conda install ipykernel
(cenv)$ ipython kernel install --user --name=<any_name_for_kernel>
(cenv($ conda deactivate
```
* Running jupyterlab:
`jupyter lab`
