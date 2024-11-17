# Shodan-IP 

A diferencia de otras de herraminetas **SHODAN IP** no usa una **API**, permite realizar consultas avanzadas a Shodan para extraer direcciones IP y puertos asociados, filtrando resultados por parámetros específicos.

![sshodan_ip](https://github.com/user-attachments/assets/360f38e6-dd83-455c-87c8-e5677c11b1b0)

## Características

El script recibe varios argumentos para personalizar la consulta:
- `--query_base`: **Define la consulta(query) base para Shodan.**

- `--facet`: **Filtra los resultados usando "facets" específicos (e.g., port, ip, etc.).**

- `--port`: **Especifica los puertos a buscar, separados por comas.**

- `-o`, `--output`: **Archivo donde guardar los resultados (IP:PORT).**

- `-fh`,`--facet_help`: **Muestra las opciones válidas para usar "facets" desde un archivo YAML.**

## Flujo de Ejecución

A. **Validación Inicial**

- Si se usa `-fh`, `--facet_help`, lee el archivo `facets.yaml`, muestra las opciones en formato tabular y terminal.

B. **Validación de Puertos**

- Si se proporciona `--port`, verifica que sea una entrada válida (números separados por comas)

C. **Realización de Consultas**

- El script construye consultas para Shodan con base en los argumentos dados.

- Para cada consulta, envía una solicitud `GET` a la URL de Shodan, analizando la respuesta **HTML** para extraer:
    1. IP y puerto(s)
    2. Resultados relacionados (cuando no se usa el argumento `--port`).

D. **Manejo de Resultados**

- Si no se especifica un archivo de salida (`-o`, `--output`), muestra los resultados en formato JSON en la consola. De lo contrario se guardarán en un archivo de texto plano.
