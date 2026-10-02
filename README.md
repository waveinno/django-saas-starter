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
├── docker-compose.yml
├── requirements.txt
└── .env.example
```

The structure may evolve as the project develops.

---

## Getting Started

### Requirements

Before starting, make sure you have:

* Python 3.11+
* PostgreSQL
* Redis
* Git
* Docker (recommended)

### Clone

```bash
git clone https://github.com/waveinno/django-saas-starter.git

cd django-saas-starter
```

### Environment

Copy the example environment file:

```bash
cp .env.example .env
```

Configure the required environment variables.

### Run with Docker

```bash
docker compose up --build
```

The application will become available through the configured development endpoint.

---

## Development

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it:

### Linux / macOS

```bash
source .venv/bin/activate
```

### Windows

```powershell
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run migrations:

```bash
python manage.py migrate
```

Start the development server:

```bash
python manage.py runserver
```

---

## Roadmap

The project is being developed incrementally.

### Foundation

* [x] Initial project structure
* [ ] Configuration management
* [ ] PostgreSQL integration
* [ ] Docker development environment

### Multi-Tenancy

* [ ] Tenant model
* [ ] Tenant isolation
* [ ] Tenant-aware middleware
* [ ] Tenant provisioning
* [ ] Tenant administration

### Authentication

* [ ] User registration
* [ ] Authentication
* [ ] Password management
* [ ] Session/token management

### Authorization

* [ ] Roles
* [ ] Permissions
* [ ] Tenant-level access control

### Platform

* [ ] REST API
* [ ] Background jobs
* [ ] Notifications
* [ ] Audit logging
* [ ] Health checks

### Production

* [ ] CI/CD
* [ ] Production Docker setup
* [ ] Monitoring
* [ ] Security hardening
* [ ] AWS deployment examples

---

## Documentation

Project documentation will be maintained under:

```text
/docs
```

Planned documentation includes:

* Architecture
* Multi-tenancy
* Local development
* Deployment
* Configuration
* Security
* API usage
* Contribution guidelines

---

## Contributing

Contributions are welcome.

Please read the project's contribution guidelines before submitting an issue or pull request.

See:

```text
CONTRIBUTING.md
```

---

## Security

If you discover a security vulnerability, please report it responsibly rather than opening a public issue.

Security guidance will be maintained in:

```text
SECURITY.md
```

---

## License

This project will be released under an open-source license.

See the `LICENSE` file for details.

---

## About Waveinno

**Waveinno Solutions** is an enterprise software engineering company building:

* Enterprise software
* SaaS platforms
* AI-powered systems
* Cloud infrastructure
* Business applications
* APIs and distributed systems

🌐 **Website:** https://waveinno.com

🚀 **GitHub:** https://github.com/waveinno

📚 **Engineering:** https://waveinno.com/blog

---

## Support the Project

If this project helps your team:

⭐ Star the repository

🐛 Report issues

💡 Share ideas

🔧 Contribute improvements

---

### Built by Waveinno

**Enterprise software built around how your business actually runs.**

https://waveinno.com
