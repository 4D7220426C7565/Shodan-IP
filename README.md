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

