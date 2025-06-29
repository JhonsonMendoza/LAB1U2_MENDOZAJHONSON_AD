**DEPARTAMENTO:** Ciencias de la Computación  
**CARRERA:** Tecnologías de la Información  
**ASIGNATURA:** Aplicaciones Distribuidas  
**NIVEL:** 7° Nivel  
**FECHA:** 29 de Junio del 2025  
**DOCENTE:** Ing. Paulo Galarza, Mgs.  
**PRÁCTICA N°:** 1  
**CALIFICACIÓN:** 10/10  
**Título o tema de la práctica:** Construcción de una API RESTful con base de datos NoSQL utilizando Express.js y Mongoose  
**Nombre del estudiante:** Jhonson Mendoza  

---

## RESUMEN

En esta práctica de laboratorio se desarrolló una API RESTful utilizando Node.js con el framework Express y MongoDB como base de datos NoSQL. Se empleó el ORM Mongoose para facilitar la creación de esquemas de datos, validaciones y operaciones CRUD. El objetivo principal fue integrar estos componentes para construir una API que permita gestionar registros de cursos. Durante el desarrollo se configuró el entorno de trabajo, se implementaron controladores, rutas y se probaron los endpoints mediante Postman. Se documentaron los resultados obtenidos y se realizaron pruebas exitosas. Esta práctica permitió afianzar conocimientos sobre la arquitectura cliente-servidor, la estructura REST y el manejo de base de datos orientada a documentos.

**Palabras clave:** API REST, MongoDB, Mongoose

---

## INTRODUCCIÓN

La evolución del desarrollo web ha llevado al uso de arquitecturas basadas en servicios, siendo las API RESTful una de las más utilizadas por su sencillez y escalabilidad. En esta práctica se aborda la construcción de una API RESTful utilizando Express.js, una de las bibliotecas más populares en Node.js para el desarrollo backend, junto con MongoDB, una base de datos NoSQL altamente eficiente. Se emplea Mongoose como ORM para facilitar la interacción entre la aplicación y la base de datos. La práctica enfatiza en el diseño modular, implementación de operaciones CRUD, y validación de la funcionalidad mediante herramientas de prueba.

---

## OBJETIVOS

**Objetivo general:**  
Desarrollar una API RESTful utilizando Express.js, MongoDB y Mongoose para implementar operaciones CRUD sobre un modelo de datos.

**Objetivos específicos:**  
- Configurar un entorno de desarrollo con soporte para Docker, MongoDB y Node.js.  
- Implementar rutas y controladores RESTful que permitan la gestión completa de datos mediante operaciones CRUD.

---

## MARCO TEÓRICO

Una API **RESTful** (Representational State Transfer) es una arquitectura que permite la comunicación entre sistemas de software de manera flexible, usando el protocolo HTTP. Esta arquitectura se basa en recursos identificables mediante URIs y utiliza los métodos HTTP estándar como GET, POST, PUT y DELETE. REST se ha convertido en el estándar para la creación de servicios web debido a su simplicidad y compatibilidad con casi cualquier lenguaje de programación y entorno.

**Express.js** es un framework minimalista de Node.js que permite el manejo de rutas, middleware y respuestas HTTP de forma sencilla. Facilita la creación de servidores web y APIs, siendo ampliamente utilizado por su rendimiento y flexibilidad.

**MongoDB** es una base de datos NoSQL orientada a documentos que almacena la información en estructuras JSON similares a objetos, llamadas BSON. Esto proporciona una gran flexibilidad en la gestión de datos no estructurados o semi-estructurados, lo cual resulta muy adecuado para aplicaciones modernas y altamente escalables.

**Mongoose** es una herramienta de modelado de objetos de datos para MongoDB y Node.js. Proporciona una solución elegante para manejar esquemas de datos, incluyendo validaciones, relaciones entre datos, middlewares y hooks. Usar Mongoose ayuda a mantener un código limpio y seguro, con definiciones claras de modelos de datos.

