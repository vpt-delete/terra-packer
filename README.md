# terra-packer

A simple docker container including terraform, packer and aws-cli

[![Build Status](https://api.travis-ci.org/pfandie/terra-packer.svg?branch=master)](https://travis-ci.org/pfandie/terra-packer)

<img src="https://cdn.rawgit.com/hashicorp/terraform-website/master/content/source/assets/images/logo-hashicorp.svg" width="150x">

## Usage

This container helps in e.g. GitLab-CI Omnibus installation.
The Terra-Packer extends the hashicorp/terraform Docker Image with aws-cli and packer.

It could be used to help you creating AMI with GitLab-CI.

## Example

Just extend your .gitlab-ci.yml to make use of this Image

```bash
build_task:
  stage: build
  image: REPOSITORY-URL/terra-packer:latest
  only:
    refs:
      - master
  script:
    - ansible --version
    - ansible-lint --version
    - aws --version
    - packer -v
    - terraform -v
    - terraform-compliance --version
```

## Featured Tools

* ansible
* ansible-lint
* aws-cli
* packer
* shellcheck
* terrafom
* terraform-compliance
