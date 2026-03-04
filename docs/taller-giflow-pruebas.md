# Documento de Pruebas

## 1. Descripcion del Sistema

El sistema permite gestionar el registro de estudiantes y su participacion en eventos, los estudiantes pueden registrarse siempre que su edad este entre 16 y 65 años y que tengan un codigo de estudiante valido. Tambien pueden inscribirse a eventos disponibles, siempre que existan cupos y no esten previamente inscritos en el evento.

## 2. Requerimientos a Evaluar

## 3. Tecnicas de Prueba Aplicadas

## 4. Casos de Prueba Diseñados

## 5. Trazabilidad

**TABLA DE TRAZABILIDAD**

| HU   | RF | CASO DE PRUEBA |ESTADO ||
|------|----|----------------|-------|----|
| HU-01| Registro de estudiante   |     verificar que el sistema registre estudianes cuya edad este entre 16  65 años.    |    pendiente   |  
| HU-02| Codigo de estudiante  |        verificar que el codigo de estudiante tenga 8 caracteres , incie con la letra e , y que los 7 caracteres despues de la letra e sean numericos.        |     pendiente  | 
| HU-03|   Incripcion a evento |          verificar que el estudiante pueda incribirse en un evento , si el estudiante cumple las todas las condiciones puede escribirse de resto el sistema no debe de permitir la inscripcion    |     pendiente  | 

## 6. Gestion de Versiones (GitFlow)

Usamos el GitFlow convencional, iniciamos el repositorio con una rama **"main"** de la cual creamos la **"develop"** y a partir de ella cada uno creo una rama **"feature"** para cada requerimiento del taller. Por lo tanto el flujo que seguimos fue: main **->** develop **->** feature. Cuando hicimos Pull request a la rama develop, hubieron varios conflictos por las lineas superpuestas y tuvimos que solucionarlos organizando cada texto uno luego del otro, siguiendo el orden del taller. 
