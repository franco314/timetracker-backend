# Instrucciones de Despliegue - TimeTracker Pro

## ✅ Cambios Realizados

### 1. **settings.py actualizado**:
- ✅ Configuración para producción
- ✅ CORS habilitado
- ✅ Base de datos PostgreSQL configurada
- ✅ Variables de entorno configuradas
- ✅ Configuración de seguridad agregada

### 2. **Archivos de configuración creados**:
- ✅ `requirements.txt` - Dependencias necesarias
- ✅ `Procfile` - Para despliegue en Heroku/Railway
- ✅ `runtime.txt` - Versión de Python
- ✅ `env_example.txt` - Ejemplo de variables de entorno

## 🚀 Pasos para Desplegar

### Paso 1: Elegir Plataforma
**Recomendado: Railway** (más fácil y gratis)

1. Ve a [railway.app](https://railway.app)
2. Crea una cuenta
3. Conecta tu repositorio de GitHub

### Paso 2: Subir el Código
1. Sube tu proyecto Django a GitHub
2. Conecta el repositorio en Railway
3. Railway detectará automáticamente que es un proyecto Django

### Paso 3: Configurar Variables de Entorno
En Railway, agrega estas variables:

```
DEBUG=False
SECRET_KEY=tu-clave-secreta-muy-larga-aqui-cambiala
DB_NAME=railway
DB_USER=postgres
DB_PASSWORD=password_que_te_da_railway
DB_HOST=host_que_te_da_railway
DB_PORT=5432
```

### Paso 4: Configurar Base de Datos
1. En Railway, agrega un servicio de PostgreSQL
2. Railway te dará automáticamente las credenciales
3. Usa esas credenciales en las variables de entorno

### Paso 5: Ejecutar Migraciones
Railway ejecutará automáticamente:
```bash
python manage.py migrate
```

### Paso 6: Obtener la URL
Railway te dará una URL como:
`https://tu-app.up.railway.app`

### Paso 7: Actualizar Android Studio
En `RetrofitClient.kt`, cambia:
```kotlin
private const val BASE_URL_RAILWAY = "https://tu-app.up.railway.app/api/"
```

## 🔧 Comandos Útiles

### Para desarrollo local:
```bash
cd "app/Horas carrefour"
pip install -r requirements.txt
python manage.py runserver
```

### Para verificar la configuración:
```bash
python manage.py check --deploy
```

## 🚨 Solución de Problemas

### Error de CORS:
- Verifica que `corsheaders` esté en `INSTALLED_APPS`
- Verifica que `CorsMiddleware` esté en `MIDDLEWARE`

### Error de base de datos:
- Verifica las variables de entorno
- Asegúrate de que la base de datos esté creada

### Error de conexión en Android:
- Verifica que la URL sea correcta
- Asegúrate de que el servidor esté funcionando

## 📱 Prueba Final

1. Despliega el backend
2. Obtén la URL de Railway
3. Actualiza `RetrofitClient.kt` con la URL
4. Compila la app Android
5. Prueba hacer login y crear registros

## 🎯 Resultado

Una vez completado, tu app funcionará desde cualquier lugar sin depender de tu PC.

---

*¡Tu proyecto está listo para producción!* 