## Fallos comunes

| Fallo | Escenario del mundo real |
|---|---|
| Inyección SQL | Obtener nombres de usuario de Active Directory y realizar un ataque de pulverización de contraseña contra una VPN o un portal de correo electrónico. |
| Inclusión de archivo | Leer el código fuente para encontrar una página o directorio oculto que exponga funcionalidad adicional que pueda utilizarse para obtener ejecución remota de código. |
| Carga de archivos sin restricciones | Una aplicación web permite a un usuario subir una imagen de perfil, pero acepta cualquier tipo de archivo y no solo imágenes. Esto puede aprovecharse para obtener el control total del servidor de aplicaciones web mediante la carga de código malicioso. |
| Referencia de objetos directos inseguros, IDOR | Cuando se combina con un defecto como control de acceso roto, puede utilizarse para acceder a archivos o funcionalidades de otro usuario. Por ejemplo, editar la URL del perfil de usuario `/user/701/edit-profile` y cambiar el identificador `701` por `702` para modificar el perfil de otra persona. |
| Control de acceso roto | Una aplicación permite registrar nuevas cuentas, pero la funcionalidad está mal diseñada. Por ejemplo, una solicitud POST envía `username=bjones&password=Welcome1&email=bjones@inlanefreight.local&roleid=3`. Si un atacante puede manipular el parámetro `roleid` y cambiarlo a `0` o `1`, podría registrarse como administrador y acceder a funcionalidades no autorizadas. |

## Tipos de aplicaciónes web
| Categoría | Descripción |
|---|---|
| Web Application Infrastructure | Describe la estructura de los componentes requeridos, como la base de datos, necesarios para que la aplicación web funcione según lo previsto. Dado que la aplicación web puede configurarse para ejecutarse en un servidor separado, es esencial saber a qué servidor de base de datos necesita acceder. |
| Web Application Components | Representa todos los componentes con los que interactúa la aplicación web. Estos se dividen en tres áreas: UI/UX, Client y Server Components. |
| Web Application Architecture | Comprende todas las relaciones entre los diversos componentes de la aplicación web. |
