# Mi Red — versión estática sin variables de Render

Esta versión elimina PayPal y el servidor Node.js para que Render no necesite variables de entorno.

## Publicar en GitHub y Render
1. Descomprime el ZIP.
2. Sube el contenido de la carpeta `final` a la raíz de un repositorio de GitHub (debe quedar `index.html` en la raíz).
3. En Render elige **New + → Static Site** y conecta ese repositorio.
4. En **Build Command**, déjalo vacío. En **Publish Directory**, escribe `.` (un punto).
5. Pulsa **Create Static Site**. No agregues variables de entorno.

## Activación necesaria de Firebase (una sola vez)
El código incluye la configuración web del proyecto Firebase que compartiste. Para que el registro y las publicaciones funcionen, igualmente debes:
1. En Firebase Console → Authentication → Sign-in method, habilitar **Email/Password**.
2. Crear Firestore Database si todavía no existe.
3. En Firestore → Rules, pegar el contenido de `firestore.rules` y pulsar **Publish**.
4. En Authentication → Settings → Authorized domains, añadir el dominio que te asigna Render.

No se puede omitir la configuración de Firebase desde el código: es el servicio que guarda las cuentas y publicaciones. No hace falta copiar la configuración a Render.

## Límites de esta versión
- No incluye PayPal ni suscripciones Premium.
- Esta versión no tiene servidor ni variables de Render.
- Los campos de imagen aceptan una URL de imagen segura; no incluye carga directa de archivos a Cloudinary.
- No afirmar que todas las funciones avanzadas (chat, reservas, mapas, notificaciones o moderación) estén implementadas.
- Antes de usarla públicamente, prueba las reglas con dos cuentas distintas y revisa privacidad y permisos.
