# Django SaaS Starter

### A production-oriented foundation for building scalable multi-tenant SaaS applications.

`django-saas-starter` is an open-source Django foundation for teams building SaaS products that need **tenant isolation, authentication, role-based access, APIs, background processing, and production-ready infrastructure**.

Built and maintained by **[Waveinno Solutions](https://waveinno.com)**.

---

## Why This Project?

Building a SaaS application often means solving the same foundational problems repeatedly:

* Tenant management
* User authentication
* Role-based access control
* Database architecture
* API structure
* Background jobs
* Configuration management
* Local development
* Production deployment

This project provides a structured starting point so teams can focus more on their product and less on rebuilding the same foundation.

---

## Features

### Multi-Tenancy

Designed as a foundation for applications serving multiple organizations from a shared SaaS platform.

### Authentication

Provides a foundation for secure user authentication and account management.

### Role-Based Access

Designed to support roles and permissions across tenants and application resources.

### API Architecture

Structured for building maintainable REST APIs with clear separation between business logic and infrastructure.

### Background Processing

Prepared for asynchronous workloads such as notifications, scheduled tasks, integrations, and long-running jobs.

### Production-Oriented Structure

The project follows a modular structure intended to support development, testing, deployment, and long-term maintenance.

---

## Architecture

```text
                         SaaS Application
                                │
                                ▼
                         ┌─────────────┐
                         │    Nginx    │
                         └──────┬──────┘
                                │
                                ▼
                         ┌─────────────┐
                         │   Django    │
                         │     API     │
                         └──────┬──────┘
                                │
                ┌───────────────┼───────────────┐
                │               │               │
                ▼               ▼               ▼
           Tenants          Accounts         Business Apps
                │               │               │
                └───────────────┼───────────────┘
                                │
                    ┌───────────┴───────────┐
                    ▼                       ▼
               PostgreSQL                 Redis
                                            │
                                            ▼
                                          Worker
```

The architecture is intentionally modular so individual components can evolve as the SaaS product grows.

---

## Technology Stack

### Backend

* Python
* Django
* Django REST Framework

### Database

* PostgreSQL

### Caching & Background Processing

* Redis
* Celery

### Infrastructure

* Docker
* Nginx
* Linux

### Cloud

Designed to be deployable on cloud infrastructure such as AWS.

---

## Project Structure

```text
django-saas-starter/
│
├── apps/
│   ├── accounts/
│   ├── tenants/
│   ├── users/
│   ├── billing/
│   └── core/
│
├── config/
│   ├── settings/
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── docs/
│
├── tests/
│
├── docker/
│
├── .github/
│   └── workflows/
│
├── manage.py
├── d
```
