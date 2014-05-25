Dockerfiles
===========

Dockerfiles for creating docker images

This software is released under the MIT License, see LICENSE.txt.

## sshmonit, sshmonitmongo, smmtd

These are registered to docker public registry.

 ex. docker pull igaki/sshmonit

In order to access containers from these public image, the following command should be added.

RUN echo 'passwd' | passwd root --stdin

## docker-registry

This dockerfile add sshd setting to the doc-cloud/docker-registry(https://github.com/dotcloud/docker-registry).
* Usage(in docker-registry dir.)
 * docker build -t hoge/hoge .
 * you should change "newpassword" to adequate one.
