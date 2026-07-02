# Resumen: Normalización de Bases de Datos

## ¿Qué es la normalización?

La **normalización** es un proceso que organiza la información en una base de datos para:

- Evitar la **redundancia** (datos repetidos).
- Mantener la **integridad** de los datos.
- Reducir errores al insertar, modificar o eliminar información.

El objetivo habitual es llegar hasta la **Tercera Forma Normal (3FN)**.

---

# Problemas de una tabla no normalizada (0FN)

Una tabla sin normalizar presenta problemas como:

- **Campos multivalor:** una misma celda contiene varios datos (por ejemplo, varios teléfonos o cursos).
- **Redundancia:** se repite la misma información en varias filas.
- **Anomalías:** modificar un dato requiere cambiarlo en muchos registros.

---

# Primera Forma Normal (1FN)

## Requisitos

- Cada celda debe contener **un solo valor** (datos atómicos).
- No deben existir grupos repetidos.
- Debe existir una **Clave Primaria (PK)**.

## Resultado

Se separan los valores múltiples en filas diferentes y cada registro queda identificado por una clave.

---

# Segunda Forma Normal (2FN)

## Requisitos

- Cumplir con la 1FN.
- Todos los atributos deben depender de la **clave primaria completa**, eliminando dependencias parciales.

## Resultado

Se divide la información en distintas tablas, por ejemplo:

- **ALUMNOS**
- **CURSOS**
- **ALUMNO_CURSO** (relación entre alumnos y cursos)

Esto evita repetir información del alumno o del curso.

---

# Tercera Forma Normal (3FN)

## Requisitos

- Cumplir con la 2FN.
- Eliminar las **dependencias transitivas**, es decir, que un atributo no dependa de otro atributo que no sea clave.

## Resultado

Se crea una tabla independiente para los profesores:

- **ALUMNOS**
- **PROFESORES**
- **CURSOS**
- **ALUMNO_CURSO**

Así, los datos de un profesor se almacenan una sola vez.

---

# Beneficios de la 3FN

- Menor redundancia de datos.
- Mayor integridad referencial.
- Menor espacio de almacenamiento.
- Mayor facilidad para actualizar la información.
- Menor posibilidad de errores e inconsistencias.

---

# Resumen de las Formas Normales

| Forma Normal | Objetivo |
|---------------|----------|
| **0FN** | Existen datos repetidos y campos con múltiples valores. |
| **1FN** | Cada celda contiene un único dato y existe una clave primaria. |
| **2FN** | Se eliminan las dependencias parciales separando la información en distintas tablas. |
| **3FN** | Se eliminan las dependencias transitivas creando tablas independientes para cada entidad. |
