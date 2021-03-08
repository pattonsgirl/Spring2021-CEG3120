# Project 3

## Objectives

- Practice good documentation for a growing infrastructure
- Play with creating a CloudFormation

~~Install python linter~~
~~Run linter when commits are made~~
~~Prevent commit if linter does not pass~~

## TODO List:

1. Create a CloudFormation Template that can recreate your environment installation - from the VPC to the two systems we have created so far.

- [Simplified Example Config File](sample-config-file.yml)
- [Example Configuration File](https://github.com/mkijowski/aws-cf-templates/blob/master/course-templates/ceg3400.yml)
- Scope: "configurations" will include software that needs to be installed on the system. Do not deal with configuration files.
- Note: to keep costs down, you will need to delete your Cloud Stack in between build & test

### AWS Educate Quick Link:

- [Sign in to AWS educate](https://www.awseducate.com/signin/SiteLogin)

Extra credit:
Play with AWS Cloud Formation linter
Notes: this package is brand new - I haven't played with it yet either.  Adopting / investigating new tools that can improve workflow is always worthwhile.  Sometimes things are a bust, but much like roasted brusselsprouts, you should try it before you bash it.
https://dannys.cloud/level-up-cloudformation-with-vs-code
https://marketplace.visualstudio.com/items?itemName=kddejong.vscode-cfn-lint
https://github.com/aws-cloudformation/aws-cfn-lint-visual-studio-code 
https://github.com/aws-cloudformation/cfn-python-lint
