# Spring WebFlux

## Tabla de contenido

- [Traditional vs Reactive APIs](#traditional-vs-reactive-apis)
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

- [Microservicios Reactivos](#final-project-reactive-microservices)
  - [Diseño de Arquitectura de Microservicios Reactivos](#diseno-arquitectura-microservicios-reactivos)
  - [Implementación de Microservicios End-to-End](#implementacion-microservicios-end-to-end)
    - [Patrones de Resiliencia en Microservicios Reactivos](#patrones-resiliencia-microservicios-reactivos)
    - [Dockerización y Despliegue](#dockerizacion-despliegue-microservicios)


<a id="traditional-vs-reactive-apis"></a>
## Traditional vs Reactive APIs

<a id="introduccion-apis-reactivas"></a>
### Introducción a las APIs Reactivas

<a id="comparacion-directa"></a>
### Comparación Directa (Caso de Uso Simple)

<a id="cuando-usar-webflux-vs-web-mvc"></a>
### Cuándo usar WebFlux vs. Web MVC

<a id="spring-data-r2dbc"></a>
## Spring Data R2DBC

<a id="problemas-jpa-jdbc-reactive"></a>
### Problemas de JPA/JDBC en un entorno Reactivo

<a id="introduccion-r2dbc"></a>
### Introducción a R2DBC

<a id="configuracion-spring-data-r2dbc"></a>
### Configuración de Spring Data R2DBC

<a id="reactivecrudrepository-r2dbcentitytemplate"></a>
### `ReactiveCrudRepository` y `R2dbcEntityTemplate`

<a id="transacciones-reactivas"></a>
### Transacciones Reactivas

<a id="mapeo-entidades-r2dbc"></a>
### Mapeo de Entidades

<a id="r2dbc-vs-jpa-jdbc"></a>
## R2DBC vs JPA/JDBC

<a id="ejemplos-implementacion-paralela"></a>
### Ejemplos de Implementación Paralela

<a id="analisis-comparativo-r2dbc-jpa"></a>
### Análisis Comparativo

<a id="reactive-crud-apis"></a>
## Reactive CRUD APIs

<a id="diseno-endpoints-rest-reactivos"></a>
### Diseño de Endpoints REST Reactivos

<a id="implementacion-operaciones-crud-webflux"></a>
### Implementación de Operaciones CRUD

<a id="manejo-respuestas-http-webflux"></a>
### Manejo de Respuestas HTTP

<a id="diferencias-spring-mvc-webflux"></a>
### Diferencias con Spring MVC

<a id="input-validation-error-handling"></a>
## Input Validation / Error Handling

<a id="validacion-reactiva"></a>
### Validación Reactiva

<a id="estrategias-manejo-errores-webflux"></a>
### Estrategias de Manejo de Errores en WebFlux

<a id="consideraciones-errores-reactivos"></a>
### Consideraciones Específicas de Errores Reactivos

<a id="webfilter"></a>
## WebFilter

<a id="concepto-webfilter"></a>
### Concepto de `WebFilter`

<a id="implementacion-webfilter"></a>
### Implementación de `WebFilter`

<a id="casos-uso-webfilter"></a>
### Casos de Uso Comunes

<a id="functional-endpoints"></a>
## Functional Endpoints

<a id="motivacion-functional-endpoints"></a>
### Motivación

<a id="conceptos-clave-functional-endpoints"></a>
### Conceptos Clave

<a id="definicion-rutas-functional-endpoints"></a>
### Definición de Rutas (Routing)

<a id="implementacion-manejadores-functional-endpoints"></a>
### Implementación de Manejadores (Handling)

<a id="ventajas-desventajas-functional-endpoints"></a>
### Ventajas y Desventajas

<a id="interoperabilidad-functional-endpoints"></a>
### Interoperabilidad

<a id="webclient-non-blocking-http-client"></a>
## WebClient - Non-Blocking HTTP Client

<a id="limitaciones-resttemplate-webclient-clasico"></a>
### Limitaciones de `RestTemplate` y `WebClient` clásico

<a id="introduccion-webclient"></a>
### Introducción a `WebClient`

<a id="creacion-webclient"></a>
### Creación de `WebClient`

<a id="realizacion-solicitudes-http-webclient"></a>
### Realización de Solicitudes HTTP

<a id="manejo-errores-webclient"></a>
### Manejo de Errores con `WebClient`

<a id="configuracion-avanzada-webclient"></a>
### Configuración Avanzada

<a id="uso-microservicios-webclient"></a>
### Uso en Microservicios

<a id="streaming-webflux"></a>
## Streaming

<a id="concepto-streaming-http"></a>
### Concepto de Streaming en HTTP

<a id="retornar-flux-webflux"></a>
### Retornar `Flux<T>` directamente desde los controladores

<a id="casos-uso-streaming-webflux"></a>
### Casos de Uso de Streaming

<a id="backpressure-streaming-webflux"></a>
### Backpressure en Streaming

<a id="server-sent-events-sse"></a>
## Server Sent Events / SSE

<a id="introduccion-sse"></a>
### Introducción a SSE

<a id="implementacion-sse-webflux"></a>
### Implementación de SSE en Spring WebFlux

<a id="ejemplos-aplicacion-sse"></a>
### Ejemplos de Aplicación

<a id="comparacion-websockets-sse"></a>
### Comparación con WebSockets

<a id="performance-optimization"></a>
## Performance Optimization

<a id="profileado-aplicaciones-webflux"></a>
### Profileado de Aplicaciones WebFlux

<a id="identificacion-cuellos-botella-webflux"></a>
### Identificación de Cuellos de Botella

<a id="estrategias-optimizacion-webflux"></a>
### Estrategias de Optimización

<a id="metricas-observabilidad-webflux"></a>
### Métricas y Observabilidad

<a id="final-project-reactive-microservices"></a>
## Microservicios Reactivos

<a id="diseno-arquitectura-microservicios-reactivos"></a>
### Diseño de Arquitectura de Microservicios Reactivos

<a id="implementacion-microservicios-end-to-end"></a>
### Implementación de Microservicios End-to-End

<a id="patrones-resiliencia-microservicios-reactivos"></a>
### Patrones de Resiliencia en Microservicios Reactivos

<a id="dockerizacion-despliegue-microservicios"></a>
### Dockerización y Despliegue


