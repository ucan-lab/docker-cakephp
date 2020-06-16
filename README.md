# docker-cakephp

![License](https://img.shields.io/github/license/ucan-lab/docker-cakephp?color=c92735)
![Stars](https://img.shields.io/github/stars/ucan-lab/docker-cakephp?color=c92735)
![Issues](https://img.shields.io/github/issues/ucan-lab/docker-cakephp?color=c92735)
![Forks](https://img.shields.io/github/forks/ucan-lab/docker-cakephp?color=c92735)

## Introduction

Build cakephp development environment with docker-compose.

## Usage

- [Build for Mac](https://github.com/ucan-lab/docker-cakephp/wiki/Build-for-Mac)
- [Build for Windows](https://github.com/ucan-lab/docker-cakephp/wiki/Build-for-Windows)

## Container structure

```bash
├── app
├── web
└── db
```

### app container

- Base image
  - [php](https://hub.docker.com/_/php):7.4-fpm-buster
  - [composer](https://hub.docker.com/_/composer):latest

### web container

- Base image
  - [nginx](https://hub.docker.com/_/nginx):1.18-alpine
  - [node](https://hub.docker.com/_/node):14.2-alpine

### db container

- Base image
  - [mysql](https://hub.docker.com/_/mysql):8.0
