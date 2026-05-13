# Django Shop

A product catalog web application built with Django. Browse products by category, view detailed product pages, and manage inventory through the Django admin panel.

## Features

- Product catalog with category filtering
- Product detail pages with related products
- Image uploads via Pillow
- Django admin panel with inline editing
- Slug-based SEO-friendly URLs

## Tech Stack

- **Backend:** Django 6.0.3
- **Database:** SQLite (development)
- **Image processing:** Pillow 12.1.1
- **Config management:** python-decouple

## Getting Started

### Prerequisites

- Python 3.10+
- pip

### Installation

```bash
# Clone the repository
git clone https://github.com/Rinat5x30/shop.git
cd shop

# Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # macOS / Linux

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env and set your own SECRET_KEY

# Apply migrations
python manage.py migrate

# Create a superuser
python manage.py createsuperuser

# Run the development server
python manage.py runserver
```

Open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

## Environment Variables

Copy `.env.example` to `.env` and fill in the values:

| Variable        | Description                        | Default      |
|-----------------|------------------------------------|--------------|
| `SECRET_KEY`    | Django secret key                  | **required** |
| `DEBUG`         | Debug mode (`True` / `False`)      | `False`      |
| `ALLOWED_HOSTS` | Comma-separated list of hosts      | `localhost`  |

## Project Structure

```
shop/
├── main/               # Products & categories app
│   ├── models.py       # Category, Product models
│   ├── views.py        # product_list, product_detail views
│   ├── admin.py        # Admin configuration
│   ├── urls.py         # App URL patterns
│   └── templates/
│       └── main/
│           ├── base.html
│           └── product/
│               ├── list.html
│               └── detail.html
├── shop/               # Project config
│   ├── settings.py
│   └── urls.py
├── .env.example
├── manage.py
└── requirements.txt
```

## Admin Panel

Navigate to [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin) and log in with your superuser credentials to manage categories and products.

## License

This project is open-source and available under the [MIT License](LICENSE).
