# cinemapedia_220262

---

## 🎬 Práctica 07: Implementación de Actores que participan en las Películas (Movie Actors)

### **Nombre del Estudiante:** [Esperanza Cruz Galindo]
### **Matrícula:** [220262]
### **Asignatura:** Desarrollo de Aplicaciones Móviles
### **Docente:** [Marco Antonio Ramírez Hérnandez]
---

## 📝 Descripción General de la Práctica

Esta práctica da continuidad al desarrollo del proyecto **Cinemapedia**, una aplicación móvil para la consulta de información de películas. El objetivo principal es **incorporar la funcionalidad de detalle de la película**, que ahora incluye información exhaustiva como el póster, el título, la calificación, la descripción y, crucialmente, la **lista de los actores participantes** (**Cast**).

Se realizaron modificaciones en las capas de **Dominio**, **Data**, y **Presentación** para consumir el *endpoint* de actores y mostrar esta nueva información de manera visual y funcional.

---

## ⚙️ Actividades Realizadas

A continuación, se detalla la implementación de cada punto solicitado:

### 1. Clonación y Estructura

* Se creó repositorio `Practica-07` a partir del proyecto anterior, manteniendo la estructura base de **Cinemapedia**.

### 2. Creación de Entidad y Modelo de Actores

* Se definió la **Entidad `Actor`** en la capa de **Dominio** para representar la información relevante del actor (e.g., `id`, `name`, `profilePath`, `character`).
* Se creó el **Modelo `CastModel`** en la capa de **Data** para mapear la respuesta del *API* (JSON) a la Entidad `Actor`.

### 3. Implementación del Datasource y Mappers

* Se modificó el **`TheMovieDbDatasource`** para incluir el método que realiza la petición HTTP al *endpoint* `/movie/{movie_id}/credits` para obtener la lista de actores (`Cast`).
* Se implementó el **`CastMapper`** para realizar la deserialización correcta y transformar el `CastModel` (Data) en la Entidad `Actor` (Dominio).

### 4. Implementación de Providers con Riverpod v.3

* Se creó un nuevo **Provider** (e.g., `castByMovieProvider`) utilizando **Riverpod** para gestionar el estado de la lista de actores por cada película. Este proveedor es responsable de llamar al repositorio y almacenar la lista de `Actor`s de manera eficiente.

### 5. Configuración del GoRouter

* Se actualizaron las rutas en **GoRouter** para manejar la navegación desde la vista principal de listados hasta la **Vista de Detalle de la Película**, asegurando que el *ID* de la película sea pasado como parámetro.

### 6. Elementos Visuales: Detalles de la Película

* Se diseñó y se implementó la **Vista de Detalle de la Película** (`MovieScreen`), la cual presenta:
    * **Poster** (`Image`).
    * **Título** y **Calificación** (`Rating`).
    * **Descripción** (*Overview*).

### 7. Elementos Visuales: Lista de Actores

* Se desarrolló un *widget* específico (e.g., `CastListWidget`) que se integra en la `MovieScreen`.
* Este *widget* muestra la lista de actores en un formato horizontal y deslizable (`ListView.builder` o similar), incluyendo la foto del actor y su nombre/personaje.


## 📸 Capturas de Pantalla de la Aplicación

A continuación, se presentan las capturas de pantalla que demuestran la funcionalidad implementada.

### A. Vista de Detalle de la Película (Movie Screen)
Muestra la información completa (póster, título, descripción) de una película seleccionada.

![Texto Alternativo](/captura1.png)

---

### B. Secciones de Actores (Cast Section)
Muestra la lista de actores participantes, generalmente en una sección deslizable dentro de la vista de detalle.

![Texto Alternativo](/captura2.png)

---


## 🔗 Enlace al Repositorio

El código fuente completo de esta práctica se encuentra disponible en:






## 🔍 Práctica 08: Implementación de Búsquedas (Search Delegate)


---

## 📝 Descripción General de la Práctica 08

El objetivo de esta práctica es añadir la funcionalidad de **búsqueda de películas** a **Cinemapedia**. Para lograrlo, se implementará el **Search Delegate** de Flutter, que proporciona una interfaz de búsqueda moderna. Se consumirá el *endpoint* de búsqueda de la *API* de TheMovieDB, incorporando buenas prácticas como el uso de un **Debouncer** para optimizar las peticiones y **Streams** para manejar el flujo de entrada de texto del usuario.

---

## ⚙️ Actividades a Realizar (Práctica 08)

### 1. Clonación y Estructura

* Clonar el Proyecto anterior o crear el ramal pertinente (`Practica-08`).

### 2. Implementación del Search Delegate

* Implementar la clase que extiende de **`SearchDelegate`** como motor de búsquedas y definir los mecanismos de visualización de resultados (e.g., `buildSuggestions`, `buildResults`).

### 3. Modificación de Datasources, Repositorios y Providers

* Modificar los **Datasources** para permitir el consumo del *endpoint* de búsquedas (`/search/movie`).
* Modificar los **Repositorios** y crear los **Providers** necesarios para vincular los resultados de la búsqueda con la interfaz de usuario.

### 4. Implementación del Debouncer y Streams

* Implementar un **`Debouncer`** para esperar un tiempo posterior al tipado de la consulta antes de enviar la petición al *API*, optimizando los recursos.
* Implementar **Streams** (o `StreamControllers`) para controlar el flujo de escritura en la caja de búsqueda y notificar al **Provider** de búsqueda.

### 5. Estilización y Widgets

* Implementar la estilización de los resultados a través de los **Builders** para mostrar *widgets* (e.g., tarjetas de película con póster y título).
* Aplicar buenas prácticas para la **reutilización de *widgets* (DRY)**, especialmente para la presentación de los resultados de búsqueda.

### Capturas 
Muestra la lista de actores participantes, generalmente en una sección deslizable dentro de la vista de detalle.

![captura](/img%203.png)
![captura](//img%204.png)


---

## 🔗 Enlace al Repositorio

El código fuente completo de la Práctica 07 y la base para la Práctica 08 se encuentra disponible en:

[https://github.com/Dulce990/DMI_Practica07_220262](https://github.com/Dulce990/DMI_Practica07_220262)