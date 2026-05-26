


## Protocolo de transferencia de hipertexto (HTTP)
> https://admin:password@inlanefreight.com:443/dashboard.php?login=true#status

| Componente | Ejemplo | Descripción |
|---|---|---|
| Scheme | `http://` / `https://` | Se utiliza para identificar el protocolo al que accede el cliente. Termina con dos puntos y doble barra (`://`). |
| User Info | `admin:password@` | Es un componente opcional que contiene las credenciales. El usuario y la contraseña se separan con dos puntos (`:`), y este bloque se separa del host con un signo arroba (`@`). |
| Host | `inlanefreight.com` | Indica la ubicación del recurso. Puede ser un nombre de dominio o una dirección IP. |
| Port | `:80` | Está separado del host por dos puntos (`:`). Si no se especifica, `http` usa por defecto el puerto `80` y `https` el puerto `443`. |
| Path | `/dashboard.php` | Apunta al recurso al que se accede, que puede ser un archivo o una carpeta. Si no se especifica una ruta, el servidor devuelve el índice predeterminado, por ejemplo `index.html`. |
| Query String | `?login=true` | La cadena de consulta comienza con un signo de interrogación (`?`) y contiene parámetros con clave y valor. Múltiples parámetros pueden separarse con ampersand (`&`). |
| Fragments | `#status` | Los fragmentos son procesados por el navegador del lado del cliente para ubicar secciones dentro del recurso primario, como un encabezado o sección de una página. |
