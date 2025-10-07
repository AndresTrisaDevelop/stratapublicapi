# Strata Public API

![Python](https://img.shields.io/badge/python-3.11-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.103.2-green.svg)
![Pydantic](https://img.shields.io/badge/Pydantic-2.4.2-orange.svg)

API para la gestión de información transaccional en la industria del mueble (furniture), construida con FastAPI.

## Descripción

**Strata Public API** proporciona una interfaz RESTful para gestionar las operaciones de contabilidad, incluyendo Cuentas por Pagar (Accounts Payable) y Cuentas por Cobrar (Accounts Receivable). Permite la creación, lectura, actualización y eliminación de diversas entidades transaccionales y de datos maestros, como órdenes de compra, facturas, clientes, proveedores y más.

La API está diseñada para ser robusta, fácil de usar y auto-documentada gracias a las características de FastAPI y Pydantic.

## Características

- **Framework Moderno**: Construido sobre **FastAPI** para un alto rendimiento.
- **Validación de Datos**: Utiliza **Pydantic** para una validación de datos robusta y una serialización clara.
- **Documentación Automática**: Genera automáticamente documentación interactiva con **Swagger UI** (`/docs`) y **ReDoc** (`/redoc`).
- **Estructura Modular**: Organizada en routers para una clara separación de responsabilidades (AP, AR, Datos Maestros, Configuración).
- **Operaciones CRUD Completas**: Endpoints para `GET`, `POST`, `PATCH`, y `DELETE` para todas las entidades principales.

---

## Instalación y Configuración

Sigue estos pasos para poner en marcha el servidor de desarrollo local.

### Prerrequisitos

- Python 3.9+
- `pip` (gestor de paquetes de Python)

### 1. Clonar el Repositorio (Opcional)

Si estás trabajando desde un repositorio Git, clónalo. De lo contrario, asegúrate de estar en el directorio raíz del proyecto.

```bash
git clone <url-del-repositorio>
cd Strata_Public_API
```

### 2. Crear y Activar un Entorno Virtual

Es una buena práctica aislar las dependencias del proyecto.

```bash
# Para Windows
python -m venv venv
.\venv\Scripts\activate

# Para macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Instalar Dependencias

Instala todos los paquetes necesarios desde el archivo `requirements.txt`.

```bash
pip install -r requirements.txt
```

---

## Cómo Ejecutar la Aplicación

Una vez que la configuración esté completa, puedes iniciar el servidor de desarrollo con Uvicorn.

```bash
uvicorn app.main:app --reload
```

- `app.main:app`: Le dice a Uvicorn que busque el objeto `app` en el archivo `app/main.py`.
- `--reload`: Reinicia el servidor automáticamente cada vez que se detecta un cambio en el código.

El servidor estará disponible en `http://127.0.0.1:8000`.

---

## Explorar la API

Una vez que el servidor esté en funcionamiento, puedes acceder a la documentación interactiva de la API desde tu navegador:

- **Swagger UI**: http://127.0.0.1:8000/docs
- **ReDoc**: http://127.0.0.1:8000/redoc

Desde la interfaz de Swagger, puedes explorar todos los endpoints, ver los esquemas de datos y probar la API directamente.

---

## Estructura del Proyecto

```
strata_public_api/
|-- venv/
|-- app/
|   |-- __init__.py
|   |-- main.py             # Punto de entrada de la aplicación
|   |-- routers/            # Módulos de endpoints
|   |   |-- accounts_payable.py
|   |   |-- accounts_receivable.py
|   |   |-- catalogs.py
|   |   |-- configuration.py
|   |   |-- ... (y otros routers)
|   `-- schemas/            # Modelos de datos Pydantic
|       |-- purchase_order.py
|       |-- bill.py
|       |-- ... (y otros esquemas)
`-- requirements.txt        # Dependencias del proyecto
```