Comprender estos conceptos es esencial para desarrollar sistemas robustos que conecten el backend con una base de datos, permitiendo una interacción eficiente con los datos y manteniendo buenas prácticas de diseño.
---

## DESCRIPCIÓN DEL PROCEDIMIENTO

La práctica se llevó a cabo mediante una serie de pasos que permitieron construir de manera progresiva una API RESTful funcional. Inicialmente, se creó el entorno de trabajo utilizando Node.js y Express como base para el servidor. Se utilizó el gestor de paquetes npm para instalar las dependencias necesarias: express, mongoose, y nodemon para la ejecución automática en desarrollo.

Posteriormente, se configuró Docker mediante un archivo docker-compose.yml para levantar los servicios de MongoDB y Mongo Express. Esto permitió tener una base de datos funcional y una interfaz gráfica para su administración. Se creó el archivo db.js, encargado de manejar la conexión con la base de datos, asegurando que se pudiera interactuar correctamente desde el backend.

Se definió el modelo Course.js con Mongoose, donde se declararon atributos como title, description, numberOfTopics y publishedAt, además de agregar validaciones de tipo, longitud y rango de valores. Esto garantizó que los datos insertados cumplieran ciertos estándares antes de ser almacenados.

A continuación, se desarrollaron los controladores (courseController.js) para definir la lógica de cada operación CRUD: crear, obtener, actualizar y eliminar cursos. Se implementaron las rutas correspondientes en courseRoutes.js, y se integraron al archivo principal index.js, donde también se incluyeron los middlewares necesarios.

Finalmente, se inició el servidor con node src/index.js, y se realizaron pruebas utilizando Postman para verificar el correcto funcionamiento de cada endpoint. Se documentaron las respuestas obtenidas y se tomaron capturas de pantalla como evidencia de los resultados

## ANÁLISIS DE RESULTADOS
Durante las pruebas realizadas con Postman, se comprobó que la API RESTful respondía de manera correcta a cada solicitud HTTP. La inserción de datos mediante el método POST permitió verificar la integración exitosa del frontend con la base de datos. El listado de cursos mediante GET devolvió los documentos almacenados, mostrando que la estructura de datos definida en el modelo se estaba respetando.

Al realizar peticiones PUT, se observaron los cambios inmediatos en la base de datos, evidenciando el correcto manejo del estado del recurso. Las operaciones DELETE permitieron comprobar la eliminación física del documento. Cada una de estas acciones fue reflejada instantáneamente en la interfaz de Mongo Express.

Se detectó que las validaciones definidas en el esquema se ejecutaban correctamente, como la longitud mínima de la descripción y el rango permitido para el número de temas. Esto garantiza la calidad de los datos almacenados.

Cada endpoint fue verificado mediante Postman. Las operaciones POST, GET, PUT y DELETE funcionaron correctamente. Se validaron restricciones de longitud, valores numéricos, y requerimientos obligatorios desde el modelo Mongoose.

Las pruebas demostraron que la API maneja correctamente las solicitudes y respuestas HTTP. La integración con Mongo Express permitió visualizar los documentos en tiempo real.

Descripción: Creación de curso desde Postman usando el método POST.

