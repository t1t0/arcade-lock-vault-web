# Arcade Lock Vault (Frontend Web)

Una aplicación web self-hosted para organizar y gestionar las contraseñas de sitios web de equipos en un entorno seguro y amigable. Esta aplicación permite a los equipos almacenar, organizar y compartir credenciales de manera segura, facilitando la colaboración mientras mantiene altos estándares de seguridad.

## Características

- 🔐 Gestión segura de contraseñas para equipos
- 🌐 Aplicación web self-hosted
- 👥 Colaboración en equipo
- 🔒 Entorno seguro y cifrado
- 🎨 Interfaz amigable e intuitiva
- ⚡ Construida con Next.js para rendimiento óptimo

## Tecnologías

Este proyecto está construido con:
- [Next.js](https://nextjs.org) - Framework de React
- TypeScript - Para tipado estático
- Tailwind CSS - Para estilos

## Requisitos Previos

Antes de comenzar, asegúrate de tener instalado:
- Node.js (versión 18 o superior)
- npm, yarn, pnpm o bun

## Instalación y Configuración

### 1. Clonar el repositorio

```bash
git clone <url-del-repositorio>
cd arcade-lock-vault-web
```

### 2. Instalar dependencias

```bash
npm install
# o
yarn install
# o
pnpm install
# o
bun install
```

### 3. Configurar variables de entorno

Crea un archivo `.env.local` en la raíz del proyecto:

```bash
cp .env.example .env.local
```

Edita el archivo `.env.local` con tus configuraciones:

```env
# Base de datos
DATABASE_URL="your-database-url"

# Autenticación
NEXTAUTH_SECRET="your-nextauth-secret"
NEXTAUTH_URL="http://localhost:3000"

# Cifrado
ENCRYPTION_KEY="your-encryption-key"

# Otras configuraciones...
```

## Desarrollo

### Ejecutar el servidor de desarrollo

```bash
npm run dev
# o
yarn dev
# o
pnpm dev
# o
bun dev
```

Abre [http://localhost:3000](http://localhost:3000) en tu navegador para ver la aplicación.

La página se actualiza automáticamente cuando editas los archivos.

### Comandos útiles para desarrollo

```bash
# Ejecutar tests
npm run test

# Ejecutar linter
npm run lint

# Formatear código
npm run format

# Verificar tipos de TypeScript
npm run type-check
```

## Producción

### Preparar para producción

#### 1. Configurar variables de entorno de producción

Crea un archivo `.env.production` o configura las variables de entorno en tu servidor:

```env
# Base de datos de producción
DATABASE_URL="your-production-database-url"

# URL de producción
NEXTAUTH_URL="https://tu-dominio.com"

# Claves de cifrado seguras
ENCRYPTION_KEY="your-secure-production-encryption-key"
NEXTAUTH_SECRET="your-secure-production-nextauth-secret"
```

#### 2. Construir la aplicación

```bash
npm run build
```

#### 3. Ejecutar en producción

```bash
npm start
```

### Despliegue con Docker

#### Crear imagen Docker

```bash
# Construir la imagen
docker build -t arcade-lock-vault .

# Ejecutar el contenedor
docker run -p 3000:3000 --env-file .env.production arcade-lock-vault
```

#### Docker Compose

```yaml
# docker-compose.yml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "3000:3000"
    env_file:
      - .env.production
    depends_on:
      - db
  
  db:
    image: postgres:15
    environment:
      POSTGRES_DB: arcade_vault
      POSTGRES_USER: vault_user
      POSTGRES_PASSWORD: secure_password
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```

Ejecutar con Docker Compose:

```bash
docker-compose up -d
```

### Despliegue en Vercel

1. Conecta tu repositorio a [Vercel](https://vercel.com)
2. Configura las variables de entorno en el dashboard de Vercel
3. Despliega automáticamente con cada push a la rama principal

### Despliegue en otros proveedores

- **Railway**: Conecta tu repositorio y configura las variables de entorno
- **Heroku**: Usa el buildpack de Node.js y configura las variables de entorno
- **DigitalOcean App Platform**: Conecta tu repositorio y configura las variables

## Configuración de Seguridad

### Recomendaciones importantes:

1. **Claves de cifrado**: Usa claves fuertes y únicas para producción
2. **HTTPS**: Siempre usa HTTPS en producción
3. **Base de datos**: Configura tu base de datos con credenciales seguras
4. **Backups**: Implementa backups regulares de la base de datos
5. **Actualizaciones**: Mantén las dependencias actualizadas

### Variables de entorno críticas:

- `ENCRYPTION_KEY`: Clave para cifrar las contraseñas almacenadas
- `NEXTAUTH_SECRET`: Secreto para la autenticación
- `DATABASE_URL`: URL de conexión a la base de datos

## Contribuir

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## Soporte

Si tienes problemas o preguntas:

1. Revisa la documentación
2. Busca en los issues existentes
3. Crea un nuevo issue si es necesario

## Recursos Adicionales

- [Documentación de Next.js](https://nextjs.org/docs)
- [Tutorial interactivo de Next.js](https://nextjs.org/learn)
- [Repositorio de Next.js en GitHub](https://github.com/vercel/next.js)
