# ML Project Template
A Cookiecutter template for ML projects inspired by [Cookiecutter Data Science](https://github.com/drivendata/cookiecutter-data-science).


## Requirements to use the cookiecutter template:
 - Python >= 3.5
 - [Cookiecutter Python package](http://cookiecutter.readthedocs.org/en/latest/installation.html) >= 1.4.0: This can be installed with pip by or conda depending on how you manage your Python packages:

```bash
$ pip install cookiecutter
```

or

```bash
$ conda config --add channels conda-forge
$ conda install cookiecutter
```
 
 - dvc >= 0.93 is optional, only if you want to control your data using DVC.


## To start a new project
Just run:
```bash
cookiecutter https://github.com/gazprom-neft/ml_project_template
```

You will be asked for these fields:
| Field                 | Default                                                       |  Description    |
|-----------------------|---------------------------------------------------------------|-----------------|
| project_name          | `Template`                                                    | Verbose project name, used in headings (docs, readme, etc).  |
| repo_name             | `project_name` lowercased with spaces replaced by underscores | Repository name on GitHub (and project's root directory name). |
| include_library       | `no`                                                          | Chose a library to attach as a git submodule. `no` means that no library will be attached. |
| git_config_user_name  | `do_not_set`                                                  | Specify local user name for git. Default is to skip this. |
| git_config_user_email | `do_not_set`                                                  | Specify local user email for git. Default is to skip this. |
| init_DVC              | `yes`                                                         | Select whether you want to initialize DVC in the project. |
| dvc_cache_dir_mode    | `pass` if you selected not to initialize DVC, else `infer`    | Select cache directory for DVC. If `pass`, nothing is done; if `infer`, path is selected as `/data/<repo_name>/.dvc/cache` depending on `include_library`, if `custom`, value from `custom_dvc_cache_dir` is used |
| custom_dvc_cache_dir  | `pass`                                                        | Provide a path to DVC cache directory, if you selected `custom` as `dvc_cache_dir_mode`. |
| lib_dvc_cache_dir_map | `default`                                                     | Just press `Enter` :) This sets some utility values. |


GitHub repositories should be created manually, but automatic GitHub repository creation can be added in future


## The project directory structure

The directory structure of your new project looks like this:

```
.
│
├── datasets                  <- Keep your datasets here.
├── docker_containers
├── notebooks                 <- Development notebooks
├── overview                  <- Notebooks with overview of main results
├── src                       <- Project-specific models and utilities
│   └── Library submodule         <- Libraris to be used as git submodules
├── tests
│
├── utils                     <- extra helper utilities that are not project-specific, ex. cookiecutter template updater
│   ├── .cookiecutter.json
│   ├── src
│   └── update_cookiecutter_template.sh   <- run this script to merge recent changes in cookiecutter template into your project
├── .github                   <- GitHub Actions
│   └── workflows
│       └── status.yml
│       └── build_docs.yml
├── .gitattributes
├── .gitignore
├── .dockerignore
├── pylintrc
├── requirements.txt
└── readme.md                 <- The top-level README for developers using this project.
```

See also:
- [Dataset versioning](../../data_versioning) for linking datasets
- [Model description](../../model_description) for model notebooks
- [Docker container](../../docker_container) for image building and container running scripts.
