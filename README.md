# AUREA
Asistente de IA

Descripción

AUREA OS es un asistente inteligente desarrollado como aplicación web que interactúa directamente con recursos reales del sistema operativo.

El proyecto fue diseñado para demostrar conceptos fundamentales de Sistemas Operativos como concurrencia observable, sincronización verificable e interacción con recursos reales como CPU, memoria, red y hardware externo.

No es una aplicación CRUD simple ni un sistema secuencial. Implementa concurrencia real y control de acceso a recursos compartidos.

Objetivo Académico

Demostrar de forma práctica:

Interacción real con el sistema operativo.

Uso de procesos e hilos reales del navegador.

Concurrencia observable (no secuencial encubierta).

Resolución de un problema de sincronización.

Monitoreo verificable de recursos del sistema.

Arquitectura General

Usuario
↓
Interfaz Web (HTML, CSS, JavaScript)
↓
Event Loop del navegador
↓
Web APIs
↓
Sistema Operativo
↓
Hardware / Red / Audio

Tecnologías Utilizadas

HTML5

CSS3

JavaScript (ES6+)

Web Speech API

Fetch API

Web Serial API

LocalStorage

Interacción con el Sistema Operativo
Web Speech API

Utiliza el motor de voz del sistema operativo para reproducir respuestas.
Esto implica uso real de CPU, memoria y servicios de audio del sistema.

Fetch API

Realiza peticiones HTTP reales a servicios externos, utilizando el stack TCP/IP del sistema operativo.

LocalStorage

Permite almacenamiento persistente del historial de conversaciones, implicando acceso a memoria y almacenamiento del sistema.

Web Serial API

Permite comunicación directa con un puerto serial físico (Arduino), interactuando con drivers del sistema operativo y hardware externo.

Concurrencia Observable

La aplicación implementa concurrencia real mediante:

async/await

Promesas

Eventos del navegador

Operaciones no bloqueantes

Ejemplo:
Mientras se realiza una petición HTTP, la interfaz continúa respondiendo sin bloquearse.
Mientras el asistente reproduce voz, el usuario puede seguir interactuando con el sistema.

Sincronización y Exclusión Mutua
Problema

El puerto serial es un recurso compartido.
Si múltiples procesos intentan escribir simultáneamente, puede producirse una condición de carrera.

Solución

Se implementa una cola de mensajes para:

Garantizar exclusión mutua.

Evitar corrupción de datos.

Controlar el acceso al recurso compartido.

Esto permite una sincronización verificable.

Recursos Reales Utilizados

Durante la ejecución se puede monitorear:

Uso de CPU (ejecución JavaScript y síntesis de voz).

Uso de memoria del navegador.

Uso de red durante peticiones HTTP.

Actividad del puerto serial al comunicarse con Arduino.

