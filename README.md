# 🚀 DIDWW API Dashboard

Un dashboard web moderno para gestionar servicios de DIDWW a través de su API REST.

## ✨ Características

- 📞 **Búsqueda de Números**: Encuentra números telefónicos disponibles por país
- 📱 **Gestión de DIDs**: Visualiza y administra tus números activos
- 🔗 **SIP Trunks**: Configura y monitorea tus troncos SIP
- 📈 **CDRs**: Consulta registros detallados de llamadas
- 💰 **Balance**: Revisa saldo y facturas
- 📡 **Capacidades**: Información del sistema y configuraciones

## 🎯 Demo en Vivo

Visita: [https://tu-usuario.github.io/didww-api-dashboard](https://tu-usuario.github.io/didww-api-dashboard)

## 🛠️ Instalación

### Opción 1: Usar directamente
1. Descarga o clona este repositorio
2. Abre `index.html` en tu navegador
3. Ingresa tu API key de DIDWW
4. ¡Comienza a usar!

### Opción 2: Servidor local
```bash
# Con Python
python -m http.server 8000

# Con Node.js
npx serve .

# Con PHP
php -S localhost:8000
```

## 🔑 Configuración

### Obtener tu API Key
1. Inicia sesión en tu [Panel de DIDWW](https://www.didww.com/)
2. Ve a la sección **"API"**
3. Genera o copia tu API key
4. Pégala en el campo correspondiente del dashboard

### Endpoints Utilizados
- `GET /capacity_pools` - Test de conexión
- `GET /available_dids` - Búsqueda de números
- `GET /dids` - Números activos
- `GET /trunks` - SIP Trunks
- `GET /cdr_exports` - Registros de llamadas
- `GET /balance` - Balance actual
- `GET /invoices` - Facturas
- `POST /trunks` - Crear nuevo trunk

## ⚠️ Consideraciones CORS

Debido a las políticas CORS del navegador, podrías necesitar:

### Para Desarrollo
```bash
# Chrome con CORS deshabilitado (solo para desarrollo)
google-chrome --disable-web-security --user-data-dir="/tmp/chrome_dev"
```

### Para Producción
1. **Implementar un proxy backend**:
```javascript
// Express.js ejemplo
app.use('/api/didww/*', (req, res) => {
  const didwwUrl = 'https://api.didww.com/v3' + req.path;
  // Proxy request to DIDWW
});
```

2. **Configurar tu dominio con DIDWW** para permitir requests directos

## 🏗️ Arquitectura

```
├── index.html              # Aplicación principal
├── README.md              # Este archivo
└── assets/               # Recursos adicionales
    ├── images/           # Capturas de pantalla
    └── docs/             # Documentación extra
```

## 🔧 Personalización

### Modificar Estilos
El CSS está embebido en el HTML. Busca la sección `<style>` para personalizar:
- Colores: Cambia las variables en `:root`
- Diseño: Modifica las clases CSS
- Animaciones: Ajusta las `@keyframes`

### Agregar Funcionalidades
1. Agrega nuevos botones en el HTML
2. Crea las funciones JavaScript correspondientes
3. Implementa las llamadas a la API de DIDWW

## 📚 Documentación DIDWW

- [API Documentation](https://doc.didww.com/)
- [JSON API Specification](https://jsonapi.org/)
- [DIDWW Portal](https://www.didww.com/)

## 🐛 Solución de Problemas

### Error 401 - Unauthorized
- ✅ Verifica que tu API key sea correcta
- ✅ Asegúrate de tener permisos en tu cuenta DIDWW

### Error CORS
- ✅ Usa un servidor local para desarrollo
- ✅ Implementa un proxy backend para producción
- ✅ Contacta a DIDWW para configurar CORS en tu dominio

### Sin datos en las respuestas
- ✅ Verifica que tengas números/trunks configurados en DIDWW
- ✅ Revisa los filtros de fecha en CDRs
- ✅ Confirma que tu cuenta tenga los servicios activos

## 📸 Screenshots

![Dashboard](assets/images/dashboard-preview.png)
*Vista general del dashboard*

![API Connection](assets/images/connection-test.png)
*Test de conexión a la API*

## 🤝 Contribuir

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit tus cambios (`git commit -am 'Agrega nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Crea un Pull Request

## 📄 Licencia

Este proyecto está bajo la licencia MIT. Puedes usarlo libremente para proyectos personales y comerciales.

## 👨‍💻 Autor

Creado para facilitar la integración con los servicios de DIDWW.

---

**⚡ ¿Necesitas ayuda?** Abre un [issue](../../issues) o consulta la [documentación de DIDWW](https://doc.didww.com/).

**🌟 ¿Te gusta el proyecto?** ¡Dale una estrella al repositorio!
