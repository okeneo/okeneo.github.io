---
layout: page
title: Blog API
description: A blog API built with Django
img: assets/img/API.png
importance: 3
category: current
---

### GitHub Repository

The repository can be found [here](https://github.com/okeneo/BlogAPI).

### About

I built a fully-functioning Blog REST API built using Django and the Django REST framework. It is hosted on an AWS EC2 instance and can be accessed [here](https://tegaokene.com/api/swagger). I do not keep it available at all times, however, due to the limitations of the AWS free-tier plan. The static API documenation version is always avalaible though, with the link below.

## Features

- **[Swagger Docs](https://okeneo.github.io/BlogAPI/) API documentation**
- JSON Web Token (JWT) for authentication
- Nginx as a reverse proxy
- Redis for caching
- Throttling to prevent abuse
- Free SSL certificates using Certbot (for HTTPS)
- Comprehensive unit tests

## Technologies Used

- Django and Django REST framework (DRF)
- Docker
- AWS (EC2, RDS, Route53)
- Nginx
- Redis
- JSON Web Token (JWT)
- PostgreSQL
- Certbot for HTTPS
