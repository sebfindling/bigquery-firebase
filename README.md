### Generador/importador datos BigQuery desde Firebase

### Instalación
1. Instalar `gcloud`: `curl https://sdk.cloud.google.com | bash`
2. Logearse con `gcloud auth login`
3. Instalar dependencias: `npm i`


### Generar columnas (una vista que contiene una columna por cada campo)
1. Especificar campos en el archivo `test_schema.json`
2. Ejecutar este comando para generar la vista
```
./node_modules/.bin/fs-bq-schema-views \
  --non-interactive \
  --project=NOMBRE_PROJECT \
  --dataset=NOMBRE_DATASET \
  --table-name-prefix=NOMBRE_PREFIJO \
  --schema-files=./test_schema.json
```
En el caso de Dreamoms: `project=dreamoms`, `dataset=users`, `table-name-prefix=users`
```
./node_modules/.bin/fs-bq-schema-views \
  --non-interactive \
  --project=dreamoms \
  --dataset=users \
  --table-name-prefix=users \
  --schema-files=./test_schema.json
```

### Importar datos anteriores de una colección
```
./node_modules/.bin/fs-bq-import-collection
```
