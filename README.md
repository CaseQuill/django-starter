
# Django Starter Project with Poetry

## Setup Instructions

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/myproject.git
   cd myproject
   ```

2. **Install Poetry**

   Ensure that Poetry is installed on your system. If not, install it using:

   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```

   For more installation options, visit the [Poetry documentation](https://python-poetry.org/docs/#installation).

3. **Install Project Dependencies**

   ```bash
   poetry install
   ```

   This command will:

   - Create a virtual environment (if one doesn't exist).
   - Install all dependencies specified in `pyproject.toml`.

4. **Apply Migrations**

   ```bash
   poetry run python manage.py migrate
   ```

5. **Create a Superuser (Optional)**

   If you want to use the admin interface to add items:

   ```bash
   poetry run python manage.py createsuperuser
   ```

6. **Run the Development Server**

   ```bash
   poetry run python manage.py runserver
   ```

7. **Access the Application**

   - **Item List View**: [http://localhost:8000/items/](http://localhost:8000/items/)
   - **Admin Interface**: [http://localhost:8000/admin/](http://localhost:8000/admin/)

---

## Adding Sample Data

You can add sample data in two ways:

### Using the Admin Interface

1. Navigate to [http://localhost:8000/admin/](http://localhost:8000/admin/).
2. Log in with your superuser credentials.
3. Click on **Items** and add new items.

### Using the Django Shell

```bash
poetry run python manage.py shell
```

Then, execute:

```python
from core.models import Item
Item.objects.create(name='Sample Item 1')
Item.objects.create(name='Sample Item 2')
exit()
```

---

## Alternative: Using the Poetry Shell

You can activate the Poetry shell to avoid prefixing commands with `poetry run`:

```bash
poetry shell
```

Now you can run Django commands directly:

```bash
python manage.py migrate
python manage.py runserver
```

---

## Notes

- Ensure you have **Python 3.6** or higher installed.
- If you encounter any issues, please check your Python and Poetry installations.
- For any questions or issues, feel free to contact us at [email@example.com](mailto:email@example.com).

---

## Project Structure

The basic structure of the project is as follows:

```
myproject/
├── core/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations/
│   │   └── __init__.py
│   ├── models.py
│   ├── templates/
│   │   └── core/
│   │       └── item_list.html
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── myproject/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── pyproject.toml
├── poetry.lock
├── manage.py
└── README.md
```

---

## Brief Overview

This starter project includes:

- A Django project set up with Poetry for dependency management.
- A `core` app with a simple `Item` model.
- A basic view (`item_list`) that displays a list of `Item` instances.
- Templates configured to render the `item_list.html`.
- URLs configured to route to the `item_list` view.
- Instructions to help you get started quickly.

---

## How to Extend the Project

Feel free to extend this project by:

- Adding new models and fields.
- Creating additional views and templates.
- Implementing forms and user authentication.
- Connecting to a real database (e.g., PostgreSQL) if needed.
- Adding RESTful endpoints using Django REST Framework.

---

## License

This project is open-source and available under the [MIT License](LICENSE).

---

## Contact

If you have any questions or need assistance, please contact:

- **Email**: [email@example.com](mailto:email@example.com)
- **GitHub**: [https://github.com/yourusername/myproject](https://github.com/yourusername/myproject)

Happy coding!