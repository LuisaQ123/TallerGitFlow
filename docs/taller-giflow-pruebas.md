# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

### RF-03 Inscripción a Evento

Un estudiante podrá inscribirse a un evento solo si:

Está registrado.
El evento tiene cupos disponibles.
No está previamente inscrito.
Si alguna condición no se cumple, el sistema no debe permitir la inscripción.

## 3. Tecnicas de Prueba Aplicadas

### RF-03 Inscripción a Evento

Para este requerimiento vamos a usar **Tabla de Decisión**. 

El requerimiento contiene múltiples condiciones booleanas que determinan una acción. La tabla de decisión permite analizar todas las combinaciones posibles y validar el comportamiento del sistema.

## 4. Casos de Prueba Diseñados

### RF-03 Inscripción a Evento

| Condiciones                      | R1 | R2 | R3 |R4|
|----------------------------------|----|----|----|----|
| Esta regristrado                 | Si | NO |NO  | SI
| El evento tiene cupos disponibles| SI | SI |NO  | NO
| No esta previamente escrito      | SI | SI |NO  | NO
| Permitir Incripcion              | X  |    |    |
| No permitir Incripcion           |    |X   | X  | X

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
