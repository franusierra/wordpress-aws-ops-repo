# Operations repository

Operations repository for the wordpress practice project.

This repository is a "demo" repository for the operations team that will let the application will be automatically deployed once the pipelines are triggered.

It will contains the definition of the ECS task deployed in each environment. The deployment action will updates the image used in the task definition and updates the task using the new definition.

## Requirements

The minimal requirements for this repository are:

* A proper `.gitignore` file.
* A `Jenkinsfile` file with a _declarative pipeline_ that will deploy the image received as a parameter to **staging** environment for the develop branch and deploy to **production** for the master branch. This pipeline will be triggered from the build pipeline. Use a **multibranch** pipeline.
* A `pre-commit` config file that use _at least_ the following hooks:
  * check-added-large-files
  * check-case-conflict
  * check-executables-have-shebangs
  * check-json
  * check-merge-conflict
  * trailing-whitespace
  * remove-tabs
  * markdownlint
  * shellcheck
  * yamllint
* Avoid the use of cloud environment credentials. Use EC2 instance profile for jenkins to gain the necessary permissions.
* Use `github workflow` to validate pre-commit hooks in the remote repository on pull request and push events.
