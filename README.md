# 🚀 MundialScope 2026

Dashboard interactivo y adaptativo desarrollado como actividad práctica de integración de APIs externas, enfocado en el Mundial 2026.

## 📌 Descripción del Proyecto

MundialScope 2026 es una aplicación web relacionada con el Mundial 2026. Su objetivo es permitir que el usuario consulte partidos, selecciones, grupos, resultados, datos de países participantes y clima de las ciudades sede.

Además, el proyecto plantea una sección de pronósticos y simulación para proyectar posibles resultados y un posible campeón del torneo. La aplicación busca integrar información real desde diferentes APIs, mostrando los datos de forma clara, visual y organizada.

## 🎯 Objetivo del Proyecto

El objetivo principal es demostrar el consumo e integración de múltiples APIs externas dentro de una aplicación web, aplicando buenas prácticas como:

* Separación entre frontend y backend.
* Uso de PHP para proteger claves privadas.
* Consumo de APIs mediante peticiones HTTP.
* Manejo de respuestas en formato JSON.
* Organización limpia del proyecto.
* Uso de variables de entorno para evitar exponer información sensible.

## 🛠️ Tecnologías Utilizadas

* HTML5
* CSS3
* JavaScript
* PHP puro
* APIs REST
* JSON
* Variables de entorno
* Git y GitHub

## 🧩 Arquitectura del Proyecto

La aplicación estará dividida en dos partes principales:

* **Frontend:** interfaz visual desarrollada con HTML, CSS y JavaScript.
* **Backend:** archivos PHP encargados de comunicarse con las APIs externas y proteger la API key.

El frontend no llamará directamente a API-Sports, ya que esta API utiliza una clave privada. En su lugar, JavaScript llamará a un archivo PHP interno, y ese archivo PHP será el encargado de consultar API-Sports usando una variable de entorno.

```txt
   [ Usuario interactúa con la interfaz ]
                     |
                     v
              [ APP FRONTEND ]
          HTML + CSS + JavaScript
                     |
                     v
             [ BACKEND PHP ]
         /          |          \
        v           v           v
[ API-Sports ] [ REST Countries ] [ Open-Meteo ]
```

## 🔌 APIs Utilizadas en la Aplicación

### 1. API-Sports / API-Football

Se utilizará para obtener información relacionada con el Mundial 2026, como:

* Partidos.
* Selecciones.
* Grupos.
* Resultados.
* Estadísticas.
* Información general del torneo.

Esta API requiere una clave privada, por lo que será consumida desde PHP y no directamente desde JavaScript.

### 2. REST Countries API

Se utilizará para mostrar datos del país de cada selección, como:

* Bandera.
* Capital.
* Población.
* Idioma.
* Moneda.
* Región.

### 3. Open-Meteo API

Se utilizará para mostrar el clima actual o pronosticado de la ciudad sede donde se jugará un partido, incluyendo datos como:

* Temperatura.
* Humedad.
* Velocidad del viento.
* Condición climática.

## 📁 Estructura del Proyecto

```txt
mundialscope-2026/
│
├── public/
│   ├── index.php
│   ├── css/
│   │   └── styles.css
│   └── js/
│       └── app.js
│
├── api/
│   ├── partidos.php
│   ├── pais.php
│   └── clima.php
│
├── config/
│   └── config.php
│
├── .env
├── .gitignore
└── README.md
```

## 🔐 Manejo de Variables de Entorno

El archivo `.env` se utilizará para guardar claves privadas, como la API key de API-Sports.

Este archivo no debe subirse a GitHub, ya que contiene información sensible.

Ejemplo de variable en el archivo `.env`:

```txt
API_FOOTBALL_KEY=tu_clave_privada
```

Para evitar subir este archivo al repositorio, se agregará al archivo `.gitignore`:

```txt
.env
```

De esta forma, el proyecto puede estar en GitHub sin exponer la clave privada.

## ⚙️ Funcionamiento General

El frontend realizará solicitudes a los archivos PHP internos del proyecto.

Ejemplo:

```js
fetch("../api/partidos.php")
  .then(response => response.json())
  .then(data => {
    console.log(data);
  });
```

Luego, el archivo `partidos.php` será el encargado de consultar API-Sports usando la clave guardada en el archivo `.env`.

De esta manera, la clave privada nunca aparece en el código JavaScript visible para el usuario.

## 🧠 Funcionalidades Previstas

* Consultar partidos del Mundial 2026.
* Ver selecciones participantes.
* Mostrar grupos y resultados.
* Consultar información general de cada país.
* Mostrar bandera, capital, idioma, moneda y población.
* Consultar clima de la ciudad sede.
* Realizar pronósticos básicos de partidos.
* Simular posibles clasificados y campeón del torneo.
* Mostrar la información en una interfaz moderna y responsive.

## 💻 Configuración Local e Instalación

1. Clonar el repositorio:

```bash
git clone https://github.com/pinela5202/mundialscope-2026.git
```

2. Entrar a la carpeta del proyecto:

```bash
cd mundialscope-2026
```

3. Crear el archivo `.env` en la raíz del proyecto:

```txt
API_FOOTBALL_KEY=tu_clave_privada
```

4. Verificar que el archivo `.gitignore` incluya:

```txt
.env
```

5. Ejecutar el proyecto en un entorno local compatible con PHP, como XAMPP, Laragon o el servidor integrado de PHP.

Ejemplo usando servidor integrado de PHP:

```bash
php -S localhost:8000 -t public
```

6. Abrir el proyecto en el navegador:

```txt
http://localhost:8000
```

## 🌐 Despliegue

El repositorio se subirá a GitHub para almacenar el código fuente del proyecto.

Para publicar la aplicación, se debe usar un hosting compatible con PHP, ya que el proyecto utiliza archivos PHP para proteger la API key y comunicarse con API-Sports.

## ✅ Buenas Prácticas Aplicadas

* No exponer la API key en archivos públicos.
* No subir el archivo `.env` a GitHub.
* Separar frontend y backend.
* Consumir APIs externas desde archivos PHP.
* Usar estructura de carpetas organizada.
* Documentar correctamente el proyecto en el README.
* Mantener el código limpio y entendible.

## 👤 Autor

**Wilson Cristóbal Pinela León**
**Curso:** 3ero Bachillerato Técnico “B”
**Proyecto:** Laboratorio de Integración de APIs
**Repositorio:** mundialscope-2026
