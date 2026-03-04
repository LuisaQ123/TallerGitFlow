# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

### RF-01 Registro de Estudiante (Edad)

El sistema debe permitir el registro de estudiantes cuya edad esté entre 16 y 65 años inclusive.

## 3. Tecnicas de Prueba Aplicadas

### RF-01 Registro de Estudiante (Edad)

Para este requerimiento decidimos usar la prueba **"Analisis de Valor Limite (BVA)"**. Porque la entrada (Edad) tiene un rango numerico definido, siendo en este caso 16 y 65.

## 4. Casos de Prueba Diseñados

| Caso | Edad |            Limite            | Resultado esperado |
|------|------|------------------------------|--------------------|
|  L1  |  15  | Justo debajo del limite      | Invalido |
|  L2  |  16  | El valor del limite inferior | Valido |
|  L3  |  17  | Justo arriba del limite      | Valido |
|  L4  |  64  | Justo debajo del limite      | Valido |
|  L5  |  65  | El valor del limite superior | Valido |
|  L6  |  66  | Justo arriba del limite      | Invalido |

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)

