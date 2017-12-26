# Pacifica Policy API
[![Build Status](https://travis-ci.org/pacifica/pacifica-policy.svg?branch=master)](https://travis-ci.org/pacifica/pacifica-policy)
[![Build status](https://ci.appveyor.com/api/projects/status/rdid7r40620xl12o?svg=true)](https://ci.appveyor.com/project/dmlb2000/pacifica-policy)
[![Code Climate](https://codeclimate.com/github/pacifica/pacifica-policy/badges/gpa.svg)](https://codeclimate.com/github/pacifica/pacifica-policy)
[![Test Coverage](https://codeclimate.com/github/pacifica/pacifica-policy/badges/coverage.svg)](https://codeclimate.com/github/pacifica/pacifica-policy/coverage)
[![Issue Count](https://codeclimate.com/github/pacifica/pacifica-policy/badges/issue_count.svg)](https://codeclimate.com/github/pacifica/pacifica-policy)
[![Docker Stars](https://img.shields.io/docker/stars/pacifica/policy.svg?maxAge=2592000)](https://cloud.docker.com/swarm/pacifica/repository/docker/pacifica/policy/general)
[![Docker Pulls](https://img.shields.io/docker/pulls/pacifica/policy.svg?maxAge=2592000)](https://cloud.docker.com/swarm/pacifica/repository/docker/pacifica/policy/general)
[![Docker Automated build](https://img.shields.io/docker/automated/pacifica/policy.svg?maxAge=2592000)](https://cloud.docker.com/swarm/pacifica/repository/docker/pacifica/policy/builds)

This is the Pacifica Policy API and implements policy decisions
for the rest of the Pacifica software.

## Installing the Service

### Use the docker container

```
docker pull pacifica/policy
```

### The Docker Compose Way

Build the images from `pacifica-metadata`.
```
docker-compose build
```

Bring up the policy and metadata images.
```
docker-compose up
```

### The Manual Way

Install the dependencies using pip (or some other similar python way).
```
pip install -r requirements.txt
```

Run the code.
```
python PolicyServer.py
```

## The API

The policy server is split up into endpoints named for their Pacifica
project that utilizes them. So the path `/uploader` is used by the
Pacifica Uploader (http://github.com/pacifica/pacifica-uploader) to
control its behavior. The idea is that workflow implemented by the
various Pacifica projects has some element of site or instance
specific policy that can be applied to the running service. The policy
is driven by the metadata and thus this project should talk to the
metadata service.

### The Uploader Policy API
