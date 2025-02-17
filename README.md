Laredu

Plataforma escolar con Laravel 11 (backend) y React 19 (frontend).

📌 Requisitos

PHP ^8.2

Composer

Node.js & npm

MySQL 8 o MariaDB

Postman (opcional, para probar la API REST)

🚀 Instalación del Backend (Laravel 11)

Clonar el repositorio y acceder a la carpeta backend:

git clone https://github.com/tuusuario/laredu.git
cd laredu/backend

Copiar y configurar el archivo .env:

cp .env.example .env

Luego, editar .env y configurar la base de datos:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laredu
DB_USERNAME=root
DB_PASSWORD=

Instalar dependencias y generar clave de aplicación:

composer install
php artisan key:generate

Ejecutar migraciones y seeders:

php artisan migrate --seed

Iniciar el servidor:

php artisan serve

El backend estará disponible en http://127.0.0.1:8000.

📂 Base de Datos

Si prefieres importar un respaldo de la base de datos en lugar de ejecutar migraciones manualmente:

En la carpeta backend/database/ encontrarás el archivo laredu.sql.

Importarlo manualmente con el siguiente comando:

mysql -u usuario -p laredu < laredu.sql

🛠 Instalación del Frontend (React 19 + Vite)

Ir a la carpeta frontend:

cd ../frontend

Instalar dependencias:

npm install

Iniciar el servidor de desarrollo:

npm run dev

El frontend estará disponible en http://localhost:3000.

🧪 Pruebas en Postman

Importar el archivo Postman Collection:

En docs/Laredu.postman_collection.json encontrarás una colección con todos los endpoints de la API.

Importa el archivo en Postman y usa las rutas configuradas.

Para endpoints protegidos, iniciar sesión y copiar el token:

POST http://127.0.0.1:8000/api/login

Copiar el token de la respuesta y usarlo en las peticiones protegidas con el encabezado:

Authorization: Bearer TU_TOKEN

📤 Despliegue en Producción

Optimizar Laravel:

php artisan config:cache
php artisan route:cache
php artisan view:cache

Compilar el frontend:

npm run build

Configurar un servidor (Apache/Nginx) y apuntar al backend en public/ y al frontend en dist/.

🚀 Subir Todo a GitHub

Asegúrate de que tu .gitignore ignore las carpetas vendor/, node_modules/ y .env.

Inicializa un repositorio Git dentro del proyecto si aún no lo has hecho:

git init

Añadir frontend/ y backend/ al repositorio:

git add .
git commit -m "Add backend and frontend"
git branch -M main
git remote add origin https://github.com/tuusuario/laredu.git
git push -u origin main

En GitHub, verás tu carpeta laredu/ con las subcarpetas backend/ y frontend/, junto con este README.md.

📜 Licencia

Este proyecto está bajo la licencia MIT.

🛠 Contribuciones

¡Las contribuciones son bienvenidas! Si deseas colaborar:

Haz un fork del repositorio.

Crea una nueva rama (git checkout -b feature-nueva).

Realiza tus cambios y haz commit (git commit -m "Añadir nueva funcionalidad").

Sube los cambios a tu repositorio (git push origin feature-nueva).

Crea un Pull Request en GitHub.
