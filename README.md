## nginx-php-fpm - [![build](https://github.com/richarvey/nginx-php-fpm/actions/workflows/build_images.yml/badge.svg)](https://github.com/richarvey/nginx-php-fpm/actions/workflows/build_images.yml) ![docker hub](https://img.shields.io/docker/pulls/richarvey/nginx-php-fpm.svg) ![docker hub](https://img.shields.io/docker/stars/richarvey/nginx-php-fpm.svg) ![Github](https://img.shields.io/github/stars/richarvey/nginx-php-fpm.svg) ![docker version](https://img.shields.io/docker/v/richarvey/nginx-php-fpm?sort=semver)

## Overview
This is a Dockerfile/image to build a container for nginx and php-fpm, with the ability to pull website code from git when the container is created, as well as allowing the container to push and pull changes to the code to and from git. The container also has the ability to update templated files with variables passed to docker in order to update your code and settings. There is support for lets encrypt SSL configurations, custom nginx configs, core nginx/PHP variable overrides for running preferences, X-Forwarded-For headers and UID mapping for local volume support.

If you have improvements or suggestions please open an issue or pull request on the GitHub project page.

### Versioning
| Docker Tag | Git Release | Nginx Version | PHP Version | Alpine Version |
|-----|-------|-----|--------|--------|
| latest/3.1.2 | Main Branch |1.22.1 | 8.2.4 | 3.17 |

For other tags please see: [versioning](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/versioning.md)

__NOTE:__ From 2.0.5 onwards there are x86 and arm64 builds available

### Links
- [https://github.com/richarvey/nginx-php-fpm](https://github.com/richarvey/nginx-php-fpm)
- [https://hub.docker.com/repository/docker/richarvey/nginx-php-fpm/general](https://hub.docker.com/repository/docker/richarvey/nginx-php-fpm/general)

## Quick Start
To pull from docker hub:
```
docker pull richarvey/nginx-php-fpm:latest
```
### Running
To simply run the container:
```
sudo docker run -d richarvey/nginx-php-fpm
```
To dynamically pull code from git when starting:
```
docker run -d -e 'GIT_EMAIL=email_address' -e 'GIT_NAME=full_name' -e 'GIT_USERNAME=git_username' -e 'GIT_REPO=github.com/project' -e 'GIT_PERSONAL_TOKEN=<long_token_string_here>' richarvey/nginx-php-fpm:latest
```

You can then browse to ```http://<DOCKER_HOST>``` to view the default install files. To find your ```DOCKER_HOST``` use the ```docker inspect``` to get the IP address (normally 172.17.0.2)

For more detailed examples and explanations please refer to the documentation.
## Documentation

- [Building from source](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/building.md)
- [Versioning](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/versioning.md)
- [Config Flags](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/config_flags.md)
- [Git Auth](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/git_auth.md)
  - [Personal Access token](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/git_auth.md#personal-access-token)
  - [SSH Keys](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/git_auth.md#ssh-keys)
- [Git Commands](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/git_commands.md)
 - [Push](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/git_commands.md#push-code-to-git)
 - [Pull](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/git_commands.md#pull-code-from-git-refresh)
- [Repository layout / webroot](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/repo_layout.md)
 - [webroot](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/repo_layout.md#src--webroot)
- [User / Group Identifiers](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/UID_GID_Mapping.md)
- [Custom Nginx Config files](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/nginx_configs.md)
 - [REAL IP / X-Forwarded-For Headers](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/nginx_configs.md#real-ip--x-forwarded-for-headers)
- [Scripting and Templating](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/scripting_templating.md)
 - [Environment Variables](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/scripting_templating.md#using-environment-variables--templating)
- [Lets Encrypt Support](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/lets_encrypt.md)
 - [Setup](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/lets_encrypt.md#setup)
 - [Renewal](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/lets_encrypt.md#renewal)
- [PHP Modules](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/php_modules.md)
- [Xdebug](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/xdebug.md)
- [Logging and Errors](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/logs.md)

## Guides
- [Running in Kubernetes](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/guides/kubernetes.md)
- [Using Docker Compose](https://github.com/richarvey/nginx-php-fpm/blob/main/docs/guides/docker_compose.md)