![Creación de curso desde Postman usando el método POST.](https://imgur.com/BMzOdyt.png)

**Figura 1.** Registro de un curso usando POST. Mendoza Jhonson  

Descripción: Visualización de los cursos creados con GET.

![Visualización de los cursos creados con GET.](https://imgur.com/OmT3WYQ.png)

**Figura 2.** Consulta de cursos con GET. Mendoza Jhonson  

Descripción: Actualización de un curso con PUT desde Postman.

![Actualización de un curso con PUT desde Postman.](https://imgur.com/hz42ZGP.png)

**Figura 3.** Actualización de curso con PUT. Mendoza Jhonson  

Descripción: Eliminación de curso con DELETE desde Postman.

![Eliminación de curso con DELETE desde Postman.](https://imgur.com/sC3hCaO.png)

**Figura 4.** Eliminación de curso. Mendoza Jhonson  

Descripción: Vista de los documentos creados en Mongo Express.

![Vista de los documentos creados en Mongo Express.](https://imgur.com/sjfssvj.png)

**Figura 5.** Visualización de datos en Mongo Express. Mendoza Jhonson

---

## GRÁFICOS O FOTOGRAFÍAS
![Vista general de datos en Mongo Express.](https://imgur.com/lZQTfpZ.png)

**Figura 6.** Levantamiento del contenedor de para mongo. Mendoza Jhonson  

![Estructura del proyecto en VS Code.](https://imgur.com/s9PST2e.png)

**Figura 7.** Estructura del proyecto en VS Code. Mendoza Jhonson

![Ejecución del backend.](https://imgur.com/5BnEWFF.png)

**Figura 8.** Ejecución del backend. Mendoza Jhonson

---

## DISCUSIÓN

Los resultados obtenidos reflejan la efectividad del uso conjunto de Express, MongoDB y Mongoose en el desarrollo backend moderno. Cada componente cumple una función clave: Express facilita el enrutamiento HTTP y la construcción de servidores, MongoDB ofrece flexibilidad en el almacenamiento de documentos, y Mongoose permite estructurar y validar los datos.

Uno de los principales beneficios observados es la posibilidad de definir validaciones a nivel de modelo, lo que evita errores de lógica o estructura antes de que los datos lleguen a la base de datos. El uso de Docker en el despliegue del entorno garantiza portabilidad y facilita el trabajo colaborativo, al evitar diferencias entre configuraciones locales.

Además, el enfoque modular adoptado en la organización del código mejora la mantenibilidad del sistema. Las rutas separadas por recurso, controladores reutilizables y modelos bien definidos siguen principios de diseño recomendados, como la responsabilidad única y la separación de preocupaciones.

El uso de Postman como herramienta de pruebas permitió verificar el correcto funcionamiento de todos los endpoints, y su combinación con Mongo Express facilitó la observación de los efectos inmediatos de cada operación en la base de datos. La práctica también permitió al estudiante adquirir una comprensión más clara sobre cómo se comunican los distintos componentes del backend, sentando las bases para proyectos más complejos que integren autenticación, relaciones entre colecciones y despliegue en la nube.

## LINK DEL REPOSITORIO: 
Enlace a repositorio remoto github: https://github.com/JhonsonMendoza/LAB1U2_MENDOZAJHONSON_AD.git

---

## CONCLUSIONES

1. La práctica permitió consolidar conocimientos fundamentales en el desarrollo backend moderno, permitiendo al estudiante familiarizarse con la arquitectura REST, el uso de rutas HTTP y la integración efectiva de herramientas como Express y Mongoose. Además, se reforzó el concepto de modularización del código mediante la separación de modelos, controladores y rutas.

2. El uso de Docker para la implementación de la base de datos MongoDB y la interfaz Mongo Express demostró ser una práctica altamente efectiva para crear entornos de desarrollo aislados, portables y fácilmente replicables. Esto es de gran utilidad en proyectos reales donde se necesita trabajar en equipos de desarrollo sin depender de configuraciones locales específicas.

3. La experiencia permitió desarrollar una API RESTful completamente funcional, con operaciones CRUD correctamente implementadas y validadas mediante Postman. Se evidenció que el uso de Mongoose como ORM no solo simplifica la interacción con MongoDB, sino que también ofrece un mecanismo eficiente de validación y estructuración de datos, aumentando la robustez y mantenibilidad del sistema creado.

---

## BIBLIOGRAFÍA

- MongoDB Documentation. https://www.mongodb.com/docs/manual/  
- Express.js Guide. https://expressjs.com/  
- Mongoose Documentation. https://mongoosejs.com/  
- Docker Docs. https://docs.docker.com/  
- Postman Learning Center. https://learning.postman.com/