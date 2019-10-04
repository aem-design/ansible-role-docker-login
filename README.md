# Ansible Role: Docker Login

[![Build Status](https://travis-ci.org/aem-design/ansible-role-docker-login.svg?branch=master)](https://travis-ci.org/aem-design/ansible-role-docker-login)

This role tests AEM Dispatcher instance for specific Security patterns.
> This role was developed as part of
> [AEM.Design](http://aem.design/)

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Name                        	| Required 	| Default                                                             	| Notes                                                                          	|
|-----------------------------	|----------	|---------------------------------------------------------------------	|--------------------------------------------------------------------------------	|
|                             	|          	|                                                                     	|                                                                                	|
| docker_registry_username    	|          	| admin                                                               	| parameter for 'docker login --username'                                        	|
| docker_registry_password    	|          	| admin123                                                            	| parameter for 'docker login --password'                                        	|
| docker_registry_email       	|          	| devops@aem.design                                                   	| default email for docker login                                                 	|
|                             	|          	|                                                                     	|                                                                                	|
|                             	|          	|                                                                     	|                                                                                	|
| docker_registry_host        	|          	| ansible_host                                                        	| registry hostname configured on host in /etc/hosts                             	|
| docker_registry_port        	|          	| 5000                                                                	| registry default port                                                          	|
| docker_registry_mirror_port 	|          	| 5001                                                                	| registry default mirror port                                                   	|
| docker_registry_group_port  	|          	| 5002                                                                	| registry default group registry and mirror port configure group nexus          	|
|                             	|          	|                                                                     	|                                                                                	|
|                             	|          	|                                                                     	|                                                                                	|
| docker_registry             	|          	| {{ docker_registry_host }}:{{ docker_registry_port }}               	| Docker private registry address                                                	|
| docker_registry_url         	|          	| http://{{ docker_registry_host }}:{{ docker_registry_port }}        	|                                                                                	|
| docker_registry_mirror_url  	|          	| http://{{ docker_registry_host }}:{{ docker_registry_mirror_port }} 	| default https://registry-1.docker.io                                           	|
| docker_registry_group_url   	|          	| http://{{ docker_registry_host }}:{{ docker_registry_group_port }}  	| default https://registry-1.docker.io                                           	|
|                             	|          	|                                                                     	|                                                                                	|
|                             	|          	|                                                                     	|                                                                                	|
| docker_registry_use         	|          	| true                                                                	| true to use private registry                                                   	|
| docker_registry_images_pull 	|          	| true                                                                	| pull images from registry, inconsistent behaviour                              	|
| docker_registry_images_push 	|          	| true                                                                	| using docker in isolation by default. set to true to push to private registry. 	|

## Dependencies

This role depends on role `aem_design.docker_login`.

## Example Playbook

```yaml
- hosts: all
  roles:
    - {
      roles: aem_design.docker_login
    }
```

## License

Apache 2.0

## Author Information

This role was created by [Max Barrass](https://aem.design/).