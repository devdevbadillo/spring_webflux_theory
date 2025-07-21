# Spring WebFlux

## Tabla de contenido

- [Traditional vs Reactive APIs](#traditional-vs-reactive-apis)
  - [Fundamentos de Spring Web MVC (Repaso)](#fundamentos-spring-web-mvc)
  - [Introducción a las APIs Reactivas](#introduccion-apis-reactivas)
  - [Comparación Directa (Caso de Uso Simple)](#comparacion-directa)
  - [Cuándo usar WebFlux vs. Web MVC](#cuando-usar-webflux-vs-web-mvc)

- [Spring Data R2DBC](#spring-data-r2dbc)
  - [Problemas de JPA/JDBC en un entorno Reactivo](#problemas-jpa-jdbc-reactive)
  - [Introducción a R2DBC](#introduccion-r2dbc)
    - [Configuración de Spring Data R2DBC](#configuracion-spring-data-r2dbc)
    - [`ReactiveCrudRepository` y `R2dbcEntityTemplate`](#reactivecrudrepository-r2dbcentitytemplate)
    - [Transacciones Reactivas](#transacciones-reactivas)
    - [Mapeo de Entidades](#mapeo-entidades-r2dbc)

- [R2DBC vs JPA/JDBC](#r2dbc-vs-jpa-jdbc)
  - [Ejemplos de Implementación Paralela](#ejemplos-implementacion-paralela)
  - [Análisis Comparativo](#analisis-comparativo-r2dbc-jpa)

- [Reactive CRUD APIs](#reactive-crud-apis)
  - [Diseño de Endpoints REST Reactivos](#diseno-endpoints-rest-reactivos)
  - [Implementación de Operaciones CRUD](#implementacion-operaciones-crud-webflux)
  - [Manejo de Respuestas HTTP](#manejo-respuestas-http-webflux)
  - [Diferencias con Spring MVC](#diferencias-spring-mvc-webflux)

- [Input Validation / Error Handling](#input-validation-error-handling)
  - [Validación Reactiva](#validacion-reactiva)
  - [Estrategias de Manejo de Errores en WebFlux](#estrategias-manejo-errores-webflux)
  - [Consideraciones Específicas de Errores Reactivos](#consideraciones-errores-reactivos)

- [WebFilter](#webfilter)
  - [Concepto de `WebFilter`](#concepto-webfilter)
  - [Implementación de `WebFilter`](#implementacion-webfilter)
  - [Casos de Uso Comunes](#casos-uso-webfilter)

- [Functional Endpoints](#functional-endpoints)
  - [Motivación](#motivacion-functional-endpoints)
  - [Conceptos Clave](#conceptos-clave-functional-endpoints)
  - [Definición de Rutas (Routing)](#definicion-rutas-functional-endpoints)
  - [Implementación de Manejadores (Handling)](#implementacion-manejadores-functional-endpoints)
  - [Ventajas y Desventajas](#ventajas-desventajas-functional-endpoints)
  - [Interoperabilidad](#interoperabilidad-functional-endpoints)

- [WebClient - Non-Blocking HTTP Client](#webclient-non-blocking-http-client)
  - [Limitaciones de `RestTemplate` y `WebClient` clásico](#limitaciones-resttemplate-webclient-clasico)
  - [Introducción a `WebClient`](#introduccion-webclient)
    - [Creación de `WebClient`](#creacion-webclient)
    - [Realización de Solicitudes HTTP](#realizacion-solicitudes-http-webclient)
    - [Manejo de Errores con `WebClient`](#manejo-errores-webclient)
    - [Configuración Avanzada](#configuracion-avanzada-webclient)
    - [Uso en Microservicios](#uso-microservicios-webclient)

- [Streaming](#streaming-webflux)
  - [Concepto de Streaming en HTTP](#concepto-streaming-http)
  - [Retornar `Flux<T>` directamente desde los controladores](#retornar-flux-webflux)
  - [Casos de Uso de Streaming](#casos-uso-streaming-webflux)
  - [Backpressure en Streaming](#backpressure-streaming-webflux)

- [Server Sent Events / SSE](#server-sent-events-sse)
  - [Introducción a SSE](#introduccion-sse)
  - [Implementación de SSE en Spring WebFlux](#implementacion-sse-webflux)
  - [Ejemplos de Aplicación](#ejemplos-aplicacion-sse)
  - [Comparación con WebSockets](#comparacion-websockets-sse)

- [Performance Optimization](#performance-optimization)
  - [Profileado de Aplicaciones WebFlux](#profileado-aplicaciones-webflux)
  - [Identificación de Cuellos de Botella](#identificacion-cuellos-botella-webflux)
  - [Estrategias de Optimización](#estrategias-optimizacion-webflux)
  - [Métricas y Observabilidad](#metricas-observabilidad-webflux)

- [Reactive Microservices](#final-project-reactive-microservices)
  - [Diseño de Arquitectura de Microservicios Reactivos](#diseno-arquitectura-microservicios-reactivos)
  - [Implementación de Microservicios End-to-End](#implementacion-microservicios-end-to-end)
    - [Patrones de Resiliencia en Microservicios Reactivos](#patrones-resiliencia-microservicios-reactivos)
    - [Dockerización y Despliegue](#dockerizacion-despliegue-microservicios)
