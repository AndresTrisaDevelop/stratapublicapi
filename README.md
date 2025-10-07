# Strata Public API

![Python](https://img.shields.io/badge/python-3.11-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.103.2-green.svg)
![Pydantic](https://img.shields.io/badge/Pydantic-2.4.2-orange.svg)

API for managing transactional information in the furniture industry, built with FastAPI.

## Description

**Strata Public API** provides a RESTful interface for managing accounting operations, including Accounts Payable (AP) and Accounts Receivable (AR). It enables the creation, reading, updating, and deletion of various transactional entities and master data, such as purchase orders, invoices, customers, suppliers, and more.

The API is designed to be robust, user-friendly, and self-documented thanks to the features of FastAPI and Pydantic.

## Features

- **Modern Framework**: Built on **FastAPI** for high performance.
- **Data Validation**: Uses **Pydantic** for robust data validation and clear serialization.
- **Automatic Documentation**: Automatically generates interactive documentation with **Swagger UI** (`/docs`) and **ReDoc** (`/redoc`).
- **Modular Structure**: Organized into routers for clear separation of responsibilities (AP, AR, Master Data, Configuration).
- **Complete CRUD Operations**: Endpoints for `GET`, `POST`, `PATCH`, and `DELETE` for all main entities.

---

## Installation and Setup

Follow these steps to set up the local development server.

### Prerequisites

- Python 3.9+
- `pip` (Python package manager)

### 1. Clone the Repository (Optional)

If you're working from a Git repository, clone it. Otherwise, make sure you're in the project's root directory.

```bash
git clone <repository-url>
cd Strata_Public_API
```

### 2. Create and Activate a Virtual Environment

It's good practice to isolate project dependencies.

```bash
# For Windows
python -m venv venv
.\venv\Scripts\activate

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

Install all necessary packages from the `requirements.txt` file.

```bash
pip install -r requirements.txt
```

---

## How to Run the Application

Once setup is complete, you can start the development server with Uvicorn.

```bash
uvicorn app.main:app --reload
```

- `app.main:app`: Tells Uvicorn to look for the `app` object in the `app/main.py` file.
- `--reload`: Automatically restarts the server whenever a code change is detected.

The server will be available at `http://127.0.0.1:8000`.

---

## Explore the API

Once the server is running, you can access the interactive API documentation from your browser:

- **Swagger UI**: http://127.0.0.1:8000/docs
- **ReDoc**: http://127.0.0.1:8000/redoc

From the Swagger interface, you can explore all endpoints, view data schemas, and test the API directly.

---

## Project Structure

```
strata_public_api/
|-- venv/
|-- app/
|   |-- __init__.py
|   |-- main.py             # Application entry point
|   |-- routers/            # Endpoint modules
|   |   |-- accounts_payable.py
|   |   |-- accounts_receivable.py
|   |   |-- catalogs.py
|   |   |-- configuration.py
|   |   |-- ... (and other routers)
|   `-- schemas/            # Pydantic data models
|       |-- purchase_order.py
|       |-- bill.py
|       |-- ... (and other schemas)
`-- requirements.txt        # Project dependencies
```
