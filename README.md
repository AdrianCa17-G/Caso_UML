#  Sistema de Biblioteca – Documentación UML

![](https://github.com/AdrianCa17-G/Caso_UML/blob/main/uml_biblioteca_use_case.png)

##  Descripción del sistema

El presente proyecto modela un sistema de biblioteca mediante un diagrama de casos de uso UML, con el fin de representar las interacciones entre los actores y las funcionalidades principales del sistema. Este diseño permite comprender el comportamiento general del sistema y sus procesos clave.

---

##  Objetivo

Modelar los procesos principales de gestión bibliotecaria, incluyendo búsqueda, préstamo, devolución, renovación de libros y pago de multas, asegurando una correcta interacción entre los actores involucrados.

---

##  Actores del sistema

* **Usuario (lector):** Interactúa con el sistema para consultar información y gestionar préstamos.
* **Bibliotecario:** Supervisa y valida las operaciones de préstamo y devolución.
* **Sistema de pagos (externo):** Procesa las transacciones relacionadas con multas.

---

##  Casos de uso

* Buscar libro
* Consultar disponibilidad
* Solicitar préstamo
* Devolver libro
* Renovar préstamo
* Pagar multa

---

##  Relaciones entre casos de uso

###  <<include>>

El caso de uso **Solicitar préstamo** incluye obligatoriamente **Consultar disponibilidad**, ya que es necesario verificar la existencia del libro antes de completar el proceso.

###  <<extend>>

El caso de uso **Pagar multa** extiende a **Devolver libro**, debido a que solo se ejecuta en situaciones específicas donde existe retraso en la devolución.

---

##  Especificación de caso de uso principal

###  ID: CU-01

###  Nombre: Solicitar préstamo

* **Actores:** Usuario, Bibliotecario
* **Propósito:** Registrar el préstamo de un libro al usuario
* **Descripción:** El usuario selecciona un libro, el sistema valida disponibilidad, verifica condiciones y registra el préstamo.
* **Precondiciones:**

  * Usuario autenticado
  * Cuenta activa
  * Libro registrado en el sistema
  * Disponibilidad verificada
  * Sin sanciones activas
* **Postcondiciones:**

  * Préstamo registrado en la base de datos
  * Libro marcado como no disponible
  * Historial actualizado
* **Extensiones síncronas:**

  *  Libro no disponible → operación bloqueada
  *  Usuario sancionado → préstamo denegado
  *  Error del sistema → proceso cancelado

---


##  Herramientas utilizadas

* Lucidchart
* GitHub

---
