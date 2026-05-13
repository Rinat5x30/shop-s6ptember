<div align="center">

# 🛍️ Django Shop

**A clean product catalog built with Django — browse by category, view product details, and manage everything via the admin panel.**

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-6.0.3-092E20?style=flat-square&logo=django&logoColor=white)](https://www.djangoproject.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

</div>

---

## Overview

Django Shop is a lightweight e-commerce catalog application. It lets you organise products into categories, upload product images, and manage the full inventory through Django's built-in admin interface — all with clean, slug-based URLs.

## Features

| Feature | Description |
|---|---|
| Category filtering | Browse products by category with dedicated pages |
| Product detail pages | Full product info with related products from the same category |
| Image uploads | Product images stored via Pillow with date-based folder structure |
| Admin panel | Inline price/availability editing, filters, prepopulated slugs |
| SEO-friendly URLs | Slug-based routing for categories and products |
| Secure config | Secrets loaded from `.env` via `python-decouple` — never hardcoded |

## Tech Stack

- **Framework** — Django 6.0.3
- **Language** — Python 3.10+
- **Database** — SQLite *(development)* — swappable via `DATABASES` setting
- **Images** — Pillow 12.1.1
- **Config** — python-decouple
- **Frontend** — Bootstrap 5.1.3 + Bootstrap Icons

## Getting Started

### Prerequisites

- Python 3.10+
- pip

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Rinat5x30/shop-s6ptember.git
cd shop-s6ptember

# 2. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # macOS / Linux

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure environment variables
cp .env.example .env
# Open .env and set your own SECRET_KEY

# 5. Apply database migrations
python manage.py migrate

# 6. Create an admin superuser
python manage.py createsuperuser

# 7. Start the development server
python manage.py runserver
```

Open **http://127.0.0.1:8000** in your browser.

## Environment Variables

Copy `.env.example` to `.env` and set the following:

| Variable | Description | Default |
|---|---|---|
| `SECRET_KEY` | Django secret key | **required** |
| `DEBUG` | Enable debug mode | `False` |
| `ALLOWED_HOSTS` | Comma-separated list of allowed hosts | `localhost` |

> **Never commit `.env`** — it is listed in `.gitignore`. Use `.env.example` as the reference template.

## Project Structure

```
shop/
├── main/                       # Core app — products & categories
│   ├── models.py               # Category, Product
│   ├── views.py                # product_list, product_detail
│   ├── admin.py                # Admin with inline editing
│   ├── urls.py                 # App-level URL patterns
│   ├── migrations/
│   └── templates/
│       └── main/
│           ├── base.html       # Bootstrap layout, nav, footer
│           └── product/
│               ├── list.html   # Product grid with category filter
│               └── detail.html # Product page with related items
├── shop/                       # Project configuration
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
├── .env.example                # Environment variable template
├── manage.py
└── requirements.txt
```

## Admin Panel

Go to **http://127.0.0.1:8000/admin** and log in with your superuser credentials.

From the admin you can:
- Create and manage **categories** (slugs are auto-generated from the name)
- Add **products** with images, price, description, and availability
- Edit price and availability directly from the product list view

## License

This project is licensed under the [MIT License](LICENSE).
