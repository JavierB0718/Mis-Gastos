[LEEME.md](https://github.com/user-attachments/files/34644010/LEEME.md)
# Mis gastos — app instalable

Contenido de esta carpeta:
- index.html, manifest.json, sw.js, icons/ → la app (se publica en GitHub Pages)
- Code.gs → el "servidor" que guarda los datos en tu planilla de Google

## Paso 1 — Planilla de Google (donde se guardan los datos)
1. Creá una planilla nueva en Google Sheets (por ejemplo "Mis gastos - datos").
2. Menú Extensiones > Apps Script. Borrá lo que aparece y pegá todo el contenido de Code.gs. Guardá.
3. Arriba elegí la función "configurar" y tocá Ejecutar. Autorizá los permisos (Google avisa que la app no está verificada: Configuración avanzada > Ir a… ). En "Registro de ejecución" aparece "Tu CLAVE es: …". Copiala.
4. Implementar > Nueva implementación > tipo "Aplicación web". Ejecutar como: Yo. Quién tiene acceso: Cualquier usuario. Implementar y copiá la URL que termina en /exec.

## Paso 2 — Publicar la app (GitHub Pages, gratis)
1. Creá una cuenta en github.com si no tenés.
2. New repository > nombre "mis-gastos" > Public > Create.
3. "uploading an existing file" > arrastrá index.html, manifest.json, sw.js y la carpeta icons > Commit.
4. Settings > Pages > Branch: main / (root) > Save. En 1-2 minutos la app queda en https://TU-USUARIO.github.io/mis-gastos/

## Paso 3 — Instalarla en el celular
- Android (Chrome): abrí el enlace > menú ⋮ > "Instalar app" o "Agregar a la pantalla principal".
- iPhone (Safari): abrí el enlace > Compartir > "Agregar a pantalla de inicio".
Abrila, tocá ⚙ y pegá la URL /exec y la clave. Repetí lo mismo en la PC (en Chrome/Edge también se puede instalar con el ícono de la barra de direcciones).

## Paso 4 — Pasar los datos de la versión anterior
En la app anterior (link de Claude) tocá "Exportar CSV". En la nueva: ⚙ > Importar CSV.

## Si cambiás Code.gs más adelante
Implementar > Administrar implementaciones > editar (lápiz) > Versión: Nueva versión. Así la URL /exec no cambia.

## Seguridad
La URL /exec y la clave dan acceso a tus datos: no las compartas. Si se filtraran, borrá la propiedad CLAVE en Apps Script (Configuración del proyecto > Propiedades del script) y ejecutá "configurar" otra vez para generar una nueva.
