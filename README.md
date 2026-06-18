# BarberFlow

## Descripción del proyecto

BarberFlow es una aplicación web desarrollada para la gestión de citas en una barbería. El sistema permite que los clientes revisen los servicios disponibles, conozcan a los barberos, seleccionen varios servicios y agenden una cita de forma rápida. También incluye un panel administrativo oculto para que el dueño pueda revisar las citas registradas.

El proyecto integra frontend, backend, base de datos en la nube y varias APIs externas para mejorar la funcionalidad del sistema.

## Enlace del proyecto

https://barberflow-vercel.vercel.app/

## Autor

Wilson Cristóbal Pinela León
Unidad Educativa Montepiedra
3ero Bachillerato Técnico “B”
Figura profesional: Informática

## Tecnologías utilizadas

* HTML5
* CSS3
* JavaScript
* Node.js
* Vercel Functions
* Supabase
* Vercel
* APIs externas

## Funcionalidades principales

* Visualización de servicios de barbería.
* Visualización de barberos y barbera disponibles.
* Agendamiento de citas.
* Selección de múltiples servicios en una misma cita.
* Recomendación automática del mejor barbero según los servicios seleccionados.
* Validación de disponibilidad de horarios.
* Bloqueo de horarios ocupados.
* Panel administrativo oculto.
* Consulta de clima.
* Consulta de feriados.
* Generación de código QR para citas.

## APIs utilizadas

### 1. Supabase API

Supabase se utilizó como base de datos en la nube. Por medio de esta API se guardan y consultan los servicios, barberos, citas y la relación entre cada cita y los servicios seleccionados. Esta API permite que el sistema trabaje con información real y persistente.

### 2. Open-Meteo API

Open-Meteo API se utilizó para consultar información del clima. Esta API permite mostrar datos climáticos relacionados con la ubicación de la barbería, lo cual mejora la experiencia del usuario antes de asistir a su cita.

### 3. Nager.Date API

Nager.Date API se utilizó para consultar días feriados. Esta información puede servir para controlar la disponibilidad de citas en fechas especiales o días no laborables.

### 4. QRServer API

QRServer API se utilizó para generar códigos QR. En el sistema, el código QR puede relacionarse con la información de la cita, permitiendo una presentación más moderna y práctica de la reserva.

### 5. APIs propias con Vercel Functions

Además de las APIs externas, se crearon APIs propias usando Vercel Functions. Estas funciones actúan como backend del sistema y conectan el frontend con Supabase y con los servicios externos.

## Endpoints principales del proyecto

* `/api/services`
* `/api/barbers`
* `/api/appointments`
* `/api/availability`
* `/api/recommendation`
* `/api/holidays`
* `/api/weather`
* `/api/qr`
* `/api/admin-login`
* `/api/admin-appointments`

## Páginas principales

* `/`
* `/servicios.html`
* `/barberos.html`
* `/agendar.html`
* `/mis-citas.html`
* `/ubicacion.html`
* `/contacto.html`
* `/acerca.html`
* `/admin-login.html`

## Variables de entorno necesarias

El proyecto utiliza variables de entorno para proteger las claves privadas y configurar la conexión con Supabase.

Ejemplo:

```env
SUPABASE_URL=tu_url_de_supabase
SUPABASE_SERVICE_ROLE_KEY=tu_clave_privada_de_supabase
OWNER_PASSWORD=contraseña_del_administrador
APP_USER_AGENT=BarberFlow/1.0
```

Importante: el archivo `.env` no debe subirse a GitHub porque contiene claves privadas.

## Instalación local

Para ejecutar el proyecto de forma local:

```bash
npm install
npx vercel@latest dev
```

Luego abrir en el navegador:

```txt
http://localhost:3000
```

## Despliegue

El proyecto fue desplegado en Vercel. Para que funcione correctamente en producción, las variables de entorno deben agregarse en:

```txt
Vercel → Project Settings → Environment Variables
```

Luego se realiza el despliegue con:

```bash
npx vercel@latest --prod
```

## Conclusión

BarberFlow demuestra el uso de integración de APIs en una aplicación web funcional. El sistema permite conectar una interfaz visual con servicios externos, una base de datos en la nube y funciones backend. Gracias a esta integración, la aplicación puede gestionar citas reales, consultar información dinámica, recomendar barberos y mejorar la experiencia del usuario.
