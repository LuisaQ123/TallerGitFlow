# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

### RF-02 Código de Estudiante

El código del estudiante debe:
Tener exactamente 8 caracteres.
Iniciar con la letra “E”.
Los 7 caracteres restantes deben ser numéricos.

## 3. Tecnicas de Prueba Aplicadas

La tecnica de prueba que hemos selecionado es **Partición de equivalencia**, ya que tenemos un valor especifico valido: el codigo debe tener 8 caracteres, debe inicar con la letra E, y que los 7 caracteres restantes sean númericos, así que cualquiera que se salga del molde es una contraseña invalida. 

## 4. Casos de Prueba Diseñados
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

  

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
