# Guía rápida de flags de curl

| Flag | Nombre / Uso | Descripción | Ejemplo |
|---|---|---|---|
| `-X` | Método HTTP | Permite especificar el método HTTP a utilizar, como `GET`, `POST`, `PUT`, `PATCH` o `DELETE`. | `curl -X POST https://api.ejemplo.com/users` |
| `-H` | Header | Agrega encabezados HTTP personalizados a la solicitud. Muy útil para enviar tokens, tipos de contenido o headers de seguridad. | `curl -H "Authorization: Bearer TOKEN" https://api.ejemplo.com/profile` |
| `-d` | Data | Envía datos en el cuerpo de la solicitud. Por defecto, suele usar `POST`. | `curl -d "user=admin&pass=123" https://api.ejemplo.com/login` |
| `--data-raw` | Data sin procesamiento especial | Envía datos exactamente como se indican, útil para JSON o payloads específicos. | `curl --data-raw '{"user":"admin"}' https://api.ejemplo.com/login` |
| `--data-binary` | Data binaria | Envía datos binarios sin alterar saltos de línea o caracteres especiales. Útil para archivos o payloads exactos. | `curl --data-binary @archivo.json https://api.ejemplo.com/upload` |
| `-G` | Query string con GET | Envía los datos con `-d` como parámetros de consulta en una URL usando `GET`. | `curl -G -d "q=test" -d "page=1" https://api.ejemplo.com/search` |
| `-I` | Solo headers | Realiza una petición `HEAD` y muestra únicamente los encabezados de respuesta. | `curl -I https://ejemplo.com` |
| `-i` | Incluir headers | Muestra los encabezados de respuesta junto con el cuerpo. | `curl -i https://api.ejemplo.com/users` |
| `-v` | Verbose | Muestra información detallada de la conexión, solicitud y respuesta. Muy útil para debugging. | `curl -v https://api.ejemplo.com/users` |
| `-s` | Silent | Oculta barra de progreso y mensajes no esenciales. Útil en scripts. | `curl -s https://api.ejemplo.com/users` |
| `-o` | Output a archivo | Guarda la respuesta en un archivo específico. | `curl -o respuesta.json https://api.ejemplo.com/users` |
| `-O` | Descargar con nombre original | Descarga un archivo usando el nombre original del recurso remoto. | `curl -O https://ejemplo.com/archivo.pdf` |
| `-L` | Follow redirects | Sigue redirecciones HTTP como `301` o `302`. | `curl -L https://ejemplo.com` |
| `-k` | Insecure SSL | Permite conexiones HTTPS con certificados inválidos o autofirmados. Útil en laboratorios, no recomendado en producción. | `curl -k https://localhost:8443` |
| `-u` | Basic Auth | Envía credenciales para autenticación básica HTTP. | `curl -u admin:password https://api.ejemplo.com/admin` |
| `-b` | Cookies de entrada | Envía cookies en la solicitud. | `curl -b "sessionid=abc123" https://api.ejemplo.com/profile` |
| `-c` | Guardar cookies | Guarda las cookies recibidas en un archivo. | `curl -c cookies.txt https://api.ejemplo.com/login` |
| `-A` | User-Agent | Define un User-Agent personalizado. Útil para pruebas de comportamiento por cliente. | `curl -A "Mozilla/5.0" https://ejemplo.com` |
| `-e` | Referer | Envía un encabezado `Referer`. | `curl -e "https://google.com" https://ejemplo.com` |
| `--url` | URL explícita | Define explícitamente la URL a consultar. | `curl --url https://api.ejemplo.com/users` |
| `--request-target` | Request target | Personaliza el target de la petición HTTP. Útil para pruebas avanzadas. | `curl --request-target "*" -X OPTIONS https://ejemplo.com` |
| `--connect-timeout` | Timeout de conexión | Define el tiempo máximo para establecer conexión. | `curl --connect-timeout 5 https://api.ejemplo.com` |
| `--max-time` | Tiempo máximo total | Limita el tiempo total de ejecución de la solicitud. | `curl --max-time 10 https://api.ejemplo.com` |
| `--retry` | Reintentos | Reintenta la solicitud si falla por errores temporales. | `curl --retry 3 https://api.ejemplo.com` |
| `--proxy` | Proxy | Envía la solicitud a través de un proxy. Muy usado con Burp Suite. | `curl --proxy http://127.0.0.1:8080 https://api.ejemplo.com` |
| `--noproxy` | Excluir proxy | Evita usar proxy para ciertos hosts. | `curl --noproxy localhost https://localhost:3000` |
| `--location-trusted` | Redirecciones con credenciales | Sigue redirecciones enviando credenciales también al destino. Usar con cuidado. | `curl --location-trusted -u admin:pass https://ejemplo.com` |
| `--compressed` | Respuesta comprimida | Solicita contenido comprimido y lo descomprime automáticamente. | `curl --compressed https://ejemplo.com` |
| `--http1.1` | Forzar HTTP/1.1 | Obliga a usar HTTP/1.1. Útil para comparar comportamiento entre versiones HTTP. | `curl --http1.1 https://api.ejemplo.com` |
| `--http2` | Forzar HTTP/2 | Intenta usar HTTP/2 en la conexión. | `curl --http2 https://api.ejemplo.com` |
| `--form` / `-F` | Form multipart | Envía datos como formulario `multipart/form-data`. Útil para subir archivos. | `curl -F "file=@reporte.pdf" https://api.ejemplo.com/upload` |
| `--get` | Forzar GET con datos | Similar a `-G`, convierte datos enviados con `-d` en query parameters. | `curl --get -d "search=test" https://api.ejemplo.com/items` |
| `--head` | HEAD request | Equivalente a `-I`, solicita solo encabezados. | `curl --head https://ejemplo.com` |
| `--include` | Incluir headers | Equivalente a `-i`, muestra headers y body. | `curl --include https://api.ejemplo.com/users` |
| `--output-dir` | Directorio de salida | Define el directorio donde se guardarán archivos descargados. | `curl -O --output-dir descargas https://ejemplo.com/file.zip` |
| `--resolve` | Resolver DNS manualmente | Fuerza la resolución de un dominio hacia una IP específica. Muy útil para pruebas de virtual hosts. | `curl --resolve ejemplo.com:443:127.0.0.1 https://ejemplo.com` |
| `--cacert` | Certificado CA | Usa un certificado CA específico para validar TLS. | `curl --cacert ca.pem https://api.ejemplo.com` |
| `--cert` | Certificado cliente | Usa un certificado de cliente para autenticación mutua TLS. | `curl --cert client.pem https://api.ejemplo.com` |
| `--key` | Llave privada cliente | Usa una llave privada asociada al certificado cliente. | `curl --cert client.pem --key client.key https://api.ejemplo.com` |
| `--trace` | Trazabilidad completa | Guarda una traza detallada de la comunicación. | `curl --trace trace.txt https://api.ejemplo.com` |
| `--trace-ascii` | Trazabilidad legible | Guarda una traza en formato más legible para humanos. | `curl --trace-ascii trace.txt https://api.ejemplo.com` |
| `-w` | Write-out | Permite imprimir métricas de la solicitud, como código HTTP o tiempo de respuesta. | `curl -w "Código: %{http_code}\nTiempo: %{time_total}\n" https://api.ejemplo.com` |
