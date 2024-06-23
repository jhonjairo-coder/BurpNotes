# Funcionalidad No Protegida y Escalada Vertical de Privilegios

## Introducción

La **escalada vertical de privilegios** ocurre cuando un usuario con menores privilegios obtiene acceso a funciones o datos restringidos para usuarios con mayores privilegios. Esto puede suceder si una aplicación no implementa correctamente controles de acceso para funciones sensibles.

## Funcionalidad No Protegida

### Ejemplo de Escalada Vertical de Privilegios

Imagina una aplicación web con una sección administrativa accesible a través de la URL:


#### Falta de Protección

- La URL debería estar protegida y solo accesible para usuarios con privilegios administrativos.
- Si la aplicación no implementa controles adecuados, cualquier usuario puede acceder a esta URL simplemente escribiéndola en su navegador.

#### Divulgación de la URL

- La URL de la funcionalidad administrativa podría ser revelada en otros lugares de la aplicación, como en el archivo `robots.txt`:
- Ejemplo de contenido del archivo `robots.txt`:

- Un atacante podría deducir que la URL `/admin` es importante y posiblemente contenga funciones administrativas.

#### Fuerza Bruta para Descubrir URLs

- Un atacante puede usar técnicas de fuerza bruta con una lista de palabras (wordlist) para intentar adivinar la ubicación de funciones sensibles.
- Herramientas automatizadas pueden probar diferentes combinaciones de URLs hasta encontrar una válida.

## Prevención

Para prevenir este tipo de vulnerabilidades, es fundamental implementar controles de acceso adecuados en todas las funciones sensibles:

### Autenticación y Autorización

- Asegurarse de que todas las funciones administrativas requieran autenticación.
- Verificar que el usuario autenticado tenga los privilegios necesarios antes de otorgar acceso.

### Revisión de Acceso

- Revisar y restringir acceso a URLs sensibles a nivel del servidor.
- Asegurarse de que solo usuarios autorizados puedan acceder a ellas.

### Seguridad en la Configuración

- Evitar la divulgación de URLs sensibles en archivos públicos como `robots.txt`.
- Revisar y proteger cualquier otro lugar donde las URLs sensibles puedan ser descubiertas.

Implementando estas prácticas, puedes proteger tu aplicación contra escalada vertical de privilegios y otros tipos de ataques.

---

## Referencias

- [Burp Suite Academy](https://portswigger.net/web-security)

