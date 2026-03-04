# Documento de Pruebas

## 1. Descripcion del Sistema

El sistema permite gestionar el registro de estudiantes y su participacion en eventos, los estudiantes pueden registrarse siempre que su edad este entre 16 y 65 años y que tengan un codigo de estudiante valido. Tambien pueden inscribirse a eventos disponibles, siempre que existan cupos y no esten previamente inscritos en el evento.

## 2. Requerimientos a Evaluar

### RF-01 Registro de Estudiante (Edad)

El sistema debe permitir el registro de estudiantes cuya edad esté entre 16 y 65 años inclusive.

### RF-02 Código de Estudiante

El código del estudiante debe:
Tener exactamente 8 caracteres.
Iniciar con la letra “E”.
Los 7 caracteres restantes deben ser numéricos.

### RF-03 Inscripción a Evento

Un estudiante podrá inscribirse a un evento solo si:

Está registrado.
El evento tiene cupos disponibles.
No está previamente inscrito.
Si alguna condición no se cumple, el sistema no debe permitir la inscripción.

## 3. Tecnicas de Prueba Aplicadas

### RF-01 Registro de Estudiante (Edad)

Para este requerimiento decidimos usar la prueba **"Analisis de Valor Limite (BVA)"**. Porque la entrada (Edad) tiene un rango numerico definido, siendo en este caso 16 y 65.

### RF-02 Código de Estudiante

La tecnica de prueba que hemos selecionado es **Partición de equivalencia**, ya que tenemos un valor especifico valido: el codigo debe tener 8 caracteres, debe iniciar con la letra E, y que los 7 caracteres restantes sean númericos, así que cualquiera que se salga del molde es una contraseña invalida. 

### RF-03 Inscripción a Evento

Para este requerimiento vamos a usar **Tabla de Decisión**. El requerimiento contiene múltiples condiciones booleanas que determinan una acción. La tabla de decisión permite analizar todas las combinaciones posibles y validar el comportamiento del sistema.

## 4. Casos de Prueba Diseñados

### RF-01 Registro de Estudiante (Edad)

| Caso | Edad |            Limite            | Resultado esperado |
|------|------|------------------------------|--------------------|
|  L1  |  15  | Justo debajo del limite      | Invalido |
|  L2  |  16  | El valor del limite inferior | Valido |
|  L3  |  17  | Justo arriba del limite      | Valido |
|  L4  |  64  | Justo debajo del limite      | Valido |
|  L5  |  65  | El valor del limite superior | Valido |
|  L6  |  66  | Justo arriba del limite      | Invalido |

### RF-02 Código de Estudiante

| Criterio                     | Clases Válidas (V)        | Clases Inválidas (I)                                      |
|------------------------------|---------------------------|------------------------------------------------------------|
| Longitud de la contraseña    | V1: 8 caracteres          | I1: Menos de 8 caracteres                                  |
| Letra inicial                | V2: Contiene "E"          | I2: Diferente de "E"                                       |
| Caracteres restantes         | V3: 7 dígitos numéricos   | I3: Contiene letras o caracteres especiales después de la primera posición |


| ID     | Descripción                                                                 | Precondiciones                                      | Datos de Prueba | Resultado Esperado                                      | Estado |
|--------|----------------------------------------------------------------------------|----------------------------------------------------|----------------|----------------------------------------------------------|--------|
| CP-01  | Verificar que la contraseña válida cumple longitud, letra inicial y formato | El usuario se encuentra en el formulario de registro | E1234567       | El sistema acepta la contraseña y permite continuar     | Valido |
| CP-02  | Verificar que se rechace contraseña con menos de 8 caracteres              | El usuario se encuentra en el formulario de registro | E123456        | El sistema muestra mensaje: "Debe tener 8 caracteres"   | Invallido |
| CP-03  | Verificar que se rechace contraseña que no inicia con "E"                  | El usuario se encuentra en el formulario de registro | A1234567       | El sistema muestra mensaje: "Debe iniciar con E"        | Invalido|
| CP-04  | Verificar que se rechace contraseña con letras después de la primera posición | El usuario se encuentra en el formulario de registro | E12345A7       | El sistema muestra mensaje: "Solo se permiten números después de la primera posición" | Pendiente |
| CP-05  | Verificar que se rechace contraseña con caracteres especiales              | El usuario se encuentra en el formulario de registro | E12345#7       | El sistema muestra mensaje de formato inválido          | Invalido |

### RF-03 Inscripción a Evento

| Condiciones                      | R1 | R2 | R3 |R4|
|----------------------------------|----|----|----|----|
| Esta regristrado                 | Si | NO |NO  | SI
| El evento tiene cupos disponibles| SI | SI |NO  | NO
| No esta previamente escrito      | SI | SI |NO  | NO
| Permitir Incripcion              | X  |    |    |
| No permitir Incripcion           |    |X   | X  | X

## 5. Trazabilidad

**TABLA DE TRAZABILIDAD**

| HU   | RF | CASO DE PRUEBA |ESTADO ||
|------|----|----------------|-------|----|
| HU-01| Registro de estudiante   |     verificar que el sistema registre estudianes cuya edad este entre 16  65 años.    |    pendiente   |  
| HU-02| Codigo de estudiante  |        verificar que el codigo de estudiante tenga 8 caracteres , incie con la letra e , y que los 7 caracteres despues de la letra e sean numericos.        |     pendiente  | 
| HU-03|   Incripcion a evento |          verificar que el estudiante pueda incribirse en un evento , si el estudiante cumple las todas las condiciones puede escribirse de resto el sistema no debe de permitir la inscripcion    |     pendiente  | 

## 6. Gestion de Versiones (GitFlow)

Usamos el GitFlow convencional, iniciamos el repositorio con una rama **"main"** de la cual creamos la **"develop"** y a partir de ella cada uno creo una rama **"feature"** para cada requerimiento del taller. Por lo tanto el flujo que seguimos fue: main **->** develop **->** feature. Cuando hicimos Pull request a la rama develop, hubieron varios conflictos por las lineas superpuestas y tuvimos que solucionarlos organizando cada texto uno luego del otro, siguiendo el orden del taller. 

