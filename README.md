[DAS.md](https://github.com/user-attachments/files/28080575/DAS.md)
# Documento de Arquitectura de Software (DAS)

---
**Proyecto:** Lilfac

**Arquitectos:**
- Karen Juliana Montoya Velandia
- Jose Manuel Mosquera Restrepo

---

## Control de cambios y revisiones

| Versión  | Fecha      | Tipo       |  Descripción                          | Autor            |
|----------|------------|------------|---------------------------------------|------------------|
| 1        | 18/02/2026 | Creación   | Versión inicial del documento         | Juliana Montoya  |
| 2        | 13/05/2026 | Revisión   | Se registran novedades de la revisión | Jose Restrepo    |
| 3        | 20/05/2026 | Aprobación | Aprobación versión 3 del documento    | Jose Restrepo    |

---

## Contenido

[1. Propósito del proyecto](#1-propósito-del-proyecto)

[2. Motivadores de la arquitectura](#2-motivadores-de-la-arquitectura)
    
- [2.1 Restricciones técnicas](#21-restricciones-técnicas)


- [2.2 Restricciones de negocio](#22-restricciones-de-negocio)


- [2.3 Atributos de calidad](#23-atributos-de-calidad)

  - [2.3.1	Atributo calidad 1 	](#231-atributo-calidad-rendimiento)
    - [2.3.1.1	Característica 1	](#2311-característica--1-_car-ren-0001_)
      - [2.3.1.1.1	Escenario de calidad 1	](#23111-escenario-de-calidad-1-_esc-cal-ren-0001_)
      - [2.3.1.1.2	Escenario de calidad 2	](#23112-escenario-de-calidad-2-_esc-cal-ren-0002_)
      - [2.3.1.1.3	Escenario de calidad 3	](#23113-escenario-de-calidad-3-_esc-cal-ren-0003_)
    - [2.3.1.2	Característica 2	](#2312-característica-2-_car-ren-0005_)
      - [2.3.1.2.1	Escenario de calidad 1	](#23121-escenario-de-calidad-1-_esc-cal-ren-0011_)
  - [2.3.2	Atributo calidad 2	](#232-atributo-calidad-seguridad)
    - [2.3.2.1	Característica 1	](#2321-característica-1-_car-seg-0001_)
      - [2.3.2.1.1	Escenario de calidad 1	](#23211-escenario-de-calidad-1-_esc-cal-seg-0004_)
    - [2.3.2.2	Característica 2	](#2322-característica-2-_car-seg-0002_)
      - [2.3.2.2.1	Escenario de calidad 1	](#23221-escenario-de-calidad-1-_esc-cal-seg-0008_)
  - [2.3.3	Atributo calidad 3	](#233-atributo-calidad-disponibilidad)
    - [2.3.3.1	Característica 1	](#2331-característica-1-_car-dis-0001_)
      - [2.3.3.1.1	Escenario de calidad 1	](#23311-escenario-de-calidad-1-_esc-cal-dis-0001_)
      - [2.3.3.1.2	Escenario de calidad 2	](#23312-escenario-de-calidad-2-_esc-cal-dis-0002_)
  - [2.3.4	Atributo calidad 4	](#234-atributo-calidad-confiabilidad)
    - [2.3.4.1	Característica 1	](#2341-característica-1-_car-conf-0003_)
      - [2.3.4.1.1	Escenario de calidad 1	](#23411-escenario-de-calidad-1-_esc-cal-conf-0008_)
  - [2.3.5	Atributo calidad 5	](#235-atributo-calidad-capacidad-para-ser-administrado)
    - [2.3.5.1	Característica 1	](#2351-característica-1-_car-cadmi-0002_)
      - [2.3.5.1.1	Escenario de calidad 1	](#23511-escenario-de-calidad-1-_esc-cal-cadmi-0004_)
      - [2.3.5.1.2	Escenario de calidad 2	](#23512-escenario-de-calidad-2-_esc-cal-cadmi-0005_)
  - [2.3.6	Atributo calidad 6	](#236-atributo-calidad-escalabilidad-)
    - [2.3.6.1	Característica 1	](#2361-característica-1-_car-esca-0002_-)
      - [2.3.6.1.1	Escenario de calidad 1	](#23611-escenario-de-calidad-1-_esc-cal-esca-0004_)
      - [2.3.6.1.2	Escenario de calidad 2	](#23612-escenario-de-calidad-2-_esc-cal-esca-0005_)
      - [2.3.6.1.3	Escenario de calidad 3	](#23613-escenario-de-calidad-3-_esc-cal-esca-0006_)
  - [2.3.7	Atributo calidad 7	](#237-atributo-calidad-trazabilidad-)
    - [2.3.7.1	Característica 1	](#2371-característica-1-_car-traz-0001_)
      - [2.3.7.1.1	Escenario de calidad 1	](#23711-escenario-de-calidad-1-_esc-cal-traz-0001_)
      - [2.3.7.1.2	Escenario de calidad 2	](#23712-escenario-de-calidad-2-_esc-cal-traz-0002_)
    - [2.3.7.2	Característica 2	](#2372-característica-2-_car-traz-0002_)
      - [2.3.7.2.1	Escenario de calidad 1	](#23721-escenario-de-calidad-1-_esc-cal-traz-0003_)


- [2.4 Funcionalidades críticas](#24-funcionalidades-críticas)

[3. Tácticas y estrategias](#3-tácticas-y-estrategias)

[4. Modelo de contexto](#4-modelo-de-contexto)

[5. Arquetipo de solución/referencia](#5-arquetipo-de-soluciónreferencia)

[6. Arquitectura de solución/referencia](#6-arquitectura-de-soluciónreferencia)

[7. Línea base arquitectónica](#7-línea-base-arquitectónica)
- [7.1	Línea base arquitectónica de componentes ](#71-línea-base-arquitectónica-de-componentes)
  - [7.1.1	Componente 1 ](#711-componente-1)
  - [7.1.2	Componente 1	](#712-componente-2)


- [7.2	Estilos y patrones arquitectónicos adoptados	](#72-estilos-y-patrones-arquitectónicos-adoptados)
  - [7.2.1	Estilo arquitectónico 1	](#721-estilo-arquitectónico-1)
    - [7.2.1.1	Nombre	](#7211-nombre)
    - [7.2.1.2	Problema	](#7212-problema)
    - [7.2.1.3	Solución/Motivación	](#7213-soluciónmotivación)
  
  
  - [7.2.2	Estilo arquitectónico 2	](#722-estilo-arquitectónico-2)
    - [7.2.2.1	Nombre	](#7221-nombre)
    - [7.2.2.2	Problema	](#7222-problema)
    - [7.2.2.3	Solución/Motivación	](#7223-soluciónmotivación)


  - [7.2.N Estilo arquitectónico n	](#72n-estilo-arquitectónico-n)
    - [7.2.N.1 Nombre	](#72n1-nombre)
    - [7.2.N.2 Problema	](#72n2-problema)
    - [7.2.N.3 Solución/Motivación	](#72n3-soluciónmotivación)

[8. Justificación alternativa de solución](#8-justificación-alternativa-de-solución) 

- [8.1	Justificación](#81-justificación)
- [8.2	Ventajas	](#82-ventajas)
- [8.3	Desventajas	](#83-desventajas)

[9. Vistas de arquitectura del sistema](#9-vistas-de-arquitectura-del-sistema)

- [9.1	Vista Funcional/Vista de Escenarios/Vista de Casos de Uso](#91-vista-funcionalvista-de-escenariosvista-de-casos-de-uso)	
    - [9.1.1	Modelo de procesos del negocio	](#911-modelo-de-procesos-del-negocio)
    - [9.1.2	Modelado de dominio	](#912-modelado-de-dominio)
    - [9.1.3	Modelo de contextos	](#913-modelo-de-contextos)
      - [9.1.3.1	Diagrama	](#9131-diagrama)
      - [9.1.3.2	Documentación contextos	](#9132-documentación-contextos)

    - [9.1.4	Modelo de mapeo de contextos	](#914-modelo-de-mapeo-de-contextos)
        - [9.1.4.1	Diagrama	](#9141-diagrama)
        - [9.1.4.2	Documentación mapeo de contextos](#9142-documentación-mapeo-de-contextos)

    - [9.1.5	Modelos de dominio	](#915-modelos-de-dominio)
        - [9.1.5.1	Contexto 1	](#9151-contexto-1)
        - [9.1.5.2	Modelo anémico](#9152-modelo-anémico)	
        - [9.1.5.3	Modelo enriquecido	](#9153-modelo-enriquecido)
        - [9.1.5.4	Contexto 2	](#9154-contexto-2)
        - [9.1.5.5	Modelo anémico	](#9155-modelo-anémico)
        - [9.1.5.6	Modelo enriquecido	](#9156-modelo-enriquecido)
        - [9.1.5.7	Contexto 3	](#9157-contexto-3)
        - [9.1.5.8	Modelo anémico	](#9158-modelo-anémico)
        - [9.1.5.9	Modelo enriquecido	](#9159-modelo-enriquecido)
        - [9.1.5.10	Contexto N	](#91510-contexto-n)
        - [9.1.5.11	Modelo anémico	](#91511-modelo-anémico)
        - [9.1.5.12	Modelo enriquecido	](#91512-modelo-enriquecido)
    
    - [9.1.6	Flujo de eventos/Event Storming	](#916-flujo-de-eventosevent-storming)
        - [9.1.6.1	Diagrama	](#9161-diagrama)
        - [9.1.6.2	Especificación	](#9162-especificación)
    - [9.1.7	Glosario de términos del negocio	](#917-glosario-de-términos-del-negocio)
    - [9.1.8	Especificación de requisitos de software	](#918-especificación-de-requisitos-de-software)
        - [9.1.8.1	Requisitos de usuario	](#9181-requisitos-de-usuario)
        - [9.1.8.2	Requisitos del sistema	](#9182-requisitos-del-sistema)
          - [9.1.8.2.1	Requisitos funcionales	](#91821-requisitos-funcionales)
          - [9.1.8.2.2	Requisitos no funcionales	](#91822-requisitos-no-funcionales)
          - [9.1.8.2.3	Requisitos de información	](#91823-requisitos-de-información)
          - [9.1.8.2.4	Reglas de negocio	](#91824-reglas-de-negocio)
    - [9.1.9	Casos de uso	](#919-casos-de-uso)
        - [9.1.9.1	Modelo de contexto	](#9191-modelo-de-contexto)
          - [9.1.9.1.1	Diagrama	](#91911-diagrama)
          - [9.1.9.1.2	Descripción	](#91912-descripción)
        - [9.1.9.2	Diagramas de casos de uso	](#9192-diagramas-de-casos-de-uso)
          - [9.1.9.2.1	Componente 1/Módulo 1/Grupo 1	](#91921-componente-1módulo-1grupo-1)
            - [9.1.9.2.1.1	Diagrama de casos de uso	]()
            - [9.1.9.2.1.2	Especificación de casos de uso	]()
              - [9.1.9.2.1.2.1	Caso de uso 1	]()
                - [9.1.9.2.1.2.1.1	Datos básicos caso de uso	]()
                - [9.1.9.2.1.2.1.2	Escenarios del caso de uso	]()
                - [9.1.9.2.1.2.1.3	Flujo normal/flujo básico	]()
                - [9.1.9.2.1.2.1.4	Flujo alterno 1	]()
                - [9.1.9.2.1.2.1.5	Flujo alterno 2	]()
                - [9.1.9.2.1.2.1.6	Flujo alterno N	]()
                - [9.1.9.2.1.2.1.7	Flujo Excepcional 1	]()
                - [9.1.9.2.1.2.1.8	Flujo Excepcional 2	]()
                - [9.1.9.2.1.2.1.9	Flujo Excepcional N	]()
                - [9.1.9.2.1.2.1.10	Diagrama de actividades	]()
                  - [9.1.9.2.1.2.1.10.1	Diagrama	]()
                  - [9.1.9.2.1.2.1.10.2	Documentación	]()
                - [9.1.9.2.1.2.1.11	Diagrama de estados	]()
                  - [9.1.9.2.1.2.1.11.1	Diagrama	]()
                  - [9.1.9.2.1.2.1.11.2	Documentación	]()
              - [9.1.9.2.1.2.2	Caso de uso 2	]()
                - [9.1.9.2.1.2.2.1	Datos básicos caso de uso	]()
                - [9.1.9.2.1.2.2.2	Escenarios del caso de uso	]()
                - [9.1.9.2.1.2.2.3	Flujo normal/flujo básico	]()
                - [9.1.9.2.1.2.2.4	Flujo alterno 1	]()
                - [9.1.9.2.1.2.2.5	Flujo alterno 2	]()
                - [9.1.9.2.1.2.2.6	Flujo alterno N	]()
                - [9.1.9.2.1.2.2.7	Flujo Excepcional 1	]()
                - [9.1.9.2.1.2.2.8	Flujo Excepcional 2	]()
                - [9.1.9.2.1.2.2.9	Flujo Excepcional N	]()
                - [9.1.9.2.1.2.2.10	Diagrama de actividades	]()
                  - [9.1.9.2.1.2.2.10.1	Diagrama	]()
                  - [9.1.9.2.1.2.2.10.2	Documentación	]()
                - [9.1.9.2.1.2.2.11	Diagrama de estados	]()
                  - [9.1.9.2.1.2.2.11.1	Diagrama	]()
                  - [9.1.9.2.1.2.2.11.2	Documentación	]()
              - [9.1.9.2.1.2.3	Caso de uso N	]()
                - [9.1.9.2.1.2.3.1	Datos básicos caso de uso	]()
                - [9.1.9.2.1.2.3.2	Escenarios del caso de uso	]()
                - [9.1.9.2.1.2.3.3	Flujo normal/flujo básico	]()
                - [9.1.9.2.1.2.3.4	Flujo alterno 1	]()
                - [9.1.9.2.1.2.3.5	Flujo alterno 2	]()
                - [9.1.9.2.1.2.3.6	Flujo alterno N	]()
                - [9.1.9.2.1.2.3.7	Flujo Excepcional 1	]()
                - [9.1.9.2.1.2.3.8	Flujo Excepcional 2	]()
                - [9.1.9.2.1.2.3.9	Flujo Excepcional N	]()
                - [9.1.9.2.1.2.3.10	Diagrama de actividades	]()
                  - [9.1.9.2.1.2.3.10.1	Diagrama	]()
                  - [9.1.9.2.1.2.3.10.2	Documentación	]()
                - [9.1.9.2.1.2.3.11	Diagrama de estados	]()
                  - [9.1.9.2.1.2.3.11.1	Diagrama	]()
                  - [9.1.9.2.1.2.3.11.2	Documentación	]()
          - [9.1.9.2.2	Componente 2/Módulo 2/Grupo 2	]()
            - [9.1.9.2.2.1	Diagrama de casos de uso	]()
            - [9.1.9.2.2.2	Especificación de casos de uso	]()
              - [9.1.9.2.2.2.1	Caso de uso 1	]()
                - [9.1.9.2.2.2.1.1	Datos básicos caso de uso	]()
                - [9.1.9.2.2.2.1.2	Escenarios del caso de uso	]()
                - [9.1.9.2.2.2.1.3	Flujo normal/flujo básico	]()
                - [9.1.9.2.2.2.1.4	Flujo alterno 1	]()
                - [9.1.9.2.2.2.1.5	Flujo alterno 2	]()
                - [9.1.9.2.2.2.1.6	Flujo alterno N	]()
                - [9.1.9.2.2.2.1.7	Flujo Excepcional 1	]()
                - [9.1.9.2.2.2.1.8	Flujo Excepcional 2	]()
                - [9.1.9.2.2.2.1.9	Flujo Excepcional N	]()
                - [9.1.9.2.2.2.1.10	Diagrama de actividades	]()
                  - [9.1.9.2.2.2.1.10.1	Diagrama	]()
                  - [9.1.9.2.2.2.1.10.2	Documentación	]()
                - [9.1.9.2.2.2.1.11	Diagrama de estados	]()
                  - [9.1.9.2.2.2.1.11.1	Diagrama	]()
                  - [9.1.9.2.2.2.1.11.2	Documentación	]()
              - [9.1.9.2.2.2.2	Caso de uso 2	]()
                - [9.1.9.2.2.2.2.1	Datos básicos caso de uso	]()
                - [9.1.9.2.2.2.2.2	Escenarios del caso de uso	]()
                - [9.1.9.2.2.2.2.3	Flujo normal/flujo básico	]()
                - [9.1.9.2.2.2.2.4	Flujo alterno 1	]()
                - [9.1.9.2.2.2.2.5	Flujo alterno 2	]()
                - [9.1.9.2.2.2.2.6	Flujo alterno N	]()
                - [9.1.9.2.2.2.2.7	Flujo Excepcional 1	]()
                - [9.1.9.2.2.2.2.8	Flujo Excepcional 2	]()
                - [9.1.9.2.2.2.2.9	Flujo Excepcional N	]()
                - [9.1.9.2.2.2.2.10	Diagrama de actividades	]()
                  - [9.1.9.2.2.2.2.10.1	Diagrama	]()
                  - [9.1.9.2.2.2.2.10.2	Documentación	]()
                - [9.1.9.2.2.2.2.11	Diagrama de estados	]()
                  - [9.1.9.2.2.2.2.11.1	Diagrama	]()
                  - [9.1.9.2.2.2.2.11.2	Documentación	]()
              - [9.1.9.2.2.2.3	Caso de uso N	]()
                - [9.1.9.2.2.2.3.1	Datos básicos caso de uso	]()
                - [9.1.9.2.2.2.3.2	Escenarios del caso de uso	]()
                - [9.1.9.2.2.2.3.3	Flujo normal/flujo básico	]()
                - [9.1.9.2.2.2.3.4	Flujo alterno 1	]()
                - [9.1.9.2.2.2.3.5	Flujo alterno 2	]()
                - [9.1.9.2.2.2.3.6	Flujo alterno N	]()
                - [9.1.9.2.2.2.3.7	Flujo Excepcional 1	]()
                - [9.1.9.2.2.2.3.8	Flujo Excepcional 2	]()
                - [9.1.9.2.2.2.3.9	Flujo Excepcional N	]()
                - [9.1.9.2.2.2.3.10	Diagrama de actividades	]()
                  - [9.1.9.2.2.2.3.10.1	Diagrama	]()
                  - [9.1.9.2.2.2.3.10.2	Documentación	]()
                - [9.1.9.2.2.2.3.11	Diagrama de estados	]()
                  - [9.1.9.2.2.2.3.11.1	Diagrama	]()
                  - [9.1.9.2.2.2.3.11.2	Documentación	]()
                - [9.1.9.2.3	Componente N/Módulo N/Grupo N	]()
                  - [9.1.9.2.3.1	Diagrama de casos de uso	]()
                  - [9.1.9.2.3.2	Especificación de casos de uso	]()
                    - [9.1.9.2.3.2.1	Caso de uso 1	]()
                      - [9.1.9.2.3.2.1.1	Datos básicos caso de uso	]()
                      - [9.1.9.2.3.2.1.2	Escenarios del caso de uso	]()
                      - [9.1.9.2.3.2.1.3	Flujo normal/flujo básico	]()
                      - [9.1.9.2.3.2.1.4	Flujo alterno 1	]()
                      - [9.1.9.2.3.2.1.5	Flujo alterno 2	]()
                      - [9.1.9.2.3.2.1.6	Flujo alterno N	]()
                      - [9.1.9.2.3.2.1.7	Flujo Excepcional 1	]()
                      - [9.1.9.2.3.2.1.8	Flujo Excepcional 2	]()
                      - [9.1.9.2.3.2.1.9	Flujo Excepcional N	]()
                      - [9.1.9.2.3.2.1.10	Diagrama de actividades	]()
                        - [9.1.9.2.3.2.1.10.1	Diagrama	]()
                        - [9.1.9.2.3.2.1.10.2	Documentación	]()
                      - [9.1.9.2.3.2.1.11	Diagrama de estados	]()
                        - [9.1.9.2.3.2.1.11.1	Diagrama	]()
                        - [9.1.9.2.3.2.1.11.2	Documentación	]()
                    - [9.1.9.2.3.2.2	Caso de uso 2	]()
                      - [9.1.9.2.3.2.2.1	Datos básicos caso de uso	]()
                      - [9.1.9.2.3.2.2.2	Escenarios del caso de uso	]()
                      - [9.1.9.2.3.2.2.3	Flujo normal/flujo básico	]()
                      - [9.1.9.2.3.2.2.4	Flujo alterno 1	]()
                      - [9.1.9.2.3.2.2.5	Flujo alterno 2	]()
                      - [9.1.9.2.3.2.2.6	Flujo alterno N	]()
                      - [9.1.9.2.3.2.2.7	Flujo Excepcional 1	]()
                      - [9.1.9.2.3.2.2.8	Flujo Excepcional 2	]()
                      - [9.1.9.2.3.2.2.9	Flujo Excepcional N	]()
                      - [9.1.9.2.3.2.2.10	Diagrama de actividades	]()
                        - [9.1.9.2.3.2.2.10.1	Diagrama	]()
                        - [9.1.9.2.3.2.2.10.2	Documentación	]()
                      - [9.1.9.2.3.2.2.11	Diagrama de estados	]()
                        - [9.1.9.2.3.2.2.11.1	Diagrama	]()
                        - [9.1.9.2.3.2.2.11.2	Documentación	]()
                    - [9.1.9.2.3.2.3	Caso de uso N	]()
                      - [9.1.9.2.3.2.3.1	Datos básicos caso de uso	]()
                      - [9.1.9.2.3.2.3.2	Escenarios del caso de uso	]()
                      - [9.1.9.2.3.2.3.3	Flujo normal/flujo básico	]()
                      - [9.1.9.2.3.2.3.4	Flujo alterno 1	]()
                      - [9.1.9.2.3.2.3.5	Flujo alterno 2	]()
                      - [9.1.9.2.3.2.3.6	Flujo alterno N	]()
                      - [9.1.9.2.3.2.3.7	Flujo Excepcional 1	]()
                      - [9.1.9.2.3.2.3.8	Flujo Excepcional 2	]()
                      - [9.1.9.2.3.2.3.9	Flujo Excepcional N	]()
                      - [9.1.9.2.3.2.3.10	Diagrama de actividades	]()
                        - [9.1.9.2.3.2.3.10.1	Diagrama	]()
                        - [9.1.9.2.3.2.3.10.2	Documentación	]()
                      - [9.1.9.2.3.2.3.11	Diagrama de estados	]()
                        - [9.1.9.2.3.2.3.11.1	Diagrama	]()
                          - [9.1.9.2.3.2.3.11.2	Documentación	]()
    - [9.1.10	Incepción Ágil	]()
    - [9.1.11	Por qué estamos aquí	]()
    - [9.1.12	Visión/Elevator Pitch	]()
      - [9.1.12.1	Visión	]()
      - [9.1.12.2	Project Canvas	]()
      - [9.1.12.3	Mapa de impacto	]()
    - [9.1.13	Caja de producto	]()
    - [9.1.14	Lo que sí, lo que no	]()
      - [9.1.14.1	Mapa de historias de usuario	]()
      - [9.1.14.2	Product Backlog Item	]()
    - [9.1.15	La comunidad	]()
    - [9.1.16	La solución	]()
    - [9.1.17	Los riesgos/Los miedos	]()
    - [9.1.18	Tamaño/Talla de historias de usuario	]()
        -   [9.1.18.1	Tallaje del producto	]()
            - [9.1.18.1.1	Definiciones para el tallaje	]()
            - [9.1.18.1.2	Tallaje del producto	]()
        - [9.1.18.2	Release Plan	]()
            -   [9.1.18.2.1	Definiciones para el release plan	]()
            - [9.1.18.2.2	Release plan	]()
    - [9.1.19	Trade off de atributos de calidad	]()
    - [9.1.20	Cuánto cuesta	]()
      - [9.1.20.1. Definiciones para el coste	]()
      - [9.1.20.1.2	Coste	]()
- [9.2	Vista Lógica	]()
    - [9.2.1	Diagrama de clases	]()
      - [9.2.1.1	Componente 1	]()
        - [9.2.1.1.1	Diagrama	]()
        - [9.2.1.1.2	Documentación	]()
      - [9.2.1.2	Componente 2	]()
        -  [9.2.1.2.1	Diagrama	]()
        -  [9.2.1.2.2	Documentación	]()
      - [9.2.1.3	Componente N	]()
        -  [9.2.1.3.1	Diagrama	]()
        -  [9.2.1.3.2	Documentación	]()
    -   [9.2.2	Diagrama de objetos	]()
         - [9.2.2.1	Componente 1	]()
            -   [9.2.2.1.1	Diagrama	]()
            -   [9.2.2.1.2	Documentación	]()
         - [9.2.2.2	Componente 2	]()
            -  [9.2.2.2.1	Diagrama	]()
            - [9.2.2.2.2	Documentación	]()
        - [9.2.2.3	Componente N	]()
- [9.3	Vista de Despliegue/Vista de Desarrollo/Vista de Implementación	]()
    - [9.3.1	Diagrama de componentes	]()
      - [9.3.1.1	Componente 1	]()
        - [9.3.1.1.1	Diagrama	]()
        - [9.3.1.1.2	Documentación	]()
      - [9.3.1.2	Componente 2	]()
        - [9.3.1.2.1	Diagrama	]()
        - [9.3.1.2.2	Documentación	]()
      - [9.3.1.3	Componente N	]()
        - [9.3.1.3.1	Diagrama	]()
        - [9.3.1.3.2	Documentación	]()
    - [9.3.2	Diagrama de paquetes	]()
      - [9.3.2.1	Componente 1	]()
        -  [9.3.2.1.1	Diagrama	]()
        - [9.3.2.1.2	Documentación	]()
      - [9.3.2.2	Componente 2	]()
        - [9.3.2.2.1	Diagrama	]()
        - [9.3.2.2.2	Documentación	]()
      - [9.3.2.3	Componente N	]()
        - [9.3.2.3.1	Diagrama	]()
        - [9.3.2.3.2	Documentación	]()
- [9.4	Vista de Procesos	]()
    - [9.4.1	Diagrama de secuencia	]()
      - [9.4.1.1	Componente 1	]()
        - [9.4.1.1.1	Diagrama	]()
        - [9.4.1.1.2	Documentación	]()
      - [9.4.1.2	Componente 2	]()
        - [9.4.1.2.1	Diagrama	]()
        - [9.4.1.2.2	Documentación	]()
      - [9.4.1.3	Componente N	]()
        - [9.4.1.3.1	Diagrama	]()
        - [9.4.1.3.2	Documentación	]()
    - [9.4.2	Diagrama de colaboración]()	
      - [9.4.2.1	Componente 1	]()
        - [9.4.2.1.1	Diagrama	]()
        - [9.4.2.1.2	Documentación	]()
      - [9.4.2.2	Componente 2	]()
        - [9.4.2.2.1	Diagrama	]()
        - [9.4.2.2.2	Documentación	]()
      - [9.4.2.3	Componente N	]()
        - [9.4.2.3.1	Diagrama	]()
        - [9.4.2.3.2	Documentación	]()
- [9.5	Vista Física/Vista de Implantación	]()
    - [9.5.1	Diagrama de despliegue	]()
      - [9.5.1.1	Diagrama	]()
      - [9.5.1.2	Documentación]()	


---

## 1. Propósito del proyecto

Las empresas pequeñas y medianas de alquiler de inventario para eventos (pymes) enfrentan un gran problema de desorganización en el control del inventario y en la gestión de sus pedidos, ya que los registros de esta información actualmente se realizan de forma manual, lo cual genera dobles reservas, pérdidas de productos, errores en entregas, retrasos y errores en la facturación, lo cual termina causando la pérdida de confianza del cliente, disminución de ingresos para la empresa y dificultad para tomar decisiones estratégicas para el negocio por falta de información consolidada y actualizada.

Lilfac es un aplicativo web que permite reducir hasta en un 40% los errores operativos relacionados con inventario y facturación, disminuyendo pérdidas por dobles reservas o errores en facturación; mejora la rentabilidad en la empresa mediante una gestión centralizada que optimiza tiempos de operación y facilita la toma de decisiones basada en los datos de la misma.
Sus competidores actuales son las aplicaciones Rentman, Booqable y CurrentRMS, nuestro producto Lilfac a diferencia de estos incorpora un sistema de Inteligencia Operativa. El cual analiza automáticamente los indicadores clave del negocio (KPIs), es decir las métricas que muestran cómo está funcionando la empresa, y con base en estos datos, el sistema muestra la información histórica y la interpreta en tiempo real para generar alertas, prever posibles faltantes de inventario en fechas de alta demanda y sugerir ajustes estratégicos, como modificaciones de precios según la temporada, con el fin de maximizar los ingresos en temporada alta e incentivar la demanda en temporada baja.

De esta manera, el administrador no solo visualiza números y reportes, sino que recibe recomendaciones concretas que le ayudan a tomar decisiones más rentables y oportunas para la empresa.

---

## 2. Motivadores de la arquitectura

Los motivadores de la arquitectura son los factores clave que orientan y condicionan las 
decisiones de diseño de la solución de software, garantizando el cumplimiento los requisitos técnicos, 
de negocio y funcionales. 

Su objetivo principal es establecer los criterios sobre los cuales se evaluarán y seleccionarán las alternativas 
arquitectónicas.
En el desarrollo del proyecto, los motivadores de la arquitectura permiten enfocar los esfuerzos en los aspectos que
generan mayor valor y riesgo para el proyecto, facilitando la toma de decisiones en cuanto a tecnologías, 
patrones de diseño, componentes e infraestructura.

Representan las necesidades, restricciones y 
prioridades del proyecto que deben ser atendidas para garantizar que la arquitectura seleccionada satisfaga 
los objetivos del negocio y sus requerimientos, asegurando que la solución propuesta responda de manera adecuada
a las necesidades del sistema y las de los interesados del proyecto.

En los principales motivadores en Lilfac se incluyen aspectos como las restricciones técnicas y de negocio, 
los atributos de calidad y las funcionalidades críticas principales del sistema, como los siguientes:

Restricciones técnicas:
* Arquitectura limpia: Facilita la separación de responsabilidades y desacopla la lógica del negocio de los 
                       detalles técnicos, permitiendo un sistema más mantenible, escalable y fácil de probar.

* Código limpio: Mejora la legibilidad y comprensión del aplicativo, reduciendo errores y facilitando el mantenimiento
                 y la evolución del sistema.

* Cloud native: Permite aprovechar servicios en la nube para lograr mayor escalabilidad y 
                facilidad de despliegue, alineando la solución con prácticas modernas de desarrollo.

Restricciones de negocio:
* Presupuesto: Se cuenta con un presupuesto bajo y limitado para el proyecto
* Humanos: Se cuenta con un equipo de desarrollo de solo dos desarrolladores los cuales tienen poca experiencia   

Atributos de calidad:
* Rendimiento: Garantiza tiempos de respuesta adecuados para que los usuarios puedan consultar y 
               procesar información de forma ágil, mejorando la experiencia de uso y la eficiencia del sistema.


* Seguridad: Protege la información sensible y asegura que solo usuarios autorizados puedan acceder a los datos
               y funcionalidades del sistema según su rol, reduciendo riesgos de fuga o alteración de información sensible.


* Disponibilidad: Asegura que el sistema se encuentre operativo y accesible cuando los usuarios lo necesiten, 
                  minimizando interrupciones y afectaciones al servicio durante la operación de la empresa.


Funcionalidades críticas:
* El sistema debe restringir el acceso a modulos y funcionalidades según el rol del usuario autenticado.


### 2.1 Restricciones técnicas

Las restricciones técnicas son condiciones, limitaciones o decisiones tecnológicas que deben cumplirse obligatoriamente durante
el desarrollo del sistema. Estas restricciones pueden estar relacionadas con el uso de lenguajes de programación, frameworks, 
bases de datos, plataformas de despliegue, estándares de interoperabilidad, políticas de seguridad, herramientas de desarrollo 
o requerimientos de infraestructura.

Su objetivo es delimitar el conjunto de alternativas tecnológicas disponibles y garantizar que la solución sea compatible con
el entorno tecnológico de la organización. Por ejemplo, una restricción técnica puede exigir el uso de una base de datos 
específica, la implementación en una plataforma en la nube determinada o la adopción de protocolos estándar para la integración
con otros sistemas.

En el desarrollo del proyecto, las restricciones técnicas orientan la selección de herramientas, tecnologías y patrones
arquitectónicos, reduciendo la incertidumbre y asegurando la viabilidad de la solución. En la definición del diseño, estas 
restricciones influyen directamente en la estructura del sistema, en la forma en que los componentes se comunican y en la 
manera en que se implementan los requisitos funcionales y no funcionales. De esta forma, permiten que la arquitectura se 
construya sobre una base tecnológica consistente, compatible y alineada con las capacidades y políticas de la organización.
---
###### *Restricciones técnicas*


---
| Tipo                       | Restricción Técnica                                                                                                                                         | Justificación                                                                                                                                                                                                                                |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| 
| Prácticas de diseño        | Se debe propender por la aplicación de prácticas basadas en Clean Architecture.                                                                             | Aislación de módulos que permite cambiar cada uno sin romper el otro, facilita las pruebas automatizadas y evita errores en conciliaciones                                                                                                   |
| Prácticas de código limpio | Se debe propender por la aplicación de prácticas relacionadas con Clean Code.                                                                               | Menos cantidad de defectos en producción y mayor entendimiento del codigo para que pueda tener una mantenibilidad correcta                                                                                                                   | 
| Prácticas de diseño        | Se debe propender por la aplicación de patrones de diseño que promuevan un diseño con bajo acoplamiento y alta cohesión.                                    | Modificaciones en un módulo no afecta el otro, reduciendo el riesgo operativo, permite incorporar nuevas reglas de negocio                                                                                                                   |
| Implementación             | Se debe propender por la adopción de prácticas de DevOps, relacionadas con las estrategias de integración continua, entrega continua y despliegue continuo. | Despliegues seguros y continuos, pruebas de calidad                                                                                                                                                                                          |
| Prácticas de diseño        | Se debe propender por la adopción de bloques de construcción que promuevan aceleradores dentro del desarrollo del producto.                                 | Mayor foco en el valor del negocio, reutilizando componentes y  minimizando el retrabajo de cosas que ya existen                                                                                                                             |
| Prácticas de diseño        | Se debe propender por construcción aplicaciones de naturaleza Cloud Enabled o Cloud Native.                                                                 | Alta disponibilidad y seguridad con los datos                                                                                                                                                                                                |
| Prácticas de diseño        | Se debe propender por la construcción de aplicaciones que sigan los principios del _manifiesto reactivo_.                                                   | Sistema de rápida respuesta y buena recuperación ante fallos, adaptable a picos y cargas pesadas de datos permitiendo escalabilidad horizontal y una buena experiencia de usuario                                                            |
| Implementación             | Se debe propender por la construcción de aplicaciones que sigan las prácticas definidas en los 12 factores de aplicación más los 3 extendidos.              | Permite despliegues  frecuentes y seguros, mantiene un tiempo de respuesta al usuario ágil y estable e implementa la configuración en el entorno separada del código                                                                         |
| Prácticas de diseño        | Se debe propender por la arquitectura de sistemas nativos para la nube basados en los pilares fundamentales del Well Architected Framework.                 | Estos pilares son fundamentales para construir un software cloud native de forma segura, estable , rápida y eficiente. <br/>  Colas para tareas pesadas, DB gestionada con backups y replicas, despliegues frecuentes y buena sostenibilidad |
| Marco metodológico         | Se debe propender por la aplicación de metodologías ágiles.                                                                                                 | Backlog por módulos, sprints organizados con código, pruebas, documentación y despliegue                                                                                                                                                     |
| Prácticas de diseño        | Se debe propender por la aplicación de patrones de diseño gof                                                                                               | Código claro y mantenible, permite minimizar errores al cambiar reglas, cada patrón tiene su propósito                                                                                                                                       |

---



### 2.2 Restricciones de negocio
Las restricciones de negocio son condiciones, reglas y limitaciones establecidas por la organización o por los interesados
del proyecto que determinan cómo debe construirse y operar la solución de software. Estas restricciones pueden estar 
relacionadas con el presupuesto disponible, los tiempos de entrega, las políticas corporativas, la normativa legal vigente, 
los procesos internos y los objetivos estratégicos de la empresa.

Su propósito es asegurar que la solución tecnológica no solo sea técnicamente viable, sino también alineada con las 
necesidades, prioridades y capacidades del negocio. Por ejemplo, una restricción de negocio puede exigir que el sistema 
se implemente dentro de una fecha específica, que se ajuste a un presupuesto determinado, que cumpla con regulaciones como 
la protección de datos personales o que se integre con procesos ya establecidos en la organización.

En el desarrollo del proyecto, las restricciones de negocio orientan la priorización de funcionalidad
es, la asignación de recursos y la selección de alternativas que generen el mayor valor posible. 
En la definición del diseño, influyen en decisiones arquitectónicas como el alcance de la solución, 
el nivel de automatización, la elección entre tecnologías propietarias o de código abierto y la estrategia de 
implementación. De esta manera, garantizan que la arquitectura responda no solo a requerimientos técnicos, 
sino también a las condiciones y objetivos del negocio.

---
###### *Restricciones de negocio*

---
| Tipo        | Restricción de Negocio                                                                                                                                                                                                                                                                                                                                                       | Justificación                                                                                                                                                                                                                                                                                                                                     | Plan de acción                                                                                                                                                                                                                                                     |
|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Humano      | El product owner asignado al proyecto no tiene el tiempo de dedicación necesario a causa de otras responsabilidades y actividades del día a día que le consumen su agenda, lo que entonces hace que no se puedan atender sesiones clave del proyecto para aclarar y definir aspectos que permitan avanzar con el desarrollo y cumplir de esta manera con el tiempo acordado. | Valor crítico para el éxito del proyecto. La baja disponibilidad del Product Owner bloquea la toma oportuna de decisiones, retrasa la definición/validación de requisitos e incrementa la incertidumbre y los retrabajos, a demás compromete directamente el alcance, el cronograma y la calidad de las entregas.                                 | Contar con una segunda parte que pueda atender estos aspectos con el mismo conocimiento que el product owner, para no restrasar el desarrollo de el proyecto                                                                                                       |
| Humano      | El equipo de desarrollo solo cuenta con dos desarrolladores y con poca experiencia en el desarrollo de aplicaciones cloud native.                                                                                                                                                                                                                                            | La capacidad limitada del equipo y la falta de experiencia en arquitecturas cloud native pueden generar retrasos en la implementación, errores en el diseño y dificultades para aplicar buenas prácticas de despliegue, escalabilidad y resiliencia. Esto puede impactar el cronograma, la calidad del prototipo y la estabilidad de la solución. | Capacitar al equipo en conceptos fundamentales de aplicaciones cloud native y apoyarse en documentación oficial, tutoriales y ejemplos de referencia. Priorizar un alcance reducido y utilizar tecnologías conocidas para disminuir la complejidad del desarrollo. | 
| Humano      | El equipo tiene poca experiencia en temas de seguridad de la información y en la implementación de medidas avanzadas de protección.                                                                                                                                                                                                                                          | La falta de conocimientos en seguridad puede ocasionar vulnerabilidades en el manejo de datos, autenticación y control de acceso, lo que podría comprometer la confidencialidad e integridad de la información y generar incumplimientos legales.                                                                                                 | Implementar controles de seguridad básicos y utilizar servicios administrados que incluyan mecanismos de seguridad incorporados.                                                                                                                                   |
| Humano      | El equipo tiene poca experiencia en la integración de los diferentes servicios dentro del desarrollo de la aplicación.                                                                                                                                                                                                                                                       | La integración de servicios externos y componentes distribuidos puede presentar errores de comunicación, problemas de compatibilidad y retrasos en el desarrollo, afectando el funcionamiento integral del sistema.                                                                                                                               | Reducir la cantidad de integraciones al mínimo necesario, realizar pruebas tempranas de conectividad y apoyarse en APIs bien documentadas y ampliamente utilizadas.                                                                                                |
| Humano      | Los miembros del equipo de desarrollo solo cuentan con 2 horas diarias de lunes a viernes disponibles para trabajar en el proyecto.                                                                                                                                                                                                                                          | La disponibilidad limitada del equipo reduce la velocidad de desarrollo y aumenta el riesgo de incumplimiento en las fechas de entrega, especialmente si surgen imprevistos o retrabajos.                                                                                                                                                         | Definir un alcance realista y priorizar únicamente las funcionalidades esenciales del prototipo. Mantener una planificación semanal y seguimiento continuo del avance.                                                                                             |
| Presupuesto | El proyecto tiene un presupuesto de $500.000 para el desarrollo inicial del producto                                                                                                                                                                                                                                                                                         | Determinante para la viabilidad y el alcance de el producto. El tope de $500.000 define las funcionalidades prioritarias y el plan por fases; exige control estricto de costos y trade-offs. Cualquier desbordamiento compromete la continuidad, el cronograma y la calidad del producto.                                                         | Definición del MVP y de los requisitos no negociables para realizar una gestión adecuada del presupuesto                                                                                                                                                           |
| Presupuesto | El presupuesto no cubre la contratación de personal adicional para soporte técnico.                                                                                                                                                                                                                                                                                          | La ausencia de recursos adicionales limita la capacidad para resolver problemas especializados y atender contingencias, aumentando la carga de trabajo del equipo actual y el riesgo de retrasos.                                                                                                                                                 | Distribuir claramente los roles y responsabilidades del equipo, documentar las soluciones implementadas y apoyarse en comunidades y recursos gratuitos para resolver problemas técnicos.                                                                           |
| Presupuesto | El presupuesto no cubre plataformas con altos costos de operación; está pensado únicamente para entregar un prototipo base desarrollado en su mayoría con servicios gratuitos.                                                                                                                                                                                               | Esta restricción limita la selección de herramientas e infraestructura, lo que puede afectar el rendimiento, la escalabilidad y algunas funcionalidades avanzadas del sistema.                                                                                                                                                                    | Seleccionar servicios gratuitos o de bajo costo, optimizar el uso de recursos y enfocar el desarrollo en un prototipo funcional que valide el concepto de negocio.                                                                                                 |
| Legal       | El sistema debe cumplir con las normativas de protección de datos personales según la Ley 1581 de 2012 en Colombia.                                                                                                                                                                                                                                                          | El incumplimiento de esta normativa puede generar sanciones legales, afectar la reputación del proyecto y comprometer la confianza de los usuarios en el manejo de su información personal.                                                                                                                                                       | Diseñar el sistema aplicando principios de privacidad y seguridad, solicitar autorización para el tratamiento de datos, implementar controles de acceso y documentar las políticas de protección de datos.                                                         |
| Procesos    | El cliente espera que TI sea un actor clave responsable de la definición del proceso de negocio, cuando no es su responsabilidad, dado que TI habilita procesos de negocio y no los define.                                                                                                                                                                                  | La confusión de roles entre negocio y TI provoca decisiones equivocadas sobre el proceso, falta de “dueño”, retrabajos y demoras en la aceptación. Afecta la calidad, la adopción del sistema y el cumplimiento normativo.                                                                                                                        | Nombrar claramente la gobernanza en el proyecto, quien es el dueño de proceso, y que el equipo de desarrollo de TI actue verdaderamente como el habilitador de esos procesos de negocio                                                                            |


---

### 2.3 Atributos de calidad

Los atributos de calidad son características no funcionales que describen cómo debe comportarse el sistema 
para cumplir con las expectativas de la empresa y de los usuarios. A diferencia de los requisitos funcionales, 
que definen qué es lo que hace el sistema, los atributos de calidad establecen el cómo debe hacerlo, considerando aspectos 
como rendimiento, seguridad, disponibilidad, escalabilidad, usabilidad y confiabilidad.

Su propósito es garantizar que la solución de software no solo cumpla con las funcionalidades requeridas, 
sino que también opere de manera eficiente, segura y estable en el entorno real de uso.

En el desarrollo del proyecto, los atributos de calidad permiten identificar los principales riesgos técnicos y 
establecer criterios claros para evaluar la arquitectura y las tecnologías seleccionadas. En la definición del diseño, 
influyen directamente en decisiones como la estructura de los componentes, los mecanismos de seguridad, la estrategia 
de despliegue, la gestión de errores y la forma de escalar el sistema. De esta manera, los atributos de calidad orientan
la construcción de una arquitectura robusta y alineada con las necesidades del negocio y las expectativas de los usuarios.

#### 2.3.1 Atributo calidad Rendimiento

El rendimiento se refiere a la capacidad del sistema para responder rápidamente a las solicitudes
de los usuarios y procesar la información de manera eficiente. Su objetivo es garantizar tiempos de respuesta adecuados
y un uso óptimo de los recursos del sistema, incluso cuando varios usuarios acceden simultáneamente.

En el desarrollo del proyecto, el rendimiento permite definir metas como tiempos de respuesta y capacidad de
atención a múltiples usuarios, ayudando a identificar y prevenir posibles cuellos de botella.

En la definición del diseño, este atributo influye en decisiones como la optimización de consultas a la base de datos, 
el uso de caché, la paginación de resultados y el procesamiento asíncrono. Esto con el fin de asegurar que la solución
funcione de manera ágil y mantenga un desempeño estable a medida que aumenta la carga del sistema.

##### 2.3.1.1 Característica  1  _CAR-REN-0001_

El sistema debe garantizar tiempos rápidos durante el acceso inicial y autenticación de usuarios

Esta característica asegura que los usuarios puedan acceder al sistema de manera rápida y fluida, 
mejorando la experiencia y la percepción de calidad del software.

##### 2.3.1.1.1 Escenario de calidad 1 _ESC-CAL-REN-0001_

Cuando un usuario ingrese su nombre de usuario y contraseña en la pantalla de inicio de sesión,
el sistema debe autenticar las credenciales y mostrar el dashboard principal en un tiempo máximo 
de 2 segundos 

Este escenario orienta el desarrollo del proyecto al establecer una meta concreta y medible 
de desempeño. Esto orienta el desarrollo a un diseño e implementación de una solución eficiente,
optimizando consultas a la base de datos, procesos de autenticación y carga de información. 
Además, permite definir criterios claros de prueba y aceptación para validar que el sistema 
cumple con el nivel de rendimiento esperado por los usuarios.

---
| Campo                 | Descripción                                                                                                                                                                                                                                            |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Código**            | ESC-CAL-REN-0001                                                                                                                                                                                                                                       |
| **Nombre**            | El sistema debe autenticar las credenciales de usuarios y cargar el dashboard principal en un tiempo máximo de 2 segundos                                                                                                                              |
| **Objetivo**          | Garantizar que el proceso de autenticación de usuarios y carga del dashboard principal se realice de manera rápida y eficiente                                                                                                                         |
| **Criterio de éxito** | El usuario ingresa credenciales válidas y es autenticado correctamente, visualizando el dashboard principal en un tiempo menor o igual a 2 segundos                                                                                                    |
| **Prerequisitos**     | 1. El usuario debe existir<br>2. La cuenta debe estar activa y vigente<br>3. El sistema debe estar disponible y operativo en ambiente productivo<br>4. La base de datos debe estar accesible<br>5. Las credenciales deben ser ingresadas correctamente |

| Fuente del estímulo                | Estímulo                                                                         | Ambiente                                  | Artefacto | Respuesta                                                                                                   | Medida de la respuesta                                                               |
|------------------------------------|----------------------------------------------------------------------------------|-------------------------------------------|-----------|-------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| Cualquier usuario de la aplicación | Ingresar nombre de usuario y contraseña y ejecutar la acción de inicio de sesión | Operación normal en ambiente productivo   | Sistema   | El sistema valida las credenciales y, si son correctas, autentica al usuario y carga el dashboard principal | El tiempo total de autenticación y carga del dashboard es menor o igual a 2 segundos |

##### 2.3.1.1.2 Escenario de calidad 2 _ESC-CAL-REN-0002_

Cuando un usuario ingrese al sistema por primera vez en el día, el sistema debe cargar completamente la 
pantalla inicial del sistema en un tiempo máximo de 3 segundos

Este escenario guía el diseño del sistema hacia la optimización del arranque inicial, lo orienta 
el desarrollo del proyecto a tomar decisiones técnicas sobre carga eficiente de recursos, consultas
optimizadas y posible uso de cache. Además, establece un criterio claro y medible de aceptación 
que permite validar el comportamiento del sistema en condiciones reales de uso.
---
| Código                | ESC-CAL-REN-0002                                                                                                                                                                                                                                                                                                               |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe cargar la pantalla inicial cuando el usuario ingrese por primera vez en el día en un tiempo máximo de 3 segundos                                                                                                                                                                                               |
| **Objetivo**          | Garantizar una carga rápida de la pantalla inicial del sistema en el primer acceso diario del usuario                                                                                                                                                                                                                          |
| **Criterio de éxito** | El usuario accede por primera vez en el día y la pantalla inicial se carga completamente en un tiempo menor o igual a 3 segundos                                                                                                                                                                                               |
| **Prerequisitos**     | 1. El usuario debe existir y estar autenticado<br>2. El sistema debe estar disponible en ambiente productivo<br>3. La conexión a la base de datos y servicios debe estar operativa<br>4. El usuario debe realizar su primer ingreso del día<br>5. El sistema debe tener acceso a los recursos necesarios para la carga inicial |

| Fuente del estímulo                                                 | Estímulo                                                | Ambiente                                                                             | Artefacto   | Respuesta                                                                                | Medida de la respuesta                                                        |
|---------------------------------------------------------------------|---------------------------------------------------------|--------------------------------------------------------------------------------------|-------------|------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| Usuario autenticado ingresando al sistema por primera vez en el día | Acceder al sistema desde la pantalla de inicio o login  | Operación normal en ambiente productivo                                              | Sistema     | El sistema carga completamente la pantalla inicial con todos sus componentes funcionales | El tiempo total de carga de la pantalla inicial es menor o igual a 3 segundos | 

##### 2.3.1.1.3 Escenario de calidad 3 _ESC-CAL-REN-0003_

Cuando un usuario introduzca credenciales incorrectas, el sistema debe validar la información y 
mostrar el mensaje de error correspondiente en un tiempo máximo de 2 segundos

Este escenario guía el diseño hacia el desarrollo de procesos de validación eficientes y optimizados,
reduciendo tiempos de consulta y respuesta. También establece un criterio medible para pruebas de
rendimiento y experiencia de usuario.

---
| Código                | ESC-CAL-REN-0003                                                                                                                                                                                                                                                                                       |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe validar credenciales incorrectas y mostrar el mensaje de error en un tiempo máximo de 2 segundos                                                                                                                                                                                       |
| **Objetivo**          | Garantizar una validación rápida y respuesta inmediata ante intentos de autenticación fallidos                                                                                                                                                                                                         |
| **Criterio de éxito** | Cuando el usuario ingresa credenciales incorrectas, el sistema valida la información y muestra el mensaje de error correspondiente en un tiempo menor o igual a 2 segundos                                                                                                                             |
| **Prerequisitos**     | 1. El usuario debe estar registrado en el sistema <br> 2. El sistema  debe estar operativo <br> 3. La base de datos de usuarios debe estar disponible <br> 4. El usuario debe intentar iniciar sesión con credenciales incorrectas <br> 5. El sistema debe contar con el servicio de validación activo |

| Fuente del estímulo                                        | Estímulo                                                                 | Ambiente                                 | Artefacto  | Respuesta                                                                                           | Medida de la respuesta                                                                   |
|------------------------------------------------------------|--------------------------------------------------------------------------|------------------------------------------|------------|-----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| Usuario intentando autenticarse con credenciales inválidas | Ingreso de usuario y/o contraseña incorrectos en el formulario de login  | Operación normal en ambiente productivo  | Sistema    | El sistema rechaza las credenciales y muestra un mensaje de error indicando autenticación inválida  | El tiempo de validación y despliegue del mensaje de error es menor o igual a 2 segundos  |


##### 2.3.1.2 Característica 2  _CAR-REN-0005_

El sistema debe permitir 50 sesiones simultáneas sin degradación en sus tiempos de respuesta

Esta característica asegura que el sistema sea capaz de atender múltiples 
usuarios simultáneamente sin afectar la velocidad de respuesta ni la experiencia del usuario.

###### 2.3.1.2.1 Escenario de calidad 1 _ESC-CAL-REN-0011_

Durante la operación normal de la empresa cuando el sistema se encuentra con varias sesiones 
abiertas simultáneamente, incluyendo personal de caja, bodegueros, logistica y el administrador 
generando registros activamente, la plataforma debe mantener un máximo de 50 sesiones activas 
sin degradar su desempeño, asegurando que cada solicitud sea procesada en menos de 5 segundos y 
sin interrupciones en el servicio.

Este escenario guía el diseño hacia la capacidad del sistema de soportar múltiples sesiones
simultáneas, manteniendo tiempos de respuesta adecuados y evitando saturación de recursos. 
También establece criterios medibles de escalabilidad y rendimiento bajo carga real.

---
| Código                | ESC-CAL-REN-0011                                                                                                                                                                                                                                 |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe soportar hasta 50 sesiones activas simultáneas sin degradar su desempeño, garantizando tiempos de respuesta menores o iguales a 5 segundos                                                                                       |
| **Objetivo**          | Garantizar la estabilidad y el rendimiento del sistema bajo condiciones de alta concurrencia de usuarios en operación normal                                                                                                                     |
| **Criterio de éxito** | Cuando existen hasta 50 sesiones activas simultáneas, el sistema procesa cada solicitud sin interrupciones y con un tiempo de respuesta menor o igual a 5 segundos                                                                               |
| **Prerequisitos**     | 1. Debe existir un conjunto de usuarios autenticados simultáneamente <br>2. Deben estar habilitados los módulos de caja, logística, bodega y administración <br>3. El sistema debe permitir la ejecución de múltiples transacciones concurrentes |
|

| Fuente del estímulo                                                                                    | Estímulo                                                                                             | Ambiente                                            | Artefacto                                                                  | Respuesta                                                                                                                | Medida de la respuesta                                                                                                        |
|--------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| Múltiples usuarios (caja, bodega, logística y administración) operando simultáneamente en el sistema   | Ejecución concurrente de registros, consultas y operaciones por parte de hasta 50 usuarios activos   | Operación normal del sistema con alta concurrencia  | Plataforma del sistema (backend, base de datos y servicios de aplicación)  | El sistema procesa todas las solicitudes concurrentes sin caídas, bloqueos ni degradación significativa del rendimiento  | El tiempo de respuesta de cada solicitud es menor o igual a 5 segundos, incluso bajo carga de hasta 50 sesiones simultáneas   |



#### 2.3.2 Atributo calidad Seguridad

El atributo de calidad de seguridad en un sistema se refiere a la capacidad que tiene el software
para proteger la información, los usuarios y los recursos del sistema frente a accesos no autorizados, 
errores, ataques o uso indebido. 

Busca garantizar que solo las personas con los permisos correspondientes puedan acceder a la información
de acuerdo a su rol y que la integridad de los datos no se vea comprometida.

##### 2.3.2.1 Característica 1  _CAR-SEG-0001_

El sistema debe implementar doble factor de autenticación por medio de SMS o correo

Esta característica asegura la seguridad del sistema al exigir una verificación adicional de 
identidad, reduciendo el riesgo de accesos no autorizados y guiando el diseño hacia una arquitectura
de autenticación más robusta y controlada.

##### 2.3.2.1.1 Escenario de calidad 1 _ESC-CAL-SEG-0004_

En un escenario donde cualquier usuario autorizado del sistema, como cajeras, bodegueros, 
personal de logística o el administrador, intenta acceder a la aplicación, el sistema debe 
requerir un segundo factor de autenticación enviando un código temporal único de verificación 
mediante SMS o correo electrónico después de validar las credenciales iniciales, el cual debe ser
enviado en un tiempo menor a 5 segundos, permitiendo el acceso únicamente si el código es ingresado
correctamente y antes de su tiempo de vencimiento para asegurar la protección de las cuentas de
usuario.

Este escenario orienta el diseño del sistema hacia la integración de mecanismos de autenticación
multifactor, gestión de códigos temporales, control de expiración e integración con servicios 
externos de mensajería y correo electrónico. Además, establece criterios claros para validar el
nivel de seguridad y la eficiencia del proceso de autenticación.

---
| Código                | ESC-CAL-SEG-0004                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | Implementación de doble factor de autenticación por medio de SMS o correo                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Objetivo**          | Garantizar la seguridad del sistema asegurando que el acceso al sistema solo sea permitido cuando el usuario valide correctamente el segundo factor de autenticación enviado a su correo electrónico o número telefónico y dentro del tiempo de vigencia del codigo                                                                                                                                                                                                                                                                       |
| **Criterio de éxito** | El usuario ingresa un código válido dentro del tiempo de vigencia, permitiendo su autenticación y redirección a la página principal del sistema                                                                                                                                                                                                                                                                                                                                                                                           |
| **Prerequisitos**     | 1. El usuario debe existir <br> 2. La cuenta debe estar activa y  vigente <br>3. El sistema debe estar disponible y operativo en ambiente productivo <br>4. La base de datos debe estar accesible <br>  5. El usuario debe tener registrado un correo electrónico y/o un número telefónico <br>6. El código debe generarse con un tiempo de expiración definido <br>7. El sistema debe enviarle un código al usuario via correo o SMS <br> 8. El usuario debe ingresar el código en el sistema dentro de el tiempo de vigencia del mismo  |

| Fuente del estímulo                 | Estímulo                                              | Ambiente                                 | Artefacto | Respuesta                                                                                                                           | Medida de la respuesta                                                                                                                                                                                                                 |
|-------------------------------------|-------------------------------------------------------|------------------------------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cualquier usuario de la aplicación  | El usuario ingresa el código de verificación valido.  | Operación normal en ambiente productivo  | Sistema   | El sistema valida el código ingresado y, si es correcto y vigente, permite el acceso redirigiendo al usuario a la página principal  | El código de verificación fue enviado al usuario en menos de 5 segundos, el código tiene un tiempo de vigencias de 5 minutos y la validación del código se realiza correctamente y en menos de 2 segundos antes de permitir el acceso  |



##### 2.3.2.2 Característica 2 _CAR-SEG-0002_

El sistema debe cerrar sesión automáticamente tras cierta cantidad establecida de tiempo de inactividad en minutos

Esta característica del atributo de calidad seguridad ayuda a proteger la información del sistema al evitar que una 
sesión quede abierta cuando el usuario deja de utilizar la aplicación y guía el diseño hacia el desarrollo de un sistema 
más seguro, evitando accesos no autorizados cuando un usuario deja su sesión abierta sin supervisión.

##### 2.3.2.2.1 Escenario de calidad 1 _ESC-CAL-SEG-0008_

En un escenario donde cualquier usuario autorizado del sistema, incluyendo cajeras, bodegueros o personal de logística, 
deja la aplicación abierta sin realizar acciones durante un periodo mayor al tiempo máximo configurado por la empresa, 
el sistema debe cerrar automáticamente la sesión activa y notificar al respectivo usuario lo sucedido, garantizando que el 
acceso al sistema permanezca protegido frente a posibles usos no autorizados.

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos de control de inactividad,
temporizadores de sesión y cierre automático, asegurando que las sesiones no permanezcan abiertas indefinidamente.

---
| Código                | ESC-CAL-SEG-0008                                                                                                                                                                                                                                                                                                                                                                                            |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe cerrar automáticamente sesiones inactivas por seguridad                                                                                                                                                                                                                                                                                                                                     |
| **Objetivo**          | Garantizar la protección del sistema frente a accesos no autorizados mediante el cierre automático de sesiones que permanezcan inactivas durante un tiempo definido por la empresa                                                                                                                                                                                                                          |
| **Criterio de éxito** | El sistema detecta la inactividad del usuario, cierra la sesión automáticamente al superar el tiempo configurado y notifica al usuario sobre el cierre de su sesión                                                                                                                                                                                                                                         |
| **Prerequisitos**     | 1. El usuario debe haber iniciado sesión en el sistema validadno sus credenciales <br> 2. Debe existir un tiempo máximo de inactividad configurado <br> 3. El sistema debe poder detectar la inactividad del usuario <br> 4. El sistema debe tener habilidato el mecanismo de gestión de sesiones <br> 5. El sistema debe ser capaz de notificar al usuario el cierre de sus sesión debido a la inactividad |

| Fuente del estímulo                             | Estímulo                                                        | Ambiente                                 | Artefacto | Respuesta                                                                                         | Medida de la respuesta                                                                                                                                                              |
|-------------------------------------------------|-----------------------------------------------------------------|------------------------------------------|-----------|---------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cualquier usuario autenticado de la aplicación  | Inactividad del usuario durante un tiempo mayor al configurado  | Operación normal en ambiente productivo  | Sistema   | El sistema detecta la inactividad, cierra automáticamente la sesión activa y notifica al usuario  | La sesión se cierra en 1 segundo al superar el tiempo de inactividad configurado por el administrador y se impide el acceso hasta que el usuario valide sus credenciales de nuevo.  |


#### 2.3.3 Atributo calidad Disponibilidad

El atributo de calidad de disponibilidad se refiere a la capacidad del sistema para estar operativo y accesible cuando los usuarios
lo necesiten. El software debe funcionar de manera continua, minimizando caídas, errores y tiempos fuera de servicio.

La disponibilidad asegura que el sistema esté funcionando y accesible cuando se necesite, orientando tanto el desarrollo como el diseño
de la solución hacia la elección de bloques de construcción confiables y con mínima interrupción del servicio.

##### 2.3.3.1 Característica 1 _CAR-DIS-0001_

El sistema debe garantizar un 95% de disponibilidad mensual.

Esta característica orienta el diseño hacia un sistema estable y confiable, asegurando que los usuarios puedan acceder a la 
aplicación la mayor parte del tiempo con un nivel aceptable de continuidad del servicio.

##### 2.3.3.1.1 Escenario de calidad 1 _ESC-CAL-DIS-0001_

Durante el uso continuo del sistema a lo largo del mes por parte de los diferentes usuarios de la empresa, el sistema debe
garantizar que el servicio permanezca accesible y operativo al menos el 95% del tiempo mensual, permitiendo que las actividades
del negocio se desarrollen con normalidad y reduciendo al mínimo los periodos de indisponibilidad.

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos de monitoreo, redundancia, recuperación ante
fallos y mantenimiento controlado, con el fin de asegurar que el sistema permanezca disponible durante la mayor parte del
tiempo. Además, establece un criterio medible para evaluar la continuidad operativa del sistema.

---
| Código                | ESC-CAL-DIS-0001                                                                                                                                                                                                                                                                |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe garantizar una disponibilidad mínima del 95% mensual                                                                                                                                                                                                            |
| **Objetivo**          | Asegurar que la plataforma se mantenga accesible y operativa durante la mayor parte del tiempo, permitiendo la continuidad de las operaciones del negocio                                                                                                                       |
| **Criterio de éxito** | El sistema permanece disponible al menos el 95% del tiempo durante un periodo mensual, permitiendo el acceso y uso normal por parte de los usuarios                                                                                                                             |
| **Prerequisitos**     | 1. El sistema debe estar disponible y operativo en ambiente productivo <br> 2. La infraestructura debe ser operativa ( servidor, red, base de datos ) <br> 3. Deben existir mecanismos de monitoreo de disponibilidad <br> 4. Los usuarios requieren acceso continuo a sistema  |

| Fuente del estímulo                      | Estímulo                                                  | Ambiente                                 | Artefacto | Respuesta                                                                                                                         | Medida de la respuesta                                                                                                                         |
|------------------------------------------|-----------------------------------------------------------|------------------------------------------|-----------|-----------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Cualquier usuario de la aplicación       | Uso continuo de la plataforma durante el periodo mensual  | Operación normal en ambiente productivo  | Sistema   | El sistema se mantiene accesible y operativo, permitiendo a los usuarios realizar sus actividades sin interrupciones prolongadas  | El sistema presenta una disponibilidad igual o superior al 95% mensual, medida como el porcentaje de tiempo en que el servicio está accesible  |


##### 2.3.3.1.2 Escenario de calidad 2 _ESC-CAL-DIS-0002_

Cuando se presentan picos de trabajo en la empresa debido a múltiples eventos programados y varios usuarios accediendo 
simultáneamente al sistema para realizar consultas, registros y actualizaciones, la plataforma debe mantener su funcionamiento 
normal, garantizando una disponibilidad mínima del 95% mensual para asegurar que las operaciones críticas del negocio puedan 
realizarse sin interrupciones.

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos de escalabilidad,
monitoreo continuo y tolerancia a fallos, con el fin de garantizar que la plataforma permanezca disponible incluso en
periodos de alta demanda.

---
| Código                  | ESC-CAL-DIS-0002                                                                                                                                                                                                                                                                                 |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**              | Disponibilidad del sistema durante picos de alta demanda                                                                                                                                                                                                                                         |
| **Objetivo**            | Garantizar que el sistema mantenga su funcionamiento normal y permanezca disponible al menos el 95% del tiempo mensual, incluso durante periodos de alta concurrencia                                                                                                                            |
| **Criterio de éxito**   | El sistema continúa operativo y accesible durante picos de trabajo, manteniendo una disponibilidad mensual igual o superior al 95%                                                                                                                                                               |
| **Prerequisitos**       | 1. El sistema debe estar desplegado en ambiente productivo  <br> 2. Deben existir mecanismos de monitoreo y registro de disponibilidad <br> 3. El sistema debe soportar múltiples usuarios concurrentes <br> 4. Deben estar implementados mecanismos de escalabilidad y recuperación ante fallos |

| Fuente del estímulo              | Estímulo                                                               | Ambiente                                                                   | Artefacto | Respuesta                                                                                                                | Medida de la respuesta                                                                                     |
|----------------------------------|------------------------------------------------------------------------|----------------------------------------------------------------------------|-----------|--------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Múltiples usuarios del sistema   | Acceso simultáneo para realizar consultas, registros y actualizaciones | Operación normal en ambiente productivo con alta concurrencia de usuarios  | Sistema   |  El sistema mantiene su funcionamiento normal y permite ejecutar las operaciones críticas del negocio sin interrupciones | La disponibilidad mensual del sistema es igual o superior al 95%, incluso durante periodos de alta demanda |



#### 2.3.4 Atributo calidad Confiabilidad

El atributo de calidad de confiabilidad se refiere a la capacidad del sistema para funcionar correctamente y sin errores durante
un período determinado. En términos simples, significa que el software debe cumplir sus funciones de manera estable y consistente,
generando resultados correctos cada vez que se utilice.

La confiabilidad asegura que el sistema opere de forma estable y correcta, orientando tanto el desarrollo como el diseño hacia una 
solución segura, consistente y con minimo riesgo de fallos posible.

##### 2.3.4.1 Característica 1 _CAR-CONF-0003_

El sistema debe realizar respaldos periódicos de la información para asegurar su integridad

Esta característica del atributo de calidad confiabilidad garantiza que la información del sistema pueda recuperarse en caso de
fallos, errores o pérdidas de datos, preservando su integridad y consistencia, y orienta el diseño hacia un sistema confiable, 
capaz de proteger la información y recuperarla oportunamente ante cualquier incidente que comprometa los datos.

##### 2.3.4.1.1 Escenario de calidad 1 _ESC-CAL-CONF-0008_

Cuando el sistema se encuentre en operación, debe realizar respaldos automáticos de la base de datos en intervalos definidos

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos automáticos de respaldo, almacenamiento
seguro y procedimientos de restauración, asegurando la protección de la información y la continuidad operativa. Además,
establece criterios claros para verificar la ejecución periódica y exitosa de las copias de seguridad.

---
| Código                | ESC-CAL-CONF-0008                                                                                                                                                                          |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe realizar respaldos automáticos de la base de datos en intervalos definidos                                                                                                 |
| **Objetivo**          | Garantizar la integridad y disponibilidad de la información mediante la generación periódica de respaldos automáticos que permitan la recuperación de datos ante fallos o pérdidas         |
| **Criterio de éxito** | El sistema ejecuta respaldos automáticos de la base de datos en los intervalos configurados, asegurando que la información pueda ser recuperada de manera oportuna                         |
| **Prerequisitos**     | 1. El sistema debe estar disponible y operativvo en ambiente productivo <br> 2. La base de datos  debe estar accesible  <br>  3. El sistema debe contar con una automatizado de respaldos  |

| Fuente del estímulo           | Estímulo                                                      | Ambiente                                 | Artefacto                | Respuesta                                                                                              | Medida de la respuesta                                                                                                                                                                                                                                                              |
|-------------------------------|---------------------------------------------------------------|------------------------------------------|--------------------------|--------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sistema (proceso automático)  | Ejecución programada de respaldo según intervalo configurado  | Operación normal en ambiente productivo  | Sistema y Base de datos  | El sistema realiza automáticamente el respaldo de la base de datos y lo almacena en el medio definido  | Los respaldos se ejecutan de forma automática según la programación definida, cumpliendo al menos el 98% de las ejecuciones dentro de un ventana de tiempo de 5 minutos. El 98% de los respaldos deben completarse correctamente, garantizando su disponibilidad para recuperación  |



#### 2.3.5 Atributo calidad Capacidad para ser administrado

El atributo de calidad de capacidad para ser administrado se refiere a qué tan fácil es gestionar, supervisar, mantener y 
ajustar el sistema en su funcionamiento diario. El sistema debe permitir que los administradores puedan controlarlo, 
diagnosticarlo y resolver problemas sin complicaciones y de la manera más simple posible.

Durante el desarrollo, este atributo influye en la forma en que se desarrolla el sistema para que sea fácil de operar y mantener, 
por ejemplo, facilitando la configuración del sistema sin necesidad de modificar código, incluyendo mensajes de error claros y
útiles, estructurando el código de forma modular para facilitar ajustes.
Lo cual permite que el sistema sea más fácil de controlar y ajustar una vez esté en funcionamiento.

##### 2.3.5.1 Característica 1 _CAR-CADMI-0002_
El sistema debe permitir configurar el tiempo máximo de inactividad antes de que se efectúe un cierre de sesión automático

Esta característica permite que el sistema sea ajustable y controlado por usuarios autorizados sin necesidad de modificar 
el código. Lo cual orienta el diseño y desarrollo de la solución hacia un sistema flexible y administrable, donde los parámetros
de funcionamiento pueden ajustarse fácilmente, mejorando la mantenibilidad y adaptabilidad del sistema.

##### 2.3.5.1.1 Escenario de calidad 1 _ESC-CAL-CADMI-0004_

Durante la configuración del sistema, cuando el administrador accede al módulo de seguridad para ajustar las políticas de acceso 
de la empresa, el sistema debe permitir configurar el tiempo máximo de inactividad permitido antes de que una sesión se cierre 
automáticamente, estableciendo un valor en minutos que será aplicado y confirmado con un mensaje de exito que debe ser mostrado
en un tiempo menor a 3 segundos, garantizando que las sesiones inactivas se cierren según la política definida para proteger la
seguridad del sistema.

Este escenario orienta el diseño del sistema hacia la implementación de módulos de gestión de parámetros configurables y 
validación inmediata de cambios, asegurando que las configuraciones aplicadas tengan efecto de forma controlada y verificable. 

---
| Código                | ESC-CAL-CADMI-0004                                                                                                                                                                                                                                                                                                                                                  |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe permitir configurar el tiempo máximo de inactividad de las sesiones                                                                                                                                                                                                                                                                                 |
| **Objetivo**          | Permitir al administrador definir políticas de seguridad relacionadas con la gestión de sesiones, específicamente el tiempo máximo de inactividad antes del cierre automático                                                                                                                                                                                       |
| **Criterio de éxito** | El administrador configura correctamente el tiempo de inactividad y el sistema aplica el valor definido, mostrando un mensaje de confirmación en un tiempo menor o igual a 3 segundos                                                                                                                                                                               |
| **Prerequisitos**     | 1. El administrador debe estar autenticado en el sistema <br>  2. Debe existir un módulo de configuración de seguridad <br> 3. El sistema debe permitir modificar parámetros de tiempo de espera por inactividad en la sesión <br> 4. Debe existir un valor configurable de tiempo de inactividad <br>   5. El sistema debe poder mostrar mensajes de confirmación  |

| Fuente del estímulo        | Estímulo                                                                | Ambiente                                 | Artefacto | Respuesta                                                                                          | Medida de la respuesta                                                                                                         |
|----------------------------|-------------------------------------------------------------------------|------------------------------------------|-----------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Administrador del sistema  | Configurar el tiempo máximo de inactividad de sesión y guardar cambios  | Operación normal en ambiente productivo  | Sistema   | El sistema guarda la configuración definida y muestra un mensaje de confirmación al administrador  | El mensaje de confirmación se muestra en un tiempo menor o igual a 3 segundos y la configuración queda aplicada correctamente  |


##### 2.3.5.1.2 Escenario de calidad 2 _ESC-CAL-CADMI-0005_

En el momento en el que el administrador desee cambiar políticas de seguridad del sistema debido a variaciones en los procedimientos
internos de la empresa, el sistema debe permitir modificar el tiempo máximo de inactividad permitido antes del cierre automático de 
sesión, aplicando la nueva configuración para todas las sesiones activas e inactivas en un tiempo menor a 3 segundos y mostrando un 
mensaje de éxito

Este escenario el diseño del sistema hacia la implementación de mecanismos de administración centralizada de políticas de
seguridad, propagación inmediata de configuraciones y control de sesiones en tiempo real, asegurando que los cambios de seguridad
tengan efecto inmediato en todo el sistema. 

---
| Código                | ESC-CAL-CADMI-0005                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | Actualización inmediata de tiempo de inactividad para cierre de sesión                                                                                                                                                                                                                                                                                                                   |
| **Objetivo**          | Garantizar que el sistema permita al administrador modificar el tiempo de inactividad y aplicar los cambios de forma inmediata a todas las sesiones del sistema                                                                                                                                                                                                                          |
| **Criterio de éxito** | El administrador actualiza el tiempo de inactividad y el sistema aplica la nueva configuración a todas las sesiones activas e inactivas en menos de 3 segundos, mostrando un mensaje de confirmación                                                                                                                                                                                     |
| **Prerequisitos**     | 1. El usuario debe ser administrador del sistema <br> 2. El sistema debe estar en operación normal <br> 3. El módulo de configuración de seguridad debe estar disponible <br> 4. Deben existir sesiones activas e inactivas en el sistema <br> 5. La base de datos y servicios deben estar operativos <br> 6. El sistema debe permitir actualización de parámetros globales de seguridad |

| Fuente del estímulo         | Estímulo                                                                       | Ambiente                                | Artefacto | Respuesta                                                                                                      | Medida de la respuesta                                                                                                       |
|-----------------------------|--------------------------------------------------------------------------------|-----------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| Administrador del sistema   | Modificación del tiempo máximo de inactividad para cierre automático de sesión | Operación normal en ambiente productivo | Sistema   | El sistema actualiza la configuración de seguridad y la aplica inmediatamente a todas las sesiones del sistema |  La nueva configuración se propaga y se aplica a todas las sesiones en menos de 3 segundos, con confirmación visual de éxito |


#### 2.3.6 Atributo calidad Escalabilidad 
El atributo de calidad de escalabilidad se refiere a la capacidad de un sistema para crecer y adaptarse al aumento de usuarios,
datos o carga de trabajo sin perder rendimiento ni estabilidad. El sistema puede “aguantar más carga” sin volverse lento o fallar.

La escalabilidad asegura que el sistema pueda crecer sin perder rendimiento, influyendo tanto en el desarrollo como en el diseño
dde la solución buscando que la aplicación pueda adaptarse a un aumento de usuarios, datos y necesidades futuras.

##### 2.3.6.1 Característica 1 _CAR-ESCA-0002_ 

El sistema debe permitir aumentar la capacidad de almacenamiento conforme crezcan los datos del negocio

Esta característica del atributo de calidad escalabilidad define la capacidad del sistema para crecer y 
adaptarse al aumento de la información sin perder rendimiento ni requerir rediseños completos. Orienta el 
diseño y desarrollo hacia un sistema flexible y expansible, capaz de crecer junto con el negocio sin afectar 
su funcionamiento ni rendimiento. Buscando construir soluciones que no limiten el crecimiento de los datos. 
Lo cual orienta a usar bases de datos y estructuras que soporten grandes volúmenes de información, así como implementar 
buenas prácticas como optimización de consultas y uso eficiente de los recursos.


##### 2.3.6.1.1 Escenario de calidad 1 _ESC-CAL-ESCA-0004_

Cuando el sistema almacene mayor cantidad de datos históricos, debe continuar funcionando correctamente

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos de escalabilidad de datos,
optimización de consultas y uso eficiente de almacenamiento, asegurando que el crecimiento del volumen de datos
no afecte la operatividad. 

---
| Código                | ESC-CAL-ESCA-0004                                                                                                                                                                                                                                                   |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | Escalabilidad del sistema frente al crecimiento de datos históricos                                                                                                                                                                                                 |
| **Objetivo**          | Garantizar que el sistema mantenga su funcionamiento correcto a medida que aumenta el volumen de datos históricos almacenados                                                                                                                                       |
| **Criterio de éxito** | El sistema continúa operando correctamente sin degradación significativa del rendimiento a pesar del incremento en la cantidad de datos históricos                                                                                                                  |
| **Prerequisitos**     | 1. El sistema debe estar en operación normal <br> 2. La base de datos debe contener información histórica acumulada <br> 3. Deben existir mecanismos de almacenamiento y consulta operativos <br> 4. Las funcionalidades de consulta y registro deben estar activas |

| Fuente del estímulo                                        | Estímulo                                                  | Ambiente                                | Artefacto                 | Respuesta                                                                                         | Medida de la respuesta                                                                                             |
|------------------------------------------------------------|-----------------------------------------------------------|-----------------------------------------|---------------------------|---------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| Crecimiento progresivo de datos históricos en el sistema   | Incremento continuo del volumen de información almacenada | Operación normal en ambiente productivo | Base de datos del sistema |  El sistema mantiene su funcionamiento correcto y permite acceso eficiente a los datos históricos |  El sistema no presenta fallos ni degradación significativa del rendimiento a medida que crece el volumen de datos |


##### 2.3.6.1.2 Escenario de calidad 2 _ESC-CAL-ESCA-0005_

Cuando el inventario del negocio aumente hasta 5.000 productos registrados, el sistema debe permitir consultarlos sin retrasos 
significativos

Este escenario orienta el diseño del sistema hacia la optimización de consultas, uso de índices en base de datos, paginación de
resultados y mecanismos de cacheo, asegurando que el crecimiento del inventario no afecte la experiencia de usuario ni el
rendimiento general del sistema. Además, establece criterios para evaluar la eficiencia del sistema bajo volúmenes moderados de
datos.

---
| Código                | ESC-CAL-ESCA-0005                                                                                                                                                                                                                                                                                                                       |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe permitir la consulta de hasta 5.000 productos sin retrasos significativos                                                                                                                                                                                                                                               |
| **Objetivo**          | Garantizar que el sistema mantenga un rendimiento adecuado al manejar grandes volúmenes de datos en el inventario, permitiendo consultas eficientes                                                                                                                                                                                     |
| **Criterio de éxito** | El usuario puede consultar el inventario con hasta 5.000 productos registrados sin experimentar retrasos significativos en la respuesta del sistema                                                                                                                                                                                     |
| **Prerequisitos**     | 1. El sistema debe estar en operación en ambiente productivo <br>  2. Deben existir minimo 5.000 productos registrados en el inventario  <br>  3. La base de datos debe estar disponible y optimizada  <br>  4.  El sistema debe contar con mecanismos de consulta eficientes  <br> 5. El usuario debe estar autenticado en el sistema  |

| Fuente del estímulo  | Estímulo                                                            | Ambiente                                 | Artefacto | Respuesta                                                                                   | Medida de la respuesta                                                                         |
|----------------------|---------------------------------------------------------------------|------------------------------------------|-----------|---------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| Usuario del sistema  | Solicitud de consulta del inventario con alto volumen de productos  | Operación normal en ambiente productivo  | Sistema   | El sistema procesa la consulta y muestra la información del inventario de manera eficiente  | El sistema responde a la consulta de hasta 5.000 productos en un tiempo máximo de 3 segundos.  |

##### 2.3.6.1.3 Escenario de calidad 3 _ESC-CAL-ESCA-0006_

Cuando el sistema almacene datos de múltiples años de operación, debe permitir consultarlos fácilmente

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos de almacenamiento histórico estructurado, 
indexación eficiente y estrategias de consulta optimizada, asegurando la accesibilidad de la información a largo plazo. 

---
| Código                | ESC-CAL-ESCA-0006                                                                                                                                                                                                                                                                                                                                             |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | Acceso eficiente a datos históricos                                                                                                                                                                                                                                                                                                                           |
| **Objetivo**          | Garantizar que el sistema permita consultar información histórica acumulada durante múltiples años de operación de manera eficiente                                                                                                                                                                                                                           |
| **Criterio de éxito** | El sistema permite consultar datos históricos de añoa anteriores de forma clara, completa y sin retrasos significativos en la respuesta                                                                                                                                                                                                                       |
| **Prerequisitos**     | 1. El sistema debe estar en operación normal <br> 2. La base de datos debe contener información histórica de múltiples años <br> 3. Deben existir mecanismos de consulta y filtrado de información <br> 4. El sistema debe contar con índices o estructuras de optimización de datos <br> 5. El usuario debe tener permisos de acceso a información histórica |

| Fuente del estímulo  | Estímulo                                                          | Ambiente                                 | Artefacto | Respuesta                                                                                       | Medida de la respuesta                                                                                       |
|----------------------|-------------------------------------------------------------------|------------------------------------------|-----------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Usuario del sistema  | Solicitud de consulta de información histórica de años anteriores |  Operación normal en ambiente productivo | Sistema   | El sistema recupera y muestra la información histórica solicitada de forma completa y eficiente | Las consultas a datos históricos de múltiples años se ejecutan sin degradación significativa del rendimiento |



#### 2.3.7 Atributo calidad Trazabilidad 

El atributo de calidad de trazabilidad se refiere a la capacidad de un sistema para seguir y registrar el rastro de las acciones,
datos o cambios que ocurren dentro de él, de forma que se pueda saber qué pasó, cuándo pasó, quién lo hizo y por qué ocurrió, lo 
cual permite “rastrear” todo lo que sucede en el sistema, lo que ayuda a mejorar el control, la seguridad, la auditoría y la 
corrección de errores, influyendo directamente en cómo se desarrolla y diseña el software, ya que se busca implementar mecanismos
que permitan registrar y seguir el comportamiento del sistema, como Logs (registros de eventos) de usuarios y acciones, historial
de cambios en datos (quién modificó qué y cuándo), identificación de usuarios en cada operación y registro de errores y eventos 
del sistema.

##### 2.3.7.1 Característica 1 _CAR-TRAZ-0001_

El sistema debe registrar qué usuario creó cada factura de alquiler para permitir seguimiento de operaciones

Esta característica permite seguir el rastro de las acciones realizadas dentro del sistema, identificando quién hizo qué
y en qué momento, orientando el diseño hacia el desarrollo de un sistema auditable y controlado, donde es posible rastrear 
el origen de cada operación, mejorando la transparencia y el control de las acciones dentro del sistema.

##### 2.3.7.1.1 Escenario de calidad 1 _ESC-CAL-TRAZ-0001_

Cuando un usuario genere una factura de alquiler, el sistema debe registrar el usuario responsable y la fecha en menos de 1 
segundo.

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos de auditoría, registro de eventos en tiempo
real y almacenamiento eficiente de metadatos asociados a las transacciones, asegurando que cada operación quede correctamente
atribuida a un usuario y momento específico. Además, establece criterios medibles de rendimiento para el registro de información
de trazabilidad.

---
| Código                | ESC-CAL-TRAZ-0001                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe registrar la trazabilidad en la generación de facturas de alquiler                                                                                                                                                        |
| **Objetivo**          | Garantizar el seguimiento de las operaciones realizadas en el sistema mediante el registro del usuario responsable y la fecha de generación de facturas                                                                                   |
| **Criterio de éxito** | El sistema registra correctamente el usuario responsable y la fecha de generación de la factura en un tiempo menor o igual a 1 segundo                                                                                                    |
| **Prerequisitos**     | 1. El usuario debe estar autenticado en el sistema <br>   2. El sistema debe permitir la generación de facturas de alquiler <br> 3. La base de datos debe estar disponible <br> 4. Debe existir un mecanismo de registro de trazabilidad  |

| Fuente del estímulo | Estímulo                                 | Ambiente                                 | Artefacto                | Respuesta                                                                              | Medida de la respuesta                                                                                                         |
|---------------------|------------------------------------------|------------------------------------------|--------------------------|----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Usuario del sistema | Generación de una factura de alquiler    | Operación normal en ambiente productivo  | Sistema y Base de datos  | El sistema registra automáticamente el usuario responsable y la fecha de la operación  | El registro de trazabilidad se realiza en un tiempo menor o igual a 1 segundo y la información queda almacenada correctamente  |



##### 2.3.7.1.2 Escenario de calidad 2 _ESC-CAL-TRAZ-0002_

Cuando se consulte una factura almacenada, el sistema debe mostrar quién la creó y cuándo fue creada

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos de auditoría y trazabilidad visibles en 
las consultas, asegurando que los metadatos de creación de las transacciones sean accesibles de forma consistente. 

---
| Código                | ESC-CAL-TRAZ-0002                                                                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | Visualización de trazabilidad en la consulta de facturas                                                                                                                                                                                                                                  |
| **Objetivo**          | Garantizar que al consultar una factura almacenada se muestre el usuario creador y la fecha de creación de la factura                                                                                                                                                                     |
| **Criterio de éxito** | Al consultar una factura, el sistema muestra correctamente el usuario que la creó y la fecha en la que fue creada                                                                                                                                                                         |
| **Prerequisitos**     | 1. El usuario debe estar autenticado en el sistema <br>   2. El sistema debe permitir la busqueda de facturas de alquiler <br> 3. La base de datos debe estar disponible <br> 4. Debe existir un mecanismo de registro de trazabilidad <br> 5. El usuario debe tener permisos de consulta |

| Fuente del estímulo  | Estímulo                            | Ambiente                                | Artefacto                | Respuesta                                                                                             | Medida de la respuesta                                                                           |
|----------------------|-------------------------------------|-----------------------------------------|--------------------------|-------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| Usuario del sistema  | Consulta de una factura de alquiler | Operación normal en ambiente productivo |  Sistema y Base de datos | El sistema muestra la información de la factura incluyendo el usuario creador y la fecha de creación  | La información de trazabilidad se muestra correctamente al consultar cualquier factura existente |



##### 2.3.7.2 Característica 2 _CAR-TRAZ-0002_

El sistema debe registrar quién modifica los pedidos o reservas de alquiler

Esta característica permite identificar el origen y la historia de los cambios realizados sobre la información del sistema, 
orientando el diseño hacia el desarrollo de un sistema transparente y auditable, donde cada modificación queda registrada, 
permitiendo seguimiento, control y responsabilidad sobre las acciones realizadas en el sistema.

##### 2.3.7.2.1 Escenario de calidad 1 _ESC-CAL-TRAZ-0003_

Cuando un usuario modifique un pedido de alquiler, el sistema debe registrar el usuario responsable, fecha y hora del cambio

Este escenario orienta el diseño del sistema hacia la implementación de mecanismos de auditoría de cambios, registro de eventos
de modificación y almacenamiento de metadatos asociados a cada actualización, asegurando la integridad histórica de la información.

---
| Código                | ESC-CAL-TRAZ-0003                                                                                                                                                                                                                                                                               |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nombre**            | El sistema debe registrar la trazabilidad en la modificación de pedidos de alquiler                                                                                                                                                                                                             |
| **Objetivo**          | Garantizar el seguimiento y control de cambios en los pedidos de alquiler mediante el registro del usuario responsable, fecha y hora de la modificación                                                                                                                                         |
| **Criterio de éxito** | El sistema registra en cada modificación de un pedido el usuario responsable, la fecha y la hora exacta de la operación, garantizando que esta información quede asociada de forma única a cada cambio realizado                                                                                |
| **Prerequisitos**     | 1. El usuario debe estar autenticado en el sistema <br> 2. Deben existir pedidos de alquiler previamente registrados  <br> 3. El sistema debe permitir la modificación de pedidos <br> 4. La base de datos debe estar disponible <br>  5. Debe existir un mecanismo de auditoría o trazabilidad |

| Fuente del estímulo  | Estímulo                               | Ambiente                                 | Artefacto                | Respuesta                                                                                                             | Medida de la respuesta                                                                                                                                                                                                                                            |
|----------------------|----------------------------------------|------------------------------------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Usuario del sistema  | Modificación de un pedido de alquiler  | Operación normal en ambiente productivo  | Sistema y Base de datos  | El sistema guarda la modificación y registra automáticamente el usuario responsable, la fecha y la hora de la misma.  | El 100% de las modificaciones de pedidos deben generar un registro de trazabilidad con usuario, fecha y hora, consistente en la base de datos en un tiempo ≤ 1 segundo <br><br>  No se permite la existencia de modificaciones sin registro de auditoría asociado |





---
### 2.4 Funcionalidades críticas

Las funcionalidades críticas son aquellas características esenciales que el sistema debe tener para cumplir con sus objetivos 
principales y satisfacer las necesidades de sus usuarios. Estas funcionalidades son fundamentales para el éxito del proyecto, 
ya que, si alguna de ellas no se implementa de manera efectiva, podría comprometer la viabilidad del sistema y la satisfacción 
del usuario.

---
###### *Funcionalidades críticas* 

---

| Identificador | Requisito Funcional                                                                                                                                                                                                                                                                                   | Justificación                                                                                                                                                                                                                                                                                                                                                               | Impacto                   |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
| RF-002        | El sistema debe implementar un doble factor de verificación para iniciar sesión.                                                                                                                                                                                                                      | Protege el sistema de accesos indebidos y mantiene la confianza en el aplicativo, aunque requiere validación técnica por integración externa y complejidad de implementación.                                                                                                                                                                                               | Humano y Reto técnico     |
| RF-004        | El sistema debe restringir el acceso a módulos y funcionalidades según el rol del usuario autenticado.                                                                                                                                                                                                | Reduce errores operativos y de seguridad al limitar acciones según las responsabilidades de cada usuario.                                                                                                                                                                                                                                                                   | Humano                    |
| RF-013        | El sistema debe permitir desactivar (inhabilitar) un cliente sin eliminarlo permanentemente del sistema.                                                                                                                                                                                              | Permite bloquear clientes con problemas reincidentes sin perder su información histórica. Esto es clave para controlar riesgos financieros, evitar reincidencias y mantener trazabilidad para auditoría. Eliminar clientes implicaría perder datos críticos que afectan el análisis y la toma de decisiones del negocio.                                                    | Financiero                |
| RF-035        | El sistema debe actualizar automáticamente el inventario disponible al confirmar una reserva o pedido, al cancelarlo, y al registrar la salida o el retorno de productos.                                                                                                                             | Es el punto más crítico del sistema porque conecta pedidos, inventario y operación real. Si el inventario no se actualiza correctamente al reservar, cancelar, entregar o devolver productos, se generan sobreventas, pérdidas económicas y desorden total en la operación. Esta funcionalidad garantiza la coherencia del sistema frente a la realidad física del negocio. | Financiero                |
| RF-042        | El sistema debe validar la disponibilidad de inventario en la fecha indicada al momento de crear o modificar un pedido.                                                                                                                                                                               | Evita comprometer productos que no están disponibles en las fechas requeridas. Si esta validación falla, se generan incumplimientos con clientes, reprocesos operativos y pérdidas económicas. Es clave para la promesa de valor del negocio de alquiler.                                                                                                                   | Financiero / Imagen       |
| RF-053        | El sistema debe permitir registrar productos devueltos con daños o faltantes, con trazabilidad para gestionar cobros adicionales en la factura.                                                                                                                                                       | Permite identificar pérdidas y asociarlas a cobros adicionales. Sin esta funcionalidad, los daños o pérdidas no se registran correctamente, generando pérdidas económicas directas y falta de control sobre el estado real del inventario.                                                                                                                                  | Financiero                |
| RF-056        | El sistema debe permitir generar una factura a partir de un pedido confirmado o cerrado. La factura debe incluir: código único, fecha de generación, datos del cliente, datos de la empresa, productos con cantidades y precios, subtotal, descuentos y costos adicionales si estos aplican, y total. | Es el mecanismo principal de monetización del sistema. Si no se puede generar correctamente una factura basada en el pedido, el negocio no puede cobrar de manera estructurada ni llevar control financiero. Es esencial para formalizar ingresos.                                                                                                                          | Financiero                |
| RF-069        | Los datos de la empresa configurados deben incluirse automáticamente en la generación de facturas y documentos del sistema.                                                                                                                                                                           | Garantiza que los documentos generados sean formales, completos y coherentes con la identidad del negocio. Su ausencia afecta la presentación profesional de la empresa y la validez de los documentos frente al cliente.                                                                                                                                                   | Humano / Imagen           |
| RF-071        | El sistema debe registrar automáticamente un log de auditoría por cada operación crítica (creación, edición, eliminación o cambio de estado) sobre: pedidos, facturas, inventario, clientes, empleados y productos.                                                                                   | Permite rastrear todas las acciones relevantes dentro del sistema (quién hizo qué y cuándo). Sin esta funcionalidad, no es posible auditar errores, detectar fraudes o resolver conflictos, afectando directamente el control interno del negocio.                                                                                                                          | Humano                    |
| RF-079        | El sistema debe integrar un módulo de análisis con IA que procese los datos históricos del negocio y genere recomendaciones automáticas.                                                                                                                                                              | Es una de las funcionalidades más complejas del sistema, ya que implica procesamiento de datos históricos, modelos de análisis y generación de recomendaciones automáticas. Requiere validación técnica (POC) para definir viabilidad, alcance y valor real dentro de las restricciones del proyecto.                                                                       | Reto técnico / Financiero |


---

## 3. Tácticas y estrategias

Una **_estrategia_** es la visión general o el enfoque principal que se sigue para cumplir con los requisitos del sistema y 
alcanzar ciertos objetivos a largo plazo, como rendimiento, escalabilidad, seguridad o facilidad de mantenimiento. 
Define la estructura global y las decisiones arquitectónicas clave que guiarán el diseño del sistema. 

Las _**tácticas**_ son técnicas o métodos específicos que se usan para abordar problemas concretos o alcanzar ciertos objetivos. 
Las tácticas son como los patrones específicos de diseño que se implementan para resolver desafíos particulares en la arquitectura.

---
######  *Tácticas y estrategias* 

---

| Tácticas - estrategias                                                    | Descripción                                                                                                                                                                                                                    | Justificación                                                                                                                                                                                                                                                                                                                      | Priorización |
|---------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| Desarrollo de módulo de gestión de usuarios a la medida                   | Construir a la medida un componente para gestionar los usuarios, sus permisos y contraseñas.                                                                                                                                   | Un módulo de gestión de usuarios personalizado permite un mayor control sobre los permisos y configuraciones específicos del sistema, mejorando la seguridad y adecuación a las necesidades específicas de la aplicación                                                                                                           | 4            |
| Gestor de identidad y acceso _( **IAM** Identity and Access Management )_ | Es un componente experto en la gestión de identidades y roles de usuarios, que permite acelerar el desarrollo tomando como base las capacidades que ya tiene predefinidas                                                      | La integración de un IAM facilita una gestión más segura y eficiente de usuarios y sus permisos por roles, aprovechando funcionalidades preconfiguradas del componente y reduciendo el tiempo de desarrollo para autenticar y gestionar identidades de manera robusta                                                              | 1            |
| Autenticación multifactor (MFA)                                           | Implementar un sistema de autenticación multifactor (por ejemplo, contraseña y código de un solo uso enviado al dispositivo móvil del usuario) para mejorar la seguridad de los accesos                                        | La MFA agrega una capa adicional de seguridad, minimizando el riesgo de accesos no autorizados, ya que requiere que el usuario valide su identidad con un segundo factor, protegiendo información sensible                                                                                                                         | 1            |
| Uso de captcha                                                            | Añadir captcha en los formularios de inicio de sesión para evitar ataques automatizados, como bots que intentan acceder a cuentas mediante fuerza bruta                                                                        | La implementación de captcha  en los formularios de inicio de sesión evita que bots y scripts automatizados realicen intentos de acceso, lo que contribuye a proteger el sistema de ataques automatizados y asegura accesos legítimos                                                                                              | 3            |
| Control de acceso basado en roles (RBAC)                                  | Definir roles claros para los usuarios del sistema, garantizando que solo quienes tienen los permisos adecuados puedan acceder o modificar información personal sensible                                                       | RBAC garantiza que solo los usuarios con permisos específicos accedan a información sensible, lo que minimiza el riesgo de acceso indebido y aumenta la seguridad y control de los datos personales                                                                                                                                | 3            |
| Temporizador de inactividad ajustable                                     | Implementar un temporizador ajustable que monitorice la actividad del usuario, reiniciándose con cada interacción y solo desconectando tras un periodo de inactividad definido previamente por el administrador                | Un temporizador ajustable permite que la sesión permanezca activa con cada interacción del usuario y desconecta solo después de un periodo prolongado de inactividad, lo que mejora la experiencia del usuario y garantiza que las sesiones inactivas se cierren según la política definida para proteger la seguridad del sistema | 4            |
| Tooltips y mensajes emergentes                                            | Implementar tooltips (consejos en pantalla) y mensajes emergentes que expliquen las funciones principales cuando el usuario interactúa por primera vez con cada una                                                            | Los tooltips y mensajes emergentes brindan explicaciones en contexto de las funciones principales, facilitando el aprendizaje progresivo y ayudando a los usuarios a comprender el propósito de cada opción cuando la exploran por primera vez                                                                                     | 1            |
| Sistema de diseño modular                                                 | Implementar un sistema de diseño modular que facilite la reutilización de componentes visuales coherentes con la marca, asegurando una estructura visual unificada en toda la aplicación                                       | Un sistema de diseño modular permite la reutilización de componentes visuales, lo cual garantiza una apariencia y funcionamiento uniformes, además de facilitar el desarrollo y mantenimiento de la aplicación, asegurando coherencia visual y optimización de recursos                                                            | 1            |
| Optimización de consultas a la base de datos                              | Optimizar las consultas SQL utilizadas en la aplicación para reducir el tiempo de respuesta, implementando índices eficientes y evitando consultas innecesarias o excesivamente complejas                                      | Optimizar las consultas SQL mejora la velocidad de respuesta de la aplicación, minimizando el tiempo que toma procesar las solicitudes y reduciendo la carga de trabajo de la base de datos, lo cual contribuye directamente a una experiencia de usuario más ágil                                                                 | 3            |
| Uso de servidores de contenido (CDN)                                      | Implementar una red de entrega de contenido (CDN) para distribuir el contenido estático de la aplicación (como imágenes, CSS y JavaScript) desde servidores ubicados geográficamente cerca de los usuarios finales             | Los CDN distribuyen el contenido estático desde servidores cercanos al usuario final, reduciendo el tiempo de carga y mejorando el rendimiento general de la aplicación, independientemente de la ubicación geográfica                                                                                                             | 1            |
| Uso de microservicios                                                     | Descomponer la aplicación en microservicios independientes, permitiendo escalar individualmente cada componente según su necesidad de uso y mejorar el rendimiento al distribuir la carga de manera modular                    | La arquitectura de microservicios permite escalar y gestionar individualmente cada componente de la aplicación, mejorando la eficiencia en la distribución de la carga y optimizando el rendimiento durante el uso concurrente                                                                                                     | 1            |
| Registro de cambios en el sistema                                         | Implementar un sistema que registre cada cambio realizado en la configuración del sistema, guardando detalles como el usuario que realizó el cambio, la fecha, la hora y los valores anteriores y nuevos del campo modificado  | Registrar los cambios en el sistema proporciona una trazabilidad completa, permitiendo identificar quién realizó un cambio, cuándo y qué se modificó, lo cual es fundamental para auditorías y resolución de problemas                                                                                                             | 1            |

---

## 4. Modelo de contexto

Un modelo de contexto es una representación visual o esquemática que muestra la relación de un sistema con su entorno y todas las entidades 
externas que interactúan con él. Sirve para comprender qué entra y qué sale del sistema, así como quiénes son los actores o elementos externos 
involucrados. 

El objetivo es tener una visión clara de los límites del sistema y las interacciones principales con su entorno, lo que facilita entender 
el alcance y los requisitos del proyecto.
---

###### **_Diagrama modelo de contexto_**

---
![img_6.png](modeloContexto.png)

---

### **Documentación modelo de contexto**

---

#### DNS Domain Name System
<u>Motivación</u>: Proveer resolución de nombres de dominio para abstraer la dirección IP de la infraestructura 
subyacente, permitiendo que el sistema Lilfac sea accesible mediante un FQDN (Fully Qualified Domain Name) en lugar de
direcciones IP directas lo que permite a los usuarios acceder al sistema Lilfac mediante un nombre de dominio legible, sin 
necesidad de conocer direcciones IP internas de la infraestructura.
También es indispensable para la operación de componentes como el WAF y el CDN que dependen de resolución DNS para el 
enrutamiento del tráfico.

<u>Uso</u>: Resolver las consultas DNS que provienen de los clientes, traduciendo el nombre de dominio de la aplicación
en la dirección IP del siguiente componente en la cadena de red.

<u>Justificación</u>: Sin este componente, el sistema no sería accesible desde Internet de forma amigable ni escalable.
Además, permite abstraer la infraestructura real del sistema, facilitando cambios futuros de servidores o regiones sin 
afectar la experiencia del usuario, La ausencia del DNS gestionado implicaría una dependencia directa en IPs estáticas, 
lo que haría inviable cualquier estrategia de alta disponibilidad.

#### WAF Web Application Firewall

<u>Motivación</u>: Proteger el sistema Lilfac contra ataques externos estableciendo un perímetro de seguridad a nivel
de capa 7 del modelo OSI _(Capa de aplicación)_ que inspeccione el tráfico HTTP/HTTPS antes de que alcance cualquier 
componente interno del sistema, mitigando vectores de ataque dirigidos específicamente a la capa de aplicación.

<u>Uso</u>: Inspeccionar y filtrar todo el tráfico HTTP/HTTPS entrante, bloqueando solicitudes que contengan patrones
de ataque conocidos como SQL Injection, XSS (Cross-Site Scripting), escaneo de vulnerabilidades o intentos de denegación
de servicio.

<u>Justificación</u>: Al ser una aplicación web expuesta a Internet, si no tuviese inspección en la capa 7 quedaría 
vulnerable a exploits automatizados que no son detectables por firewalls de red tradicionales. 
El WAF actúa como primera línea de defensa activa, reduciendo significativamente la superficie
de ataque antes de que cualquier solicitud llegue al CDN, al Frontend o al Backend.


#### CDN Content Delivery Network

<u>Motivación</u>: Garantizar que los usuarios de Lilfac reciban la interfaz de usuario con la menor latencia posible,
independientemente de su ubicación geográfica.

<u>Uso</u>: Distribuir y servir los archivos estáticos del Frontend Lilfac, como HTML, CSS, JavaScript e imágenes, 
desde nodos de red cercanos al usuario. Además, enrutar las solicitudes dinámicas hacia el API Gateway.

<u>Justificación</u>: Mejora notablemente la velocidad de carga de la aplicación al evitar que cada solicitud de 
contenido estático recorra toda la cadena hasta el servidor de origen. Al mismo tiempo, actúa como punto de
distribución inteligente del tráfico dinámico hacia el interior del sistema.


#### API Gateway

<u>Motivación</u>: Centralizar y controlar el acceso de todos los clientes implementando un único punto de entrada 
para todas las solicitudes hacia el Backend Lilfac, centralizando funciones transversales como autenticación, 
autorización, control de tráfico y observabilidad que de otro modo deberían ser implementadas de forma redundante 
en cada servicio del Backend.

<u>Uso</u>: Recibir todas las solicitudes dinámicas provenientes del Frontend, validar los tokens de autenticación 
en conjunto con el IAM, aplicar políticas de seguridad como rate limiting, y enrutar cada solicitud al endpoint
correspondiente del Backend Lilfac.

<u>Justificación</u>: Evita que los clientes interactúen directamente con el Backend, reduciendo la exposición de la
lógica interna del sistema. Centraliza funciones transversales como autenticación, logging de peticiones y 
control de tráfico, simplificando considerablemente la arquitectura del Backend.

#### IAM Identity and access management 

<u>Motivación</u>: Centralizar la gestión del ciclo de vida de identidades digitales y el control de acceso basado en 
roles (RBAC) para todos los usuarios y servicios que interactúan con el sistema Lilfac lo cual garantiza que únicamente
los usuarios y servicios autorizados puedan acceder a los recursos y funcionalidades del sistema.

<u>Uso</u>: Gestionar la autenticación de usuarios mediante la validación de credenciales y la emisión de tokens de 
seguridad, así como controlar la autorización definiendo qué acciones puede ejecutar cada usuario según su rol 
dentro del sistema.

<u>Justificación</u>: Es el componente que sostiene la seguridad de acceso de todo el sistema. Sin él, no existiría 
un mecanismo centralizado y confiable para distinguir entre un usuario administrador, un operador o un cliente,
ni para proteger los datos sensibles que maneja Lilfac.



#### CI /CD pipeline 

<u>Motivación</u>: Automatizar el ciclo completo de construcción, pruebas y despliegue del software de Lilfac, 
reduciendo el riesgo de errores manuales en cada entrega.

<u>Uso</u>: Detectar cambios en el repositorio de código, ejecutar automáticamente las pruebas definidas, construir
los artefactos del Frontend y del Backend, y desplegarlos en los ambientes correspondientes de forma controlada
y repetible.

<u>Justificación</u>: Permite que el equipo de desarrollo entregue nuevas funcionalidades y correcciones de forma ágil
y segura. Garantiza que ningún cambio llegue a producción sin haber pasado por un proceso de validación, lo que 
reduce considerablemente los tiempos de detección de errores y los riesgos asociados a los despliegues.



#### Cache

<u> Motivación</u>: Reducir la carga sobre la base de datos SQL y mejorar los tiempos de respuesta del Backend de 
Lilfac ante consultas frecuentes o costosas.

<u>Uso</u>: Almacenar temporalmente resultados de consultas que el Backend solicita con alta frecuencia, de 
manera que puedan ser retornados directamente sin necesidad de ejecutar nuevamente la consulta completa 
contra la base de datos.

<u>Justificación</u>: En un sistema que puede recibir múltiples solicitudes concurrentes, acceder repetidamente
a la base de datos para los mismos datos representa un cuello de botella. La caché permite escalar el rendimiento
del sistema sin incrementar los recursos de base de datos, mejorando la experiencia del usuario final.



#### Base de datos

<u> Motivación</u> : Proveer almacenamiento persistente, estructurado y confiable para todos los datos de negocio 
que gestiona el sistema Lilfac.

<u>Uso</u>: Guardar y gestionar la información crítica del sistema como usuarios, registros operativos, transacciones
y cualquier entidad del dominio del negocio, garantizando integridad referencial y consistencia de los datos.

<u>Justificación</u>: Es el núcleo de persistencia del sistema. Toda la lógica de negocio del Backend depende de la 
capacidad de leer y escribir datos de forma confiable. Una base de datos SQL relacional asegura la integridad de los datos y permite consultas complejas necesarias para las operaciones del sistema.



#### CDC Change Data Capture

<u> Motivación</u> : Detectar y propagar en tiempo real los cambios que ocurren en la base de datos SQL de 
Lilfac sin impactar el rendimiento del sistema principal.

<u> Uso</u> : Capturar eventos de inserción, actualización y eliminación en la base de datos y ponerlos a 
disposición de otros procesos o sistemas que necesiten reaccionar ante esos cambios, como procesos de auditoría,
sincronización o integración con sistemas externos.

<u> Justificación</u> : Permite que el sistema evolucione hacia integraciones y procesos reactivos sin necesidad
de implementar consultas periódicas a la base de datos, lo que sería ineficiente y costoso. Facilita la 
trazabilidad de cambios y sienta las bases para capacidades de auditoría y análisis de datos en tiempo real.


#### Parameter Catalog

<u> Motivación</u> : Centralizar la gestión de los parámetros de configuración del sistema Lilfac para que puedan
ser modificados sin necesidad de redesplegar el Backend.

<u>Uso</u>: Almacenar y exponer vía API valores configurables del sistema como umbrales, límites operativos, 
indicadores de comportamiento y cualquier parámetro que controle la lógica de negocio del Backend.

<u>Justificación</u>: Separa la configuración del código, lo que otorga flexibilidad operativa al sistema. 
Un cambio en un parámetro de negocio no implica un nuevo despliegue, reduciendo el riesgo operativo y permitiendo
ajustes rápidos ante cambios en los requisitos del negocio.



#### Message Catalog

<u>Motivación</u>: Centralizar todos los textos, mensajes de error y literales que el sistema Lilfac utiliza 
en sus respuestas hacia el usuario o entre componentes.

<u>Uso</u>: Proveer al Backend y al Frontend un repositorio único de mensajes estandarizados que pueden 
consultarse vía API, garantizando consistencia en la comunicación del sistema y facilitando soporte multiidioma
si el proyecto lo requiere.

<u>Justificación</u>: Evita que los mensajes estén dispersos y duplicados en el código de los distintos componentes.
Asegura uniformidad en la experiencia del usuario y simplifica el mantenimiento, ya que cualquier cambio en un texto
se realiza en un solo lugar.


#### Notification Catalog

<u>Motivación</u>: Centralizar las plantillas de notificación que el sistema Lilfac utiliza para comunicarse con los 
usuarios a través del Notification Gateway.

<u>Uso</u>: Almacenar y exponer las plantillas estructuradas de correos electrónicos, SMS y notificaciones push, 
incluyendo su contenido, formato y variables dinámicas que el Notification Gateway completa antes de enviar cada mensaje.

<u>Justificación</u>: Desacopla el contenido de las notificaciones de la lógica del Backend y del Gateway. 
Permite que las plantillas sean gestionadas y actualizadas de forma centralizada sin modificar el código, 
garantizando consistencia en todas las comunicaciones enviadas a los usuarios.


#### Notification Gateway

Notification Gateway
<u>Motivación</u>: Proveer un canal centralizado y desacoplado para el envío de notificaciones a los usuarios del sistema
Lilfac.

<u>Uso</u>: Recibir instrucciones del Backend indicando qué notificación enviar y a quién, consultar la plantilla 
correspondiente en el Notification Catalog, y ejecutar el envío a través del canal adecuado, ya sea correo electrónico, 
SMS o notificación push.

<u>Justificación</u>: Abstrae al Backend de los detalles técnicos de cada canal de notificación. Si en el futuro se 
agrega un nuevo canal de comunicación, el cambio se realiza únicamente en el Gateway sin afectar la lógica del Backend,
lo que mejora la mantenibilidad y escalabilidad del sistema.



#### Key Vault

<u>Motivación</u>: Proteger todos los secretos, credenciales y claves criptográficas que el sistema Lilfac necesita 
para operar, manteniéndolos fuera del código fuente y de los archivos de configuración.

<u>Uso</u>: Almacenar de forma segura contraseñas de bases de datos, claves de APIs externas, certificados y tokens 
de servicio, permitiendo que el Backend los consulte en tiempo de ejecución mediante acceso controlado y auditado.

<u>Justificación</u>: Elimina el riesgo de exponer información sensible en el repositorio de código o en variables de 
entorno sin cifrar. Centraliza la gestión de secretos con control de acceso granular, lo que facilita la rotación de 
credenciales y el cumplimiento de buenas prácticas de seguridad.


#### APM Application performance monitoring 

<u>Motivación</u>: Tener visibilidad continua sobre el comportamiento, el rendimiento y la salud del sistema Lilfac 
en ambientes productivos.

<u>Uso</u>: Recopilar métricas de rendimiento, trazas de ejecución, registros de errores y excepciones del Backend en
tiempo real, generando alertas automáticas cuando se detectan degradaciones o fallos en el sistema.

<u>Justificación</u>: Sin observabilidad, los problemas en producción son difíciles de detectar y aún más difíciles de
diagnosticar. El APM permite al equipo identificar cuellos de botella, errores recurrentes y comportamientos anómalos 
antes de que impacten negativamente a los usuarios, reduciendo los tiempos de respuesta ante incidentes.




---

## 5. Arquetipo de solución/referencia

Un arquetipo de solución es un modelo o patrón general que representa una forma común de abordar un 
problema específico en un contexto particular. En otras palabras, es una estructura o una plantilla 
que muestra cómo se puede resolver un tipo de desafío de manera efectiva. Estos arquetipos se basan 
en prácticas comprobadas y patrones que han demostrado ser efectivos en contextos similares.
---

###### **_Diagrama Arquetipo de solución/referencia_**

---
<img width="1792" height="862" alt="arquetipoReferencia" src="https://github.com/user-attachments/assets/a9328122-d1d8-4107-abdf-3fc16345d787" />

---

### **Documentación Arquetipo de solución/referencia**

---


#### DNS Domain Name System
<u>Motivación</u>: Proveer resolución de nombres de dominio para abstraer la dirección IP de la infraestructura
subyacente, permitiendo que el sistema Lilfac sea accesible mediante un FQDN (Fully Qualified Domain Name) en lugar de
direcciones IP directas lo que permite a los usuarios acceder al sistema Lilfac mediante un nombre de dominio legible, sin
necesidad de conocer direcciones IP internas de la infraestructura.
También es indispensable para la operación de componentes como el WAF y el CDN que dependen de resolución DNS para el
enrutamiento del tráfico.

<u>Uso</u>: Resolver las consultas DNS que provienen de los clientes, traduciendo el nombre de dominio de la aplicación
en la dirección IP del siguiente componente en la cadena de red.

<u>Justificación</u>: Sin este componente, el sistema no sería accesible desde Internet de forma amigable ni escalable.
Además, permite abstraer la infraestructura real del sistema, facilitando cambios futuros de servidores o regiones sin
afectar la experiencia del usuario, La ausencia del DNS gestionado implicaría una dependencia directa en IPs estáticas,
lo que haría inviable cualquier estrategia de alta disponibilidad.

#### WAF Web Application Firewall

<u>Motivación</u>: Proteger el sistema Lilfac contra ataques externos estableciendo un perímetro de seguridad a nivel
de capa 7 del modelo OSI _(Capa de aplicación)_ que inspeccione el tráfico HTTP/HTTPS antes de que alcance cualquier
componente interno del sistema, mitigando vectores de ataque dirigidos específicamente a la capa de aplicación.

<u>Uso</u>: Inspeccionar y filtrar todo el tráfico HTTP/HTTPS entrante, bloqueando solicitudes que contengan patrones
de ataque conocidos como SQL Injection, XSS (Cross-Site Scripting), escaneo de vulnerabilidades o intentos de denegación
de servicio.

<u>Justificación</u>: Al ser una aplicación web expuesta a Internet, si no tuviese inspección en la capa 7 quedaría
vulnerable a exploits automatizados que no son detectables por firewalls de red tradicionales.
El WAF actúa como primera línea de defensa activa, reduciendo significativamente la superficie
de ataque antes de que cualquier solicitud llegue al CDN, al Frontend o al Backend.


#### CDN Content Delivery Network

<u>Motivación</u>: Garantizar que los usuarios de Lilfac reciban la interfaz de usuario con la menor latencia posible,
independientemente de su ubicación geográfica.

<u>Uso</u>: Distribuir y servir los archivos estáticos del Frontend Lilfac, como HTML, CSS, JavaScript e imágenes,
desde nodos de red cercanos al usuario. Además, enrutar las solicitudes dinámicas hacia el API Gateway.

<u>Justificación</u>: Mejora notablemente la velocidad de carga de la aplicación al evitar que cada solicitud de
contenido estático recorra toda la cadena hasta el servidor de origen. Al mismo tiempo, actúa como punto de
distribución inteligente del tráfico dinámico hacia el interior del sistema.

#### Storage Account

<u>Motivación</u>: Proveer un mecanismo de almacenamiento persistente y altamente disponible para alojar los archivos
estáticos del Frontend del sistema Lilfac, como HTML, CSS, JavaScript, imágenes, íconos y fuentes. Este componente 
permite desacoplar la capa de presentación de la infraestructura de procesamiento, ofreciendo un repositorio optimizado
para servir contenido estático de forma segura y escalable.

<u>Uso</u>: Almacenar los artefactos compilados del Frontend y actuar como origen del CDN, desde donde se distribuyen 
los recursos estáticos a los usuarios finales. Cada vez que se publica una nueva versión de la aplicación, los archivos
generados por el proceso de despliegue se cargan en este componente para quedar disponibles de manera inmediata.

<u>Justificación</u>: Sin este componente, los archivos del Frontend tendrían que hospedarse directamente en servidores
de aplicación, incrementando costos y acoplando innecesariamente la interfaz de usuario con la lógica del negocio. 
El Storage Account ofrece alta durabilidad, disponibilidad y escalabilidad para contenido estático, permitiendo 
desplegar nuevas versiones del Frontend de forma sencilla y sirviendo como origen confiable para el CDN, lo que mejora
el rendimiento y simplifica la arquitectura del sistema.

#### Front End Lilfac

<u>Motivación</u>: Proveer la interfaz gráfica con la que los usuarios interactúan para realizar las operaciones del 
sistema Lilfac, como registrar cliente, registrar empleados, gestionar inventario, crear pedidos y consultar facturas.
Este componente traduce las funcionalidades del negocio en una experiencia visual intuitiva, accesible y fácil de usar.

<u>Uso</u>: Presentar formularios, tablas, reportes y paneles interactivos que permiten capturar información y visualizar
resultados. El Frontend consume los servicios expuestos por el Backend mediante APIs, enviando solicitudes y mostrando al
usuario la información procesada por el sistema.

<u>Justificación</u>: Sin este componente, los usuarios no contarían con un medio práctico para interactuar con el sistema.
Además, al separar la interfaz de usuario de la lógica de negocio, se facilita el mantenimiento, la evolución del diseño y 
la posibilidad de adaptar la aplicación a distintos dispositivos y necesidades de usabilidad sin afectar los componentes 
internos.

#### API Gateway

<u>Motivación</u>: Centralizar y controlar el acceso de todos los clientes implementando un único punto de entrada
para todas las solicitudes hacia el Backend Lilfac, centralizando funciones transversales como autenticación,
autorización, control de tráfico y observabilidad que de otro modo deberían ser implementadas de forma redundante
en cada servicio del Backend.

<u>Uso</u>: Recibir todas las solicitudes dinámicas provenientes del Frontend, validar los tokens de autenticación
en conjunto con el IAM, aplicar políticas de seguridad como rate limiting, y enrutar cada solicitud al endpoint
correspondiente del Backend Lilfac.

<u>Justificación</u>: Evita que los clientes interactúen directamente con el Backend, reduciendo la exposición de la
lógica interna del sistema. Centraliza funciones transversales como autenticación, logging de peticiones y
control de tráfico, simplificando considerablemente la arquitectura del Backend.

#### Back End Lilfac

<u>Motivación</u>: Centralizar la lógica de negocio del sistema Lilfac, implementando las reglas que controlan procesos
como la gestión de inventario, reservas, alquileres, facturación y autenticación de usuarios. Este componente actúa como
núcleo funcional del sistema y garantiza la integridad y consistencia de la información.

<u>Uso</u>: Recibir las solicitudes enviadas por el Frontend, validar los datos, ejecutar las reglas del negocio, 
interactuar con la base de datos y con el Storage Account, y devolver respuestas estructuradas a los clientes. 
También se encarga de aplicar controles de seguridad y auditoría.

<u>Justificación</u>: Sin este componente, no existiría un punto central encargado de procesar las operaciones 
del sistema ni de garantizar que se cumplan las reglas del negocio. El Backend permite desacoplar la lógica funcional
de la interfaz de usuario, facilita la reutilización de servicios y proporciona una arquitectura más segura, mantenible
y escalable.

#### IAM Identity and access management

<u>Motivación</u>: Centralizar la gestión del ciclo de vida de identidades digitales y el control de acceso basado en
roles (RBAC) para todos los usuarios y servicios que interactúan con el sistema Lilfac lo cual garantiza que únicamente
los usuarios y servicios autorizados puedan acceder a los recursos y funcionalidades del sistema.

<u>Uso</u>: Gestionar la autenticación de usuarios mediante la validación de credenciales y la emisión de tokens de
seguridad, así como controlar la autorización definiendo qué acciones puede ejecutar cada usuario según su rol
dentro del sistema.

<u>Justificación</u>: Es el componente que sostiene la seguridad de acceso de todo el sistema. Sin él, no existiría
un mecanismo centralizado y confiable para distinguir entre un usuario administrador, un operador o un cliente,
ni para proteger los datos sensibles que maneja Lilfac.

#### CI /CD pipeline

<u>Motivación</u>: Automatizar el ciclo completo de construcción, pruebas y despliegue del software de Lilfac,
reduciendo el riesgo de errores manuales en cada entrega.

<u>Uso</u>: Detectar cambios en el repositorio de código, ejecutar automáticamente las pruebas definidas, construir
los artefactos del Frontend y del Backend, y desplegarlos en los ambientes correspondientes de forma controlada
y repetible.

<u>Justificación</u>: Permite que el equipo de desarrollo entregue nuevas funcionalidades y correcciones de forma ágil
y segura. Garantiza que ningún cambio llegue a producción sin haber pasado por un proceso de validación, lo que
reduce considerablemente los tiempos de detección de errores y los riesgos asociados a los despliegues.

#### Cache

<u> Motivación</u>: Reducir la carga sobre la base de datos SQL y mejorar los tiempos de respuesta del Backend de 
Lilfac ante consultas frecuentes o costosas.

<u>Uso</u>: Almacenar temporalmente resultados de consultas que el Backend solicita con alta frecuencia, de
manera que puedan ser retornados directamente sin necesidad de ejecutar nuevamente la consulta completa
contra la base de datos.

<u>Justificación</u>: En un sistema que puede recibir múltiples solicitudes concurrentes, acceder repetidamente
a la base de datos para los mismos datos representa un cuello de botella. La caché permite escalar el rendimiento
del sistema sin incrementar los recursos de base de datos, mejorando la experiencia del usuario final.

#### Base de datos

<u> Motivación</u> : Proveer almacenamiento persistente, estructurado y confiable para todos los datos de negocio 
que gestiona el sistema Lilfac.

<u>Uso</u>: Guardar y gestionar la información crítica del sistema como usuarios, registros operativos, transacciones
y cualquier entidad del dominio del negocio, garantizando integridad referencial y consistencia de los datos.

<u>Justificación</u>: Es el núcleo de persistencia del sistema. Toda la lógica de negocio del Backend depende de la
capacidad de leer y escribir datos de forma confiable. Una base de datos SQL relacional asegura la integridad de los datos y permite consultas complejas necesarias para las operaciones del sistema.


#### CDC Change Data Capture

<u> Motivación</u> : Detectar y propagar en tiempo real los cambios que ocurren en la base de datos SQL de 
Lilfac sin impactar el rendimiento del sistema principal.

<u> Uso</u> : Capturar eventos de inserción, actualización y eliminación en la base de datos y ponerlos a 
disposición de otros procesos o sistemas que necesiten reaccionar ante esos cambios, como procesos de auditoría,
sincronización o integración con sistemas externos.

<u> Justificación</u> : Permite que el sistema evolucione hacia integraciones y procesos reactivos sin necesidad
de implementar consultas periódicas a la base de datos, lo que sería ineficiente y costoso. Facilita la 
trazabilidad de cambios y sienta las bases para capacidades de auditoría y análisis de datos en tiempo real.


#### Parameter Catalog

<u> Motivación</u> : Centralizar la gestión de los parámetros de configuración del sistema Lilfac para que puedan
ser modificados sin necesidad de redesplegar el Backend.

<u>Uso</u>: Almacenar y exponer vía API valores configurables del sistema como umbrales, límites operativos,
indicadores de comportamiento y cualquier parámetro que controle la lógica de negocio del Backend.

<u>Justificación</u>: Separa la configuración del código, lo que otorga flexibilidad operativa al sistema.
Un cambio en un parámetro de negocio no implica un nuevo despliegue, reduciendo el riesgo operativo y permitiendo
ajustes rápidos ante cambios en los requisitos del negocio.


#### Message Catalog

<u>Motivación</u>: Centralizar todos los textos, mensajes de error y literales que el sistema Lilfac utiliza
en sus respuestas hacia el usuario o entre componentes.

<u>Uso</u>: Proveer al Backend y al Frontend un repositorio único de mensajes estandarizados que pueden
consultarse vía API, garantizando consistencia en la comunicación del sistema y facilitando soporte multiidioma
si el proyecto lo requiere.

<u>Justificación</u>: Evita que los mensajes estén dispersos y duplicados en el código de los distintos componentes.
Asegura uniformidad en la experiencia del usuario y simplifica el mantenimiento, ya que cualquier cambio en un texto
se realiza en un solo lugar.


#### Notification Catalog

<u>Motivación</u>: Centralizar las plantillas de notificación que el sistema Lilfac utiliza para comunicarse con los
usuarios a través del Notification Gateway.

<u>Uso</u>: Almacenar y exponer las plantillas estructuradas de correos electrónicos, SMS y notificaciones push,
incluyendo su contenido, formato y variables dinámicas que el Notification Gateway completa antes de enviar cada mensaje.

<u>Justificación</u>: Desacopla el contenido de las notificaciones de la lógica del Backend y del Gateway.
Permite que las plantillas sean gestionadas y actualizadas de forma centralizada sin modificar el código,
garantizando consistencia en todas las comunicaciones enviadas a los usuarios.


#### Notification Gateway

Notification Gateway
<u>Motivación</u>: Proveer un canal centralizado y desacoplado para el envío de notificaciones a los usuarios del sistema
Lilfac.

<u>Uso</u>: Recibir instrucciones del Backend indicando qué notificación enviar y a quién, consultar la plantilla
correspondiente en el Notification Catalog, y ejecutar el envío a través del canal adecuado, ya sea correo electrónico,
SMS o notificación push.

<u>Justificación</u>: Abstrae al Backend de los detalles técnicos de cada canal de notificación. Si en el futuro se
agrega un nuevo canal de comunicación, el cambio se realiza únicamente en el Gateway sin afectar la lógica del Backend,
lo que mejora la mantenibilidad y escalabilidad del sistema.


#### Key Vault

<u>Motivación</u>: Proteger todos los secretos, credenciales y claves criptográficas que el sistema Lilfac necesita
para operar, manteniéndolos fuera del código fuente y de los archivos de configuración.

<u>Uso</u>: Almacenar de forma segura contraseñas de bases de datos, claves de APIs externas, certificados y tokens
de servicio, permitiendo que el Backend los consulte en tiempo de ejecución mediante acceso controlado y auditado.

<u>Justificación</u>: Elimina el riesgo de exponer información sensible en el repositorio de código o en variables de
entorno sin cifrar. Centraliza la gestión de secretos con control de acceso granular, lo que facilita la rotación de
credenciales y el cumplimiento de buenas prácticas de seguridad.


#### APM Application performance monitoring

<u>Motivación</u>: Tener visibilidad continua sobre el comportamiento, el rendimiento y la salud del sistema Lilfac
en ambientes productivos.

<u>Uso</u>: Recopilar métricas de rendimiento, trazas de ejecución, registros de errores y excepciones del Backend en
tiempo real, generando alertas automáticas cuando se detectan degradaciones o fallos en el sistema.

<u>Justificación</u>: Sin observabilidad, los problemas en producción son difíciles de detectar y aún más difíciles de
diagnosticar. El APM permite al equipo identificar cuellos de botella, errores recurrentes y comportamientos anómalos
antes de que impacten negativamente a los usuarios, reduciendo los tiempos de respuesta ante incidentes.


---

## 6. Arquitectura de solución/referencia

Una arquitectura de solución es un diseño estructurado que describe cómo se integran y organizan los
diferentes componentes de un sistema para cumplir con un conjunto específico de requisitos y objetivos, 
es un plano que guía la construcción de un software o sistema, considerando tanto los aspectos técnicos 
como los de negocio.

---

###### **_Diagrama Arquitectura de solución/referencia_**

---
![img.png](arquitecturaSolución.png)
---

### **Documentación Arquetipo de solución/referencia**

---

#### DNS _( Cloudflare DNS )_

Motivación: Se selecciona Cloudflare DNS por su alto rendimiento, disponibilidad global y tiempos de resolución DNS 
extremadamente bajos. Cloudflare opera una de las redes más grandes del mundo, ofreciendo redundancia y protección 
contra ataques DDoS a nivel DNS. Su integración nativa con WAF y CDN del mismo proveedor simplifica la gestión de 
la infraestructura de red.

Uso: Cloudflare DNS se utiliza para resolver los nombres de dominio del sistema Lilfac hacia las IPs correspondientes,
gestionando registros A, CNAME y TXT necesarios para la operación del sistema. También habilita configuraciones de 
failover y balanceo de carga DNS.

Justificación: Al centralizar DNS, WAF y CDN en Cloudflare, se reduce la latencia de resolución y se simplifica la administración. La integración con los demás servicios de Cloudflare garantiza coherencia en las políticas de seguridad y rendimiento del sistema.


#### WAF _( Cloudflare Web Application Firewall )_

Motivación: Se elige Cloudflare WAF por su capacidad de inspeccionar y filtrar el tráfico HTTP/HTTPS malicioso antes de
que llegue a los servidores de aplicación. Ofrece reglas gestionadas actualizadas continuamente contra vulnerabilidades
OWASP Top 10, así como reglas personalizables.

Uso: Cloudflare WAF se posiciona como primera línea de defensa frente al tráfico externo, bloqueando ataques de inyección
SQL, XSS, CSRF y otras amenazas web conocidas. Se configura con reglas específicas para los endpoints de la API y el 
frontend de Lilfac.

Justificación: La elección de Cloudflare WAF permite proteger el sistema sin impacto significativo en el rendimiento,
aprovechando la red global de Cloudflare para filtrar amenazas en el edge antes de que consuman recursos del backend.
Se alinea con los requisitos de seguridad del sistema.


#### CDN _(Cloudflare CDN)_

Motivación: Se selecciona Cloudflare CDN por su red de más de 300 puntos de presencia (PoP) a nivel mundial que permiten
distribuir el contenido estático del frontend cerca del usuario final, reduciendo la latencia y mejorando la experiencia
de usuario.

Uso: Cloudflare CDN almacena en caché los assets estáticos del frontend de Lilfac (JS, CSS, imágenes) y los sirve desde 
el nodo más cercano al usuario. 

Justificación: Al combinar CDN con DNS y WAF en Cloudflare, se obtiene una solución unificada que mejora el rendimiento,
la disponibilidad y la seguridad del sistema de manera consistente, reduciendo la carga sobre la infraestructura de 
backend.



#### Storage Account _(Amazon S3)_

Motivación: Se elige Amazon S3 por su escalabilidad prácticamente ilimitada, alta durabilidad (99.999999999%) y su
capacidad para almacenar grandes volúmenes de objetos no estructurados como documentos, imágenes y archivos generados
por el sistema. Su modelo de pago por uso lo hace eficiente en costos.

Uso: Amazon S3 se utiliza para almacenar y recuperar archivos adjuntos, documentos de usuarios, reportes generados y 
cualquier otro dato binario o no estructurado que el sistema Lilfac necesite persistir de forma segura y accesible.

Justificación: La elección de Amazon S3 garantiza que el sistema pueda escalar el almacenamiento de forma independiente
a la base de datos, con políticas de ciclo de vida, versionado y control de acceso granular mediante IAM policies, 
asegurando la integridad y disponibilidad de los archivos.


#### Front End Lilfac _(Framework React)_

Motivación: Se selecciona React por su enfoque basado en componentes, alto rendimiento mediante Virtual DOM y su amplia
adopción en la industria. Permite construir interfaces dinámicas y escalables con un ecosistema maduro de librerías 
complementarias.

Uso: React se utiliza para desarrollar toda la interfaz de usuario del sistema Lilfac, estructurando la aplicación en
componentes reutilizables que gestionan el estado de la UI, las interacciones del usuario y la comunicación con el API
Gateway.

Justificación: Se elige React porque permite construir interfaces modulares y reutilizables, facilitando el desarrollo
de funcionalidades complejas como dashboards y gestión de datos. Su enfoque reactivo mejora la experiencia del usuario
y el rendimiento del sistema.


#### API Gateway _(Kong Gateway)_

Motivación: Se opta por Kong Gateway por su arquitectura orientada a microservicios que permite una gestión eficiente, 
escalable y centralizada de las APIs. Ofrece funcionalidades integradas de seguridad como autenticación, rate limiting,
logging y control de tráfico mediante plugins.

Uso: Kong Gateway se utiliza para enrutar las solicitudes entrantes desde el frontend y clientes externos hacia los 
microservicios correspondientes del backend de Lilfac, aplicando políticas de seguridad, transformación de requests 
y observabilidad de forma transversal.

Justificación: Al elegir Kong, se facilita la centralización de la gestión de APIs, mejorando tanto la seguridad como
la eficiencia operativa. Su modelo de plugins permite extender funcionalidades sin modificar el código de los servicios,
lo que reduce el acoplamiento y facilita el mantenimiento.


#### Back End Lilfac _(SpringBoot)_
Motivación: Se selecciona Spring Boot por ser un framework robusto y maduro para el desarrollo de aplicaciones Java 
empresariales, que reduce la configuración boilerplate y facilita la creación de microservicios REST con soporte 
integrado para seguridad, persistencia y observabilidad.

Uso: Spring Boot se utiliza para implementar la lógica de negocio del sistema Lilfac, exponiendo APIs REST consumidas
por el frontend a través del API Gateway. Gestiona la conexión con la base de datos PostgreSQL, la integración con 
Keycloak y la publicación de eventos hacia el sistema de mensajería.

Justificación: La elección de Spring Boot permite al equipo desarrollar servicios backend de forma estandarizada, 
aprovechando el ecosistema Spring (Spring Security, Spring Data JPA, Spring Cloud) para cubrir los requisitos de 
seguridad, persistencia y configuración distribuida del sistema.

Versión: Spring Boot 3.3.5 (compatible con Java 21 LTS), Open Source (Apache 2.0 License).

#### IAM _(Kaycloak)_

Motivación: Keycloak fue elegido por su capacidad para gestionar autenticación y autorización de manera centralizada, 
ofreciendo características como inicio de sesión único (SSO), federación de identidades, gestión de roles y soporte 
para estándares como OAuth 2.0 y OpenID Connect.

Uso: Keycloak se utiliza para validar las credenciales de los usuarios del sistema Lilfac, emitir tokens JWT de acceso
y refresco, y gestionar los roles y permisos asociados a cada perfil de usuario. Se integra con Kong Gateway para validar
tokens en cada request.

Justificación: La selección de Keycloak asegura un enfoque seguro, estándar y escalable para la gestión de identidades,
centralizando el control de acceso y desacoplándolo de la lógica de negocio. Reduce el riesgo de implementaciones de 
seguridad incorrectas al delegar este dominio a un componente especializado.


#### CI /CD pipeline _(GitHub Actions)_

Motivación: Se selecciona GitHub Actions como herramienta de integración y entrega continua por su integración nativa 
con el repositorio GitHub del proyecto, eliminando la necesidad de infraestructura adicional para pipelines. Ofrece un
modelo de configuración declarativa (YAML) y un amplio marketplace de actions reutilizables.

Uso: GitHub Actions se utiliza para automatizar el ciclo completo de CI/CD: compilación del código, ejecución de pruebas
unitarias e integración, análisis estático con SonarQube, construcción de imágenes Docker y despliegue de los servicios 
en los ambientes correspondientes.

Justificación: La integración directa de GitHub Actions con el repositorio GitHub centraliza el código y el pipeline en 
una sola plataforma, facilitando la trazabilidad entre commits, pull requests y despliegues. Esto reduce la fricción del
proceso de entrega y mejora la velocidad de desarrollo del equipo.

#### Cache _(Redis)_

Motivación: Se selecciona Redis por su naturaleza in-memory que ofrece tiempos de acceso en microsegundos, siendo ideal
para almacenar datos de acceso frecuente como sesiones de usuario, resultados de consultas costosas y datos de configuración
temporal que no justifican una consulta a la base de datos principal.

Uso: Redis se utiliza como capa de caché del sistema Lilfac para reducir la carga sobre PostgreSQL, almacenar tokens de 
sesión y gestionar rate limiting distribuido en combinación con Kong Gateway. También puede emplearse como broker de 
mensajes ligeros para comunicaciones internas.

Justificación: La incorporación de Redis permite mejorar significativamente el rendimiento y la escalabilidad del backend
al reducir la latencia de las operaciones de lectura frecuentes. Su simplicidad operativa y su amplio soporte en el 
ecosistema Spring Boot facilitan su adopción sin complejidad adicional.

#### Base de datos _(PostrgeSQL)_

Motivación: Se elige PostgreSQL por ser un sistema de gestión de bases de datos relacional de código abierto con soporte
completo para transacciones ACID, tipos de datos avanzados (JSON, arrays, UUID), extensiones y alto rendimiento en cargas
de trabajo complejas.

Uso: PostgreSQL actúa como la base de datos principal del sistema Lilfac, almacenando todos los datos estructurados del 
dominio de negocio: usuarios, transacciones, configuraciones y registros de auditoría. Los microservicios backend acceden
a ella mediante Spring Data JPA.

Justificación: La elección de PostgreSQL garantiza integridad referencial, soporte para consultas complejas y capacidad 
de escalar verticalmente. Su madurez, comunidad activa y compatibilidad con herramientas como Debezium para CDC lo 
convierten en la opción más sólida para el núcleo de persistencia del sistema.

#### CDC _(Debezium)_

Motivación: Se selecciona Debezium como solución de Change Data Capture por su capacidad de capturar cambios en la base
de datos PostgreSQL en tiempo real mediante la lectura del Write-Ahead Log (WAL), sin impacto en el rendimiento de la 
base de datos de origen.

Uso: Debezium se utiliza para capturar los cambios (inserciones, actualizaciones, eliminaciones) en las tablas de 
PostgreSQL y publicarlos como eventos en el sistema de mensajería, permitiendo la sincronización de datos entre 
microservicios y la construcción de flujos de datos reactivos.

Justificación: La adopción de Debezium permite implementar una arquitectura orientada a eventos de forma confiable, 
garantizando que ningún cambio en la base de datos sea perdido. Esto facilita la integración entre servicios sin 
acoplamiento directo y soporta patrones como Outbox y Event Sourcing.


#### Parameter Catalog _(Spring Cloud Config)_

Motivación: Se selecciona Spring Cloud Config Server para centralizar la gestión de configuraciones de todos los 
microservicios del sistema, permitiendo externalizar propiedades de configuración del código fuente y gestionarlas
de forma unificada por ambiente (desarrollo, staging, producción).

Uso: 
Spring Cloud Config se utiliza para servir configuraciones a los microservicios del backend de Lilfac en tiempo
de arranque y, opcionalmente, en caliente mediante refresh. Las configuraciones se almacenan en el repositorio GitHub
del proyecto, versionadas junto al código.

Justificación: La centralización de parámetros de configuración en Spring Cloud Config elimina la dispersión de 
configuraciones entre servicios, facilita los cambios de entorno sin redespliegues y mejora la trazabilidad de 
cambios de configuración al estar versionados en Git.

#### Message Catalog _(i18next)_

Motivación: Se elige i18next como framework de internacionalización por ser la solución más completa y adoptada del 
ecosistema JavaScript/React. Ofrece soporte para pluralización, interpolación, namespaces, carga lazy de traducciones
y detección automática del idioma del usuario.

Uso: i18next se utiliza en el frontend de Lilfac para gestionar todos los textos de la interfaz de usuario en múltiples
idiomas, cargando los catálogos de mensajes de forma dinámica y permitiendo cambiar el idioma sin recargar la aplicación.

Justificación: La adopción de i18next garantiza una experiencia de usuario localizada desde el diseño del sistema, 
facilitando la expansión del producto a nuevos mercados sin refactorizaciones costosas. Su integración con React mediante
react-i18next es directa y bien documentada.

#### Notification Catalog _(Twilio Notify)_

Motivación: Se selecciona Twilio Notify por su capacidad de gestionar de forma centralizada el envío de notificaciones
a través de múltiples canales (SMS, push, email) desde una única API, simplificando la lógica de notificaciones del 
sistema y abstrayendo los detalles de cada canal.

Uso: Twilio Notify se utiliza como catálogo de plantillas y orquestador de notificaciones del sistema Lilfac, definiendo
los tipos de notificación disponibles y gestionando el enrutamiento hacia el canal apropiado según las preferencias del 
usuario y el tipo de evento.

Justificación: Centralizar las notificaciones en Twilio Notify permite al sistema escalar el envío de comunicaciones sin
acoplarse a proveedores específicos de cada canal, manteniendo consistencia en los mensajes y facilitando la gestión de 
preferencias de los usuarios.

#### Notification Gateway _(Twilio Messaging API)_

Motivación: Se elige Twilio Messaging API como gateway de notificaciones por su confiabilidad global en el envío de SMS,
alta tasa de entrega, cobertura en múltiples países y su SDK robusto para integración con aplicaciones Java/Spring Boot.

Uso: Twilio Messaging API se utiliza para ejecutar el envío efectivo de mensajes SMS y WhatsApp a los usuarios del sistema
Lilfac, gestionando los acuses de entrega, reintentos y registro de cada mensaje enviado desde la plataforma.

Justificación: La elección de Twilio como gateway garantiza la entrega confiable de notificaciones críticas a los usuarios,
respaldada por SLAs empresariales y soporte global. Su integración con Twilio Notify como catálogo permite una arquitectura
de notificaciones cohesiva y mantenible.

#### Key Vault _(HashiCorp Vault)_

Motivación: Se selecciona HashiCorp Vault como solución de gestión de secretos por su capacidad de almacenar, rotar y 
controlar el acceso a credenciales, tokens, certificados y claves de cifrado de forma centralizada y auditable, eliminando
el uso de secretos hardcodeados en el código o en archivos de configuración.

Uso: HashiCorp Vault se utiliza para gestionar todos los secretos del sistema Lilfac: credenciales de base de datos, 
API keys de terceros (Twilio, AWS), certificados TLS y tokens de servicio. Los microservicios obtienen los secretos en 
tiempo de ejecución mediante el agente de Vault o la integración con Spring Cloud Vault.

Justificación: La adopción de HashiCorp Vault elimina la exposición de credenciales en repositorios y archivos de 
configuración, estableciendo un modelo de acceso basado en políticas y con rotación automática de secretos. 
Esto reduce significativamente la superficie de ataque y facilita el cumplimiento de requisitos de seguridad.

#### APM Application performance monitoring _(Grafana Cloud)_
Motivación: Se selecciona Grafana Cloud como plataforma de observabilidad por su capacidad de unificar métricas, logs 
y trazas distribuidas en una sola interfaz, integrando Prometheus para métricas, Loki para logs y Tempo para trazas, 
con dashboards personalizables y alertas configurables.

Uso: Grafana Cloud se utiliza para monitorear el rendimiento de todos los componentes del sistema Lilfac en tiempo real:
latencia de APIs, uso de recursos de los microservicios, errores en los pipelines y comportamiento de la base de datos. 
Centraliza la observabilidad del sistema en dashboards unificados accesibles al equipo.

Justificación: La elección de Grafana Cloud permite al equipo detectar degradaciones de rendimiento y errores proactivamente
antes de que impacten a los usuarios, con una solución gestionada que elimina la carga operativa de mantener infraestructura
de monitoreo propia. Su integración con el stack tecnológico elegido (Spring Boot, PostgreSQL, Redis) es nativa y bien 
documentada.

---

## 7. Línea base arquitectónica

Es un conjunto de documentos y especificaciones que describen como debe ser la estructura y el diseño de un sistema 
o software. Esta línea base sirve como referencia para asegurarse de que todos los cambios y desarrollos futuros se 
realicen de manera coherente y alineada con los objetivos iniciales del proyecto.
### 7.1 Línea base arquitectónica de componentes

A continuación, se presentan cada uno de los componentes empleados en la construcción de LILFAC, detallando la motivación
y descripción de cada uno. Este análisis permite comprender las decisiones arquitectónicas y tecnologías que sustentan el
desarrollo del sistema, asegurando que cada componente cumpla con los objetivos establecidos y contribuya al funcionamiento
eficiente, seguro y escalable de la plataforma de gestión de inventario y facturación para empresas de alquiler de productos
para eventos.

#### 7.1.1 Componente 1

Nombre: Lilfac Backend

Tipo de componente: Desarrollo propio

Descripción: Componente que contiene toda la lógica de negocio necesaria para la aplicación LILFAC, 
incluyendo la gestión de inventario, facturación, pedidos, clientes, productos y el dashboard de análisis 
con inteligencia artificial.

Justificación: Este componente es vital, ya que incluye toda la funcionalidad para el registro de clientes, empleados,
información de la empresa, registro de pedidos, productos, inventario, edición y eliminación de registros y generación 
de reportes.

Categoría: Core

#### 7.1.2 Componente 2

Nombre: Base de datos (PostgreSQL)

Tipo de componente: Componente adoptado

Descripción: Componente que permite gestionar toda la información estructurada que requiere LILFAC, incluyendo clientes,
productos, pedidos, facturas, inventario, historial de costos y registros de trazabilidad.

Justificación: Gestiona de forma centralizada los registros del negocio de alquiler de eventos, asegurando la consistencia
transaccional en operaciones críticas como la creación de facturas con costos adicionales, el control de disponibilidad de
inventario y el historial de modificaciones para auditoría. Cumple con las restricciones de diseño de alta disponibilidad,
seguridad de datos y soporte para consultas complejas requeridas por el dashboard de análisis. Su naturaleza relacional 
garantiza la integridad referencial entre pedidos, productos y clientes, y su compatibilidad con Debezium habilita el CDC
necesario para la sincronización de datos en tiempo real.

Categoría: Genérico

### 7.1.3 Componente 3
Nombre: IAM Identity and access management (Keycloak)

Tipo de componente: Componente adoptado

Descripción: Componente que gestiona la autenticación y autorización de los usuarios de LILFAC, administrando los cuatro
roles del sistema: administrador, cajero, bodega y logística.

Justificación: Asegura que cada usuario acceda únicamente a las funcionalidades correspondientes a su rol, protegiendo 
operaciones sensibles como la modificación de facturas, el ajuste de precios y la consulta de reportes financieros. 
Proporciona un inicio de sesión seguro basado en estándares OAuth 2.0 y OpenID Connect, desacoplando la lógica de seguridad
del código de negocio en alineación con los principios de Clean Architecture definidos como restricción técnica del proyecto.

Categoría: Soporte

### 7.1.4 Componente 4
Nombre: API Gateway (Kong Gateway)

Tipo de componente: Componente adoptado

Descripción: Componente que centraliza y administra todas las peticiones hacia los servicios del backend de LILFAC, 
aplicando políticas de seguridad, enrutamiento y control de tráfico de forma transversal.

Justificación: Facilita la comunicación entre el frontend y los servicios del backend, garantizando conexiones seguras 
para todas las operaciones del sistema, desde la gestión de clientes y productos hasta la generación de facturas y la 
consulta del dashboard. Su modelo de plugins permite aplicar autenticación, rate limiting y logging sin modificar el 
código de los servicios, respetando el principio de bajo acoplamiento y alta cohesión exigido por las restricciones técnicas
del proyecto.

Categoría: Soporte

### 7.1.5 Componente 5
Nombre: APM / Observabilidad (Grafana Cloud)

Tipo de componente: Componente adoptado

Descripción: Componente que centraliza el monitoreo del rendimiento, los logs y las trazas distribuidas de todos los 
servicios de LILFAC, proporcionando visibilidad en tiempo real del estado del sistema.

Justificación: Es esencial para detectar de forma proactiva fallos en procesos críticos como la entrega y recepción de 
pedidos, la generación de facturas y la sincronización de inventario. Permite al equipo identificar cuellos de botella 
en el dashboard de IA y garantizar tiempos de respuesta adecuados. Cumple con los principios del manifiesto reactivo y 
del Well-Architected Framework definidos como restricciones técnicas, habilitando una respuesta rápida ante incidentes 
y una operación confiable del sistema.

Categoría: Soporte

### 7.1.6 Componente 6
Nombre: WAF (Cloudflare Web Application Firewall)

Tipo de componente: Componente adoptado

Descripción: Componente de seguridad que protege a LILFAC de ataques externos, inspeccionando y filtrando el tráfico 
HTTP/HTTPS malicioso antes de que alcance los servidores de aplicación.

Justificación: Protege los datos de clientes, facturas e inventario frente a amenazas como inyecciones SQL, ataques 
XSS y DDoS, garantizando un entorno seguro para las operaciones del negocio. Dado que el sistema maneja información 
financiera sensible y trazabilidad de auditoría, la protección en el perímetro es un requisito no negociable alineado
con los pilares de seguridad del Well-Architected Framework establecidos en las restricciones técnicas del proyecto.

Categoría: Genérico

### 7.1.7 Componente 7
Nombre: CDC — Change Data Capture (Debezium)

Tipo de componente: Componente adoptado

Descripción: Componente que captura en tiempo real los cambios realizados en la base de datos PostgreSQL de LILFAC, 
publicándolos como eventos para su procesamiento por otros servicios del sistema.

Justificación: Permite mantener sincronizados los datos de inventario, pedidos y facturación entre los distintos módulos
del sistema sin acoplamiento directo entre servicios, respetando el principio de aislación de módulos de Clean Architecture.
Es fundamental para alimentar el dashboard de análisis con datos actualizados en tiempo real y para construir el historial 
de trazabilidad de modificaciones requerido para auditorías, sin impactar el rendimiento de la base de datos principal.

Categoría: Soporte

### 7.1.8 Componente 8
Nombre: Baúl de llaves (HashiCorp Vault)

Tipo de componente: Componente adoptado

Descripción: Componente que gestiona el almacenamiento seguro de claves, secretos y credenciales del sistema LILFAC, 
incluyendo credenciales de base de datos, API keys de servicios externos (Twilio, AWS) y certificados TLS.

Justificación: Protege la información sensible del sistema eliminando el uso de credenciales hardcodeadas en el código 
o en archivos de configuración, en cumplimiento directo con los principios de los 12 factores de aplicación y las 
prácticas de Clean Code definidas como restricciones técnicas. Garantiza que los secretos estén encriptados, versionados
y accesibles únicamente por los servicios autorizados, reduciendo la superficie de ataque del sistema.

Categoría: Genérico

### 7.1.9 Componente 9
Nombre: Catálogo de parámetros (Spring Cloud Config)

Tipo de componente: Componente adoptado

Descripción: Componente que centraliza y gestiona los parámetros de configuración de todos los servicios de LILFAC por 
ambiente (desarrollo, staging, producción), externalizando las configuraciones del código fuente.

Justificación: Facilita la administración y ajuste del comportamiento del sistema sin necesidad de cambios directos en 
el código ni redespliegues, permitiendo configurar aspectos como umbrales de alertas de inventario, reglas de costos 
adicionales por multas y parámetros del motor de recomendaciones de IA. Se alinea con el factor de configuración de los
12 factores de aplicación y con la práctica de separar la configuración del entorno, definida como restricción técnica 
del proyecto.

Categoría: Soporte

### 7.1.10 Componente 10
Nombre: Catálogo de mensajes (i18next)

Tipo de componente: Componente adoptado

Descripción: Componente que centraliza y gestiona todos los textos, etiquetas y mensajes de la interfaz de usuario de 
LILFAC, habilitando la internacionalización y consistencia en las comunicaciones del sistema.

Justificación: Garantiza coherencia en los mensajes mostrados a los distintos roles del sistema (administrador, cajero,
bodega, logística) y facilita futuras adaptaciones del sistema a otros mercados o idiomas sin modificaciones en el código
de negocio. Su gestión centralizada reduce el retrabajo y mejora la mantenibilidad del frontend, en línea con los principios
de Clean Code y la reutilización de componentes definidos en las restricciones técnicas del proyecto.

Categoría: Soporte

### 7.1.11 Componente 11
Nombre: Sistema de autenticación (Keycloak)

Tipo de componente: Componente adoptado

Descripción: Componente que maneja los mecanismos de autenticación y control de sesiones de LILFAC, gestionando el ciclo
de vida de los tokens de acceso para los cuatro roles del sistema.

Justificación: Garantiza un proceso seguro de inicio de sesión para los usuarios del sistema, protegiendo el acceso a 
funcionalidades críticas como la modificación de facturas, el ajuste de inventario y la consulta del dashboard de análisis.
Al delegar la autenticación a un componente especializado y desacoplado, se reduce el riesgo de implementaciones de seguridad
incorrectas y se facilita la evolución del sistema sin afectar la lógica de negocio, en cumplimiento de los principios 
de Clean Architecture.

Categoría: Soporte

### 7.1.12 Componente 12
Nombre: CDN (Cloudflare CDN)

Tipo de componente: Componente adoptado

Descripción: Componente que mejora la distribución del contenido estático del frontend de LILFAC, acercando los assets a
los usuarios finales mediante la red global de puntos de presencia de Cloudflare.

Justificación: Reduce la latencia en la carga del sistema para los usuarios operativos (administrador, cajero, bodega, 
logística) independientemente de su ubicación geográfica, mejorando la experiencia de uso en operaciones de alta frecuencia
como la consulta de inventario, la gestión de pedidos y la revisión del dashboard. Su integración nativa con el DNS y WAF de
Cloudflare simplifica la gestión de la infraestructura de red del sistema.

Categoría: Genérico

### 7.1.13 Componente 13
Nombre:  Storage Account (Amazon S3)

Tipo de componente: Componente adoptado

Descripción: Componente que almacena archivos y documentos no estructurados generados por LILFAC, incluyendo facturas
en PDF, reportes del dashboard, imágenes de productos y respaldos de información del negocio.

Justificación: Almacena y gestiona los documentos generados por el sistema de forma escalable y duradera, permitiendo 
que administradores y cajeros accedan y descarguen facturas y reportes en cualquier momento. Su uso como servicio en 
la nube para respaldos de información cubre directamente uno de los requisitos de integración con servicios externos 
identificados para el proyecto, garantizando la disponibilidad de los datos ante fallos del sistema principal.

Categoría: Genérico

### 7.1.14 Componente 14
Nombre: CI-CD Pipeline (GitHub Actions)

Tipo de componente: Componente adoptado

Descripción: Componente que automatiza el ciclo completo de integración, entrega y despliegue continuo de LILFAC, 
gestionando la compilación, pruebas, análisis de calidad y despliegue de los servicios del sistema en cada cambio 
al repositorio.

Justificación: Permite desacoplar y automatizar el proceso de entrega de software, garantizando que cada cambio en
el código pase por validaciones de calidad (pruebas unitarias, análisis estático con SonarQube) antes de llegar a 
producción. Cumple directamente con la restricción técnica de adoptar prácticas DevOps de CI/CD, habilitando despliegues
frecuentes y seguros que reducen el riesgo operativo y acortan el tiempo de entrega de nuevas funcionalidades al cliente.

Categoría: Soporte

### 7.1.15 Componente 15
Nombre: Observabilidad y APM (Grafana Cloud)

Tipo de componente: Componente adoptado

Descripción: Capacidad de medir el estado interno del sistema LILFAC basándose en sus salidas, integrando métricas de 
rendimiento, logs de operación y trazas distribuidas de todos los servicios en una plataforma unificada y accesible al
equipo.

Justificación: Proporciona visibilidad en tiempo real sobre el comportamiento del sistema en procesos críticos como la
sincronización de inventario, el procesamiento de pedidos y la operación del dashboard de IA. Ayuda a detectar fallos y
degradaciones de rendimiento antes de que impacten a los usuarios operativos, en alineación con los principios del 
manifiesto reactivo y los pilares de confiabilidad del Well-Architected Framework definidos en las restricciones técnicas
del proyecto.

Categoría: Soporte

### 7.1.16 Componente 16
Nombre: Componente de Notificaciones (Twilio Notify + Twilio Messaging API)

Tipo de componente: Componente adoptado

Descripción: Componente responsable de enviar notificaciones a los usuarios y clientes de LILFAC a través de múltiples 
canales: correo electrónico, SMS y mensajes WhatsApp, integrado con los eventos del sistema para disparar alertas y 
comunicaciones automáticas.

Justificación: Mejora la experiencia operativa del negocio al mantener informados tanto al equipo interno como a los 
clientes sobre eventos relevantes: confirmaciones de pedidos, alertas de inventario bajo, notificaciones de entrega y
recepción de productos, y alertas de costos adicionales por multas o daños. Cubre directamente los requisitos de integración
con servicios externos de SMS y WhatsApp identificados para el proyecto, facilitando la comunicación oportuna que es crítica
en un negocio de alquiler de productos para eventos con fechas comprometidas.

Categoría: Genérico

### 7.2 Estilos y patrones arquitectónicos adoptados

Los estilos y patrones críticos son enfoques y soluciones estructuradas que se utilizan en el diseño y desarrollo de 
software para abordar problemas comunes y mejorar la calidad del sistema. Los estilos críticos se refieren a los enfoques
arquitectónicos que establecen la estructura general del software. Estos estilos pueden incluir arquitecturas como en capas,
microservicios u orientadas a eventos, que ayudan a organizar el código y a definir cómo se comunican los diferentes 
componentes del sistema. Al elegir un estilo adecuado, se asegura que el proyecto sea escalable, mantenible y eficiente.
Por otro lado, los patrones críticos son soluciones probadas y reutilizables a problemas específicos que se presentan 
durante el desarrollo, estos patrones ayudan a los desarrolladores a escribir código más limpio y comprensible, evitando
la reinvención de soluciones ya existentes.

#### 7.2.1 Estilo arquitectónico 1

Estilo arquitectónico que se basa en la creación de aplicaciones como un conjunto de pequeños servicios independientes,
cada uno de los cuales está diseñado para cumplir una funcionalidad específica.

##### 7.2.1.1 Nombre

Microservicios

##### 7.2.1.2 Problema

El enfoque de microservicios resuelve el problema de la complejidad en aplicaciones monolíticas, donde todo el código y 
la funcionalidad están integrados en una sola base de código. Este tipo de arquitectura es difícil de escalar, mantener 
y desplegar, especialmente a medida que el proyecto crece. Los microservicios son ideales en contextos donde se requiere
una alta disponibilidad, escalabilidad y flexibilidad, permitiendo a diferentes equipos trabajar de manera independiente
en distintas partes de la aplicación.

##### 7.2.1.3 Solución/Motivación

La solución propuesta por el enfoque de microservicios es descomponer la aplicación en pequeños servicios independientes,
cada uno enfocado en una funcionalidad específica. Cada microservicio se puede desarrollar, desplegar y escalar de manera
independiente, lo que permite una mayor agilidad en el desarrollo y la implementación. Además, los microservicios pueden 
ser escritos en diferentes lenguajes de programación y usar diferentes bases de datos, lo que fomenta la diversidad 
tecnológica y la innovación.

#### 7.2.2 Estilo arquitectónico 2

Estilo que promueve la separación de la lógica de negocio de los detalles de implementación. Esta arquitectura organiza 
el software en capas que se comunican a través de interfaces, donde el núcleo del sistema (la lógica de negocio) es 
independiente de los componentes externos como bases de datos, interfaces de usuario y otros servicios.

##### 7.2.2.1 Nombre

Arquitectura Hexagonal (Clean Architecture)

##### 7.2.2.2 Problema

La arquitectura hexagonal aborda el problema de acoplar la lógica de negocio a detalles de implementación específicos, 
como bases de datos, interfaces de usuario y servicios externos. En contextos donde la aplicación necesita adaptarse a 
cambios tecnológicos frecuentes o donde se requiere integrar diferentes interfaces (como móviles y web), este estilo 
arquitectónico proporciona una solución clara.

##### 7.2.2.3 Solución/Motivación

La solución de la arquitectura hexagonal es organizar el sistema de manera que la lógica de negocio esté en el centro y 
rodeada de interfaces que permiten la interacción con el mundo exterior. Esto significa que los detalles de implementación
(como frameworks y bases de datos) están aislados del núcleo del negocio, facilitando la prueba y la modificación del sistema
sin afectar su funcionalidad principal. Esta estructura modular y flexible permite adaptarse rápidamente a nuevos requerimientos
y tecnologías.


#### 7.2.3	Patrón arquitectónico 1

Patrón que permite que un objeto (o clase) reciba sus dependencias de fuentes externas en lugar de crearlas internamente.
Esto se logra mediante la inyección de objetos necesarios en el constructor, en métodos o a través de propiedades

##### 7.2.3.1	Nombre

Inyección de Dependencias (DI)

##### 7.2.3.2 Problema

El patrón de Inyección de Dependencias resuelve el problema del acoplamiento fuerte entre componentes en una aplicación. 
En contextos donde las clases dependen de otras clases para funcionar, la creación de instancias dentro de esas clases 
puede dificultar el mantenimiento, la prueba y la evolución del sistema. Este patrón es particularmente útil en arquitecturas
complejas, donde el cambio de una dependencia puede requerir modificaciones significativas en múltiples lugares del código.

##### 7.2.3.3	Solución/Motivación

La solución propuesta por la Inyección de Dependencias es permitir que un objeto reciba sus dependencias desde el exterior,
en lugar de crearlas internamente. Esto se logra a través de la inyección en el constructor, en métodos o a través de 
propiedades. Al hacerlo, se promueve un bajo acoplamiento y se facilita la reutilización de componentes, ya que las clases
se pueden construir de manera independiente de sus dependencias. Este enfoque ayuda a mantener un diseño limpio y modular,
alineándose con los principios de arquitecturas como la Clean Architecture, lo que permite una evolución más sencilla y 
flexible del software a lo largo del tiempo.

#### 7.2.4	Patrón arquitectónico 2

Diseño creacional que asegura que una clase tenga una única instancia a lo largo de la aplicación y proporciona un punto
de acceso global a esa instancia. Este patrón es útil en situaciones donde es necesario tener un control centralizado 
sobre un recurso compartido, como una configuración global, un registro de eventos o una conexión a una base de datos.

##### 7.2.4.1 Nombre
Singleton

##### 7.2.4.2 Problema
El patrón Singleton resuelve el problema de la creación de múltiples instancias de una clase que debería tener una única
instancia a lo largo de la aplicación. Este contexto de aplicación es crítico en situaciones donde se necesita un control
centralizado sobre recursos compartidos, como una configuración global, un registro de eventos, o una conexión a base de
datos. Sin el uso del patrón Singleton, se corre el riesgo de tener múltiples instancias que pueden provocar inconsistencias
y comportamientos inesperados en la aplicación.

##### 7.2.4.3 Solución/Motivación
La solución propuesta por el patrón Singleton es restringir la creación de instancias de la clase a una sola instancia y 
proporcionar un punto de acceso global a esa instancia. Esto se logra mediante un constructor privado que impide la creación 
de instancias fuera de la clase y un método estático que devuelve la instancia única. Esta estrategia garantiza que todos 
los componentes de la aplicación que requieren acceso a ese recurso compartido utilicen la misma instancia, lo que mejora 
la gestión de recursos y la coherencia en el estado de la aplicación. Al aplicar este patrón, se facilita la implementación
de funcionalidades que requieren un control centralizado y se minimizan los riesgos de error asociados con el manejo de 
múltiples instancias.

---

## 8. Justificación alternativa de solución

La justificación de una alternativa de solución es la explicación que respalda la elección de un enfoque específico para 
resolver un problema. Consiste en evaluar diversas opciones y determinar cuál es la más adecuada según los requisitos del
proyecto, las restricciones de diseño y los objetivos estratégicos. Esta justificación asegura que la solución no solo aborde
el problema de manera efectiva, sino que también sea sostenible a largo plazo y se alinee con los principios de diseño deseados.

### 8.1 Justificación

La alternativa de solución propuesta para LILFAC, basada en una arquitectura hexagonal (Clean Architecture) integrada 
con microservicios y un ecosistema de componentes externos como Cloudflare (DNS, WAF, CDN), Kong Gateway, Keycloak, 
Amazon S3, PostgreSQL, Redis, Debezium, HashiCorp Vault y Grafana Cloud, es la más adecuada para resolver las necesidades
operativas, de seguridad, escalabilidad y trazabilidad del sistema de gestión de inventario y facturación para empresas 
de alquiler de productos para eventos.

Esta arquitectura proporciona una separación clara de responsabilidades mediante la aplicación de los estilos arquitectónicos 
de microservicios y arquitectura hexagonal, donde cada capa se encuentra desacoplada a través de interfaces bien definidas. 
Esto garantiza que la lógica de negocio del sistema, que incluye la gestión de pedidos, inventario, facturación con costos 
adicionales, trazabilidad de auditoría y el dashboard de recomendaciones con inteligencia artificial, permanezca independiente
de los detalles de implementación como bases de datos, frameworks o servicios externos. 
Esta separación permite que a medida que el negocio crezca y se incorporen nuevas funcionalidades, el sistema pueda evolucionar
sin comprometer la estabilidad ni el rendimiento de los módulos existentes.

La decisión de adoptar patrones como la Inyección de Dependencias y el Singleton, dentro de un backend desarrollado con 
Spring Boot, refuerza los principios de bajo acoplamiento y alta cohesión definidos como restricciones técnicas del proyecto.
La Inyección de Dependencias facilita las pruebas automatizadas de los módulos de negocio (clientes, pedidos, facturación, 
inventario) de forma aislada, mientras que el Singleton garantiza un control centralizado de recursos compartidos críticos 
como conexiones a la base de datos y configuraciones del sistema.

Uno de los aspectos centrales de esta solución es la seguridad en capas. La arquitectura posiciona a Cloudflare como 
primera línea de defensa con DNS, WAF y CDN integrados, filtrando amenazas en el borde de la red antes de que alcancen
la infraestructura de aplicación. Kong Gateway actúa como punto único de entrada para todas las solicitudes hacia el 
backend, aplicando autenticación, rate limiting y logging de forma transversal. Keycloak centraliza la gestión de identidades
y el control de acceso por roles (administrador, cajero, bodega y logística), asegurando que cada actor del sistema acceda 
únicamente a las funcionalidades que le corresponden. HashiCorp Vault completa esta estrategia de seguridad gestionando los
secretos y credenciales del sistema sin exponerlos en el código ni en archivos de configuración, cumpliendo con los principios
de los 12 factores de aplicación definidos en las restricciones técnicas.

El uso de Debezium como componente de Change Data Capture representa una ventaja significativa para LILFAC, ya que permite
capturar en tiempo real todos los cambios en la base de datos PostgreSQL y publicarlos como eventos, sin impactar el 
rendimiento de la base de datos principal. Esto habilita la trazabilidad completa de modificaciones sobre pedidos, 
facturas e inventario requerida para auditorías, y alimenta el dashboard de análisis con datos actualizados

La incorporación de Redis como capa de caché complementa el rendimiento del sistema al reducir la carga sobre PostgreSQL
en consultas frecuentes de inventario y productos, mientras que Amazon S3 provee el almacenamiento escalable y duradero 
de documentos no estructurados como facturas en PDF, reportes del dashboard e imágenes de productos, cubriendo directamente
el requisito de respaldo en la nube identificado para el proyecto. El pipeline de CI/CD implementado con GitHub Actions, 
integrado con el análisis estático de SonarQube, garantiza que cada cambio en el sistema pase por validaciones de calidad
antes de llegar a producción, alineándose con las restricciones técnicas de DevOps y entrega continua.

Y la plataforma de notificaciones construida sobre Twilio Notify y Twilio Messaging API cubre los requisitos de 
comunicación multicanal (SMS y correo electronico) identificados para el proyecto, permitiendo informar a clientes 
y operarios sobre confirmaciones de pedidos, alertas de inventario, notificaciones de entrega y alertas por multas o 
daños al inventario, lo cual es crítico en un negocio donde los eventos tienen fechas inamovibles y la comunicación 
oportuna es un diferenciador del servicio.

Esta solución no solo cumple con las restricciones técnicas y de negocio identificadas, sino que también alinea las 
capacidades tecnológicas con la visión de LILFAC de ser una herramienta integral, segura, auditable y eficiente para
la operación de empresas de alquiler de productos para eventos, con capacidad de escalar y adaptarse a medida que el 
negocio crece.


### 8.2 Ventajas

* **Escalabilidad Modular mediante Microservicios:** 

    La combinación de arquitectura hexagonal y microservicios permite que cada módulo del sistema (gestión de clientes, 
pedidos, facturación, inventario, dashboard de IA) se escale y evolucione de forma independiente. 
Esto es fundamental para LILFAC, ya que en temporadas de alta demanda de eventos el sistema puede incrementar la 
capacidad de los módulos más exigidos sin afectar los demás, soportando el crecimiento del negocio de manera progresiva.


* **Seguridad en Capas con Cobertura Completa:** 

    La arquitectura implementa múltiples niveles de protección: Cloudflare filtra amenazas en el perímetro de red, Kong 
Gateway controla el acceso a los servicios, Keycloak gestiona la identidad y los roles, y HashiCorp Vault protege las 
credenciales. Esta estrategia de defensa en profundidad minimiza el riesgo de exposición de datos sensibles de clientes,
facturas e inventario, cumpliendo con los más altos estándares de seguridad definidos en el Well-Architected Framework.


* **Trazabilidad y Auditoría Garantizada mediante Debezium:** 

    La adopción de Change Data Capture con Debezium asegura que cada modificación sobre pedidos, facturas o inventario quede
registrada como un evento inmutable y reproducible. Esto cubre directamente el requisito crítico de trazabilidad para 
auditorías del proyecto, permitiendo rastrear quién modificó qué y cuándo, sin necesidad de implementar lógica adicional
en cada servicio.


* **Rendimiento Optimizado para Operaciones de Alta Frecuencia:** 

    La integración de Cloudflare CDN para el contenido estático del frontend y Redis como caché de consultas frecuentes garantiza
tiempos de respuesta rápidos para las operaciones del día a día de los usuarios operativos (consulta de inventario, búsqueda 
de productos y clientes). Esto asegura una experiencia de uso fluida incluso en momentos de alta concurrencia durante temporadas
de eventos.

* **Observabilidad Proactiva del Sistema:** 

    Grafana Cloud centraliza métricas, logs y trazas distribuidas de todos los componentes, proporcionando visibilidad
    completa del estado del sistema en tiempo real. Esto permite al equipo detectar y resolver fallos en procesos críticos 
    como la sincronización de inventario o la generación de facturas antes de que impacten a los usuarios, alineándose con 
    los principios del manifiesto reactivo exigidos por las restricciones técnicas.


* **Calidad de Código Continua con CI/CD y SonarQube:** 
    
    El pipeline de GitHub Actions integrado con SonarQube garantiza que cada cambio pase por validaciones automatizadas 
    de calidad antes de llegar a producción. Esto reduce significativamente la cantidad de defectos en producción, 
    cumpliendo con las prácticas de Clean Code y DevOps definidas como restricciones técnicas del proyecto, y protegiendo 
    la estabilidad del sistema en cada entrega.


* **Independencia Tecnológica y Configuración Externalizada:** 
    Spring Cloud Config centraliza la gestión de configuraciones por ambiente, y el desacoplamiento entre módulos mediante 
arquitectura hexagonal permite actualizar o reemplazar componentes individuales (base de datos, proveedor de 
notificaciones, mecanismo de caché) sin afectar el núcleo de negocio. Esto le da al proyecto flexibilidad para 
adaptarse a cambios tecnológicos o de presupuesto sin incurrir en refactorizaciones costosas.


* **Comunicación Multicanal Integrada:** 
    
    La plataforma de notificaciones sobre Twilio cubre los requisitos de comunicación por SMS y correo electronico, 
    garantizando que clientes y operarios estén informados en tiempo real sobre el estado de sus pedidos, entregas y 
    posibles multas, lo cual es un diferenciador operativo crítico en un negocio donde los eventos tienen fechas inamovibles.

### 8.3 Desventajas

* **Complejidad Inicial en el Desarrollo:**

    La integración de múltiples componentes especializados (Debezium, Keycloak, Kong, HashiCorp Vault, Grafana Cloud, 
    entre otros) incrementa significativamente la complejidad del desarrollo inicial del sistema. Esto implica una mayor
    inversión de tiempo en la configuración, integración y prueba de cada componente antes de poder entregar valor 
    funcional al negocio, lo que puede generar tensión con el presupuesto limitado de $500.000 y los hitos de pago por 
    avances definidos como restricción del proyecto.


* **Costos de Mantenimiento de la Infraestructura:**

    La operación de una arquitectura con tantos servicios externos gestionados
    (Cloudflare, Twilio, Amazon S3, Grafana Cloud) implica costos recurrentes que deben ser monitoreados y 
    controlados de forma estricta. A medida que el volumen de operaciones del negocio crece, los costos por uso de estos
    servicios pueden escalar, lo que requiere una gestión financiera cuidadosa alineada con las restricciones de
    presupuesto del proyecto.


* **Curva de Aprendizaje Elevada para el Equipo: **

    La adopción simultánea de arquitectura hexagonal, microservicios, patrones como Inyección de Dependencias y Singleton
    , y herramientas como Debezium o HashiCorp Vault requiere que el equipo de desarrollo esté capacitado en múltiples 
    tecnologías y conceptos arquitectónicos. Esto puede ralentizar las primeras etapas del desarrollo y requerir tiempo     
    adicional de formación, lo que debe contemplarse en la planificación de sprints y en la gestión de expectativas con 
    el cliente.


* **Dependencia de la Disponibilidad de Servicios Externos:**

    El sistema depende críticamente de la disponibilidad de servicios como Cloudflare, Twilio, Amazon S3 y Grafana Cloud.
    Si alguno de estos proveedores experimenta una interrupción, funcionalidades clave del sistema como el envío de 
    notificaciones, el almacenamiento de facturas o la protección perimetral podrían verse afectadas. Aunque estos 
    proveedores ofrecen SLAs de alta disponibilidad, esta dependencia debe ser gestionada con planes de contingencia claros.


* **Latencia Potencial en la Comunicación entre Microservicios:**

    En una arquitectura de microservicios, la comunicación entre servicios a través de la red introduce latencias 
    adicionales respecto a un sistema monolítico. En operaciones que involucran múltiples servicios de forma encadenada,
    como la generación de una factura que actualiza el inventario y dispara notificaciones simultáneamente, esta latencia
    acumulada podría impactar la experiencia del usuario si no se gestiona adecuadamente mediante caché, asincronía y 
    optimización de consultas.


* **Complejidad en la Observabilidad y el Monitoreo:**

    Mantener Grafana Cloud actualizado y correctamente configurado para monitorear la interacción entre todos los 
    componentes del sistema es un desafío operativo continuo. La correcta instrumentación de métricas, logs y trazas
    en cada servicio requiere disciplina del equipo de desarrollo y esfuerzo de mantenimiento sostenido, especialmente
    a medida que se incorporan nuevos módulos o se realizan cambios en la arquitectura.


* **Riesgo de Sobrecarga con Baja Disponibilidad del Product Owner:**

    Dado que el Product Owner tiene disponibilidad limitada, la validación de decisiones arquitectónicas y funcionales
    críticas puede retrasarse. En una arquitectura de esta complejidad, donde las decisiones de diseño tienen impacto 
    transversal en múltiples componentes, la falta de retroalimentación oportuna del negocio puede generar retrabajos 
    costosos o desalineamientos entre lo construido y lo esperado, amplificando el riesgo ya identificado en las 
    restricciones de negocio del proyecto.

---

## 9. Vistas de arquitectura del sistema

Las vistas de diseño del sistema permiten a los desarrolladores y arquitectos de software entender y comunicar cómo está 
construido el sistema, cómo funcionan sus componentes y cómo interactúan entre sí.

### 9.1 Vista Funcional/Vista de Escenarios/Vista de Casos de Uso

La vista funcional es una representación enfocada en describir las funciones esenciales que el sistema debe realizar,
mostrando cómo se organizan en módulos o componentes que interactúan para cumplir con los requisitos. Su motivación 
principal es asegurar que tanto el equipo de desarrollo como los stakeholders tengan una comprensión común de las 
actividades clave, facilitando la planificación y minimizando los malentendidos durante la implementación. 
En el diseño del sistema, esta vista aporta una estructura clara y modular, donde cada función puede desarrollarse, 
probarse y actualizarse de forma independiente. Esto no solo permite construir un sistema escalable y adaptable a 
cambios futuros, sino que también facilita el mantenimiento, asegurando que el sistema pueda evolucionar de acuerdo
con nuevas necesidades sin comprometer su estabilidad o rendimiento.

---

### 9.2 Vista Lógica

La vista lógica es una representación que organiza y estructura los elementos del sistema desde una perspectiva de software, 
enfocándose en los componentes y sus interacciones sin entrar en detalles físicos o de implementación. Su motivación principal
es clarificar cómo se agrupan y relacionan los componentes en función de sus roles y responsabilidades, facilitando una comprensión 
clara de la arquitectura del sistema para el equipo de desarrollo y otros stakeholders. En el diseño del sistema, esta vista aporta 
una estructura bien definida que permite una separación clara de responsabilidades y dependencias, lo que facilita el mantenimiento,
la reutilización de componentes y la escalabilidad del sistema, asegurando que el desarrollo y la evolución sean coherentes y eficientes.

#### 9.2.1 Diagrama de clases

Un **diagrama de clases** es una representación gráfica de la estructura estática de un sistema orientado a objetos. 
Muestra las clases que componen el sistema, sus atributos, métodos y las relaciones existentes entre ellas, como 
asociaciones, herencia, agregación y composición.

### Motivación
El diagrama de clases se utiliza para modelar y organizar las entidades principales del sistema y la forma en que 
interactúan entre sí. Su propósito es ofrecer una visión clara de la estructura lógica del software antes de su 
implementación, facilitando la comprensión del dominio del problema y la definición de responsabilidades para cada clase.

### Aporte al diseño del sistema
El diagrama de clases aporta al diseño del sistema porque:

- Define la estructura de datos y objetos que compondrán la aplicación.
- Establece las relaciones entre las entidades del negocio.
- Permite identificar responsabilidades y comportamientos de cada clase.
- Sirve como guía para la implementación del código y el diseño de la base de datos.
- Facilita la comunicación entre los miembros del equipo de desarrollo.
- Ayuda a detectar redundancias o inconsistencias en el modelo antes de programar.


### 9.3 Vista de Despliegue/Vista de Desarrollo/Vista de Implementación

La vista de despliegue, también llamada vista de desarrollo o de implementación, es una representación que muestra cómo
y dónde se desplegarán los componentes del sistema en la infraestructura física, como servidores, contenedores o máquinas 
virtuales. Su motivación principal es asegurar que todos comprendan cómo el sistema se distribuye y funciona en el entorno
físico, considerando factores como rendimiento, disponibilidad y escalabilidad. En el diseño del sistema, esta vista aporta 
una comprensión clara sobre la disposición de los recursos, permitiendo planificar un despliegue óptimo que aproveche la 
infraestructura disponible, minimice tiempos de respuesta y facilite el mantenimiento, asegurando que el sistema esté bien
configurado para cumplir con sus requisitos técnicos y operativos.

#### 9.3.1 Diagrama de componentes

Un **diagrama de componentes** es una representación visual en la arquitectura de software que muestra cómo los distintos
módulos o componentes del sistema interactúan entre sí. Cada componente representa una unidad de software independiente 
que cumple una función específica dentro del sistema.

### Motivación
La principal motivación para usar un diagrama de componentes es descomponer el sistema en partes manejables y autónomas. 
Esta representación facilita la comprensión de la estructura interna del sistema, lo que ayuda a los equipos a identificar
cómo interactúan las diferentes partes y cómo se pueden desarrollar, probar, mantener y desplegar de manera independiente.

### Aportación al diseño del sistema
- **Claridad en la arquitectura:** Define de manera explícita qué hace cada componente y cómo se integra en el sistema, ayudando a visualizar el flujo y organización de la lógica.
- **Facilita la modularidad:** Al mostrar los componentes y sus interacciones, permite diseñar un sistema modular, en el cual las partes pueden desarrollarse y desplegarse de forma independiente, reduciendo la complejidad general.
- **Mejor gestión de dependencias:** Al ver cómo los componentes dependen entre sí, es posible gestionar y reducir las dependencias, facilitando un diseño más limpio y minimizando el acoplamiento.
- **Facilita el mantenimiento y la escalabilidad:** Ayuda a localizar componentes específicos para cambios o mejoras, y permite planificar de forma efectiva futuras expansiones o integraciones, asegurando que el sistema puede crecer sin comprometer la estructura inicial.

##### 9.3.1.1 Componente 1

**Descripción del componente:** Microservicio encargado de gestionar la información de los empleados del sistema LILFAC, incluyendo su creación, actualización, eliminación y consulta, así como la asignación de roles (administrador, cajero, bodega, logística) para el control de acceso por perfil en coordinación con Keycloak.

**Motivación del diagrama:** Diagrama encargado de mostrar todos los componentes técnicos involucrados en el microservicio lilfac-empleado-ms y su relación de dependencias.

- **Diagrama:** 
---

![img.png](img.png)

---
- **Documentación:**

  **Componente:** lilfac-employee-ms
  **Tipo:** Desarrollado
  **Depende de:**
  - Spring Boot 3.3.5
  - Java 21
  - postgresql 
  - Spring Cloud 4.1.3 
  
##### 9.3.1.2 Componente 2

**Descripción del componente:** Microservicio encargado de gestionar la información de los clientes de la empresa, incluyendo su registro, actualización, eliminación y consulta, con soporte para filtrado por nombre y cédula.

**Motivación del diagrama:** Diagrama encargado de mostrar todos los componentes técnicos involucrados en el microservicio lilfac-cliente-ms y su relación de dependencias.


- **Diagrama:** 
---
![img_1.png](img_1.png)
---

- **Documentación:**
- **Componente:** lilfac-customer-ms
  **Tipo:** Desarrollado
  **Depende de:**
    - Spring Boot 3.3.5
    - Java 21
    - postgresql
    - Spring Cloud 4.1.3


##### 9.3.1.3 Componente 3

**Descripción del componente:** Microservicio encargado de gestionar el catálogo de productos disponibles para alquiler, incluyendo su registro, actualización, eliminación, consulta y filtrado por código y categoría, así como el historial de costos de cada producto.

**Motivación del diagrama:** Diagrama encargado de mostrar todos los componentes técnicos involucrados en el microservicio lilfac-inventory-ms y su relación de dependencias.

-**Diagrama:** 

---
![img_2.png](img_2.png)
--- 
- **Documentación:**
- **Componente:** lilfac-inventory-ms
  **Tipo:** Desarrollado
  **Depende de:**
    - Spring Boot 3.3.5
    - Java 21
    - postgresql
    - Spring Cloud 4.1.3

##### 9.3.1.4 Componente 4
**Descripción del componente:** Microservicio encargado de gestionar el ciclo completo de los pedidos de alquiler, desde su creación hasta la entrega y recibimiento de productos, incluyendo la trazabilidad de modificaciones para auditoría.

**Motivación del diagrama:** Diagrama encargado de mostrar todos los componentes técnicos involucrados en el microservicio lilfac-order-ms y su relación de dependencias.

**Diagrama**
---
![img_3.png](img_3.png)
---
- **Documentación:**
- **Componente:** lilfac-order-ms
  **Tipo:** Desarrollado
  **Depende de:**
    - Spring Boot 3.3.5
    - Java 21
    - postgresql
    - Spring Cloud 4.1.3
  
##### 9.3.1.5 Componente 5
**Descripción del componente:** Microservicio encargado de gestionar la facturación del negocio, incluyendo la creación, actualización y eliminación de facturas con soporte para costos adicionales por multas, entrega tardía o daños de productos, así como la información de la empresa configurable para inclusión en documentos.

**Motivación del diagrama:** Diagrama encargado de mostrar todos los componentes técnicos involucrados en el microservicio lilfac-billing-ms y su relación de dependencias.

**Diagrama**
---
![img_4.png](img_4.png)
---

- **Documentación:**
- **Componente:** lilfac-billing-ms
  **Tipo:** Desarrollado
  **Depende de:**
    - Spring Boot 3.3.5
    - Java 21
    - postgresql
    - Spring Cloud 4.1.3

##### 9.3.1.6 Componente 6

**Descripción del componente:** Microservicio encargado de consolidar y analizar los datos del negocio mediante inteligencia artificial, generando recomendaciones de precios por temporada, identificando productos con baja disponibilidad y alta demanda, y facilitando la toma de decisiones estratégicas del administrador.

**Motivación del diagrama:** Diagrama encargado de mostrar todos los componentes técnicos involucrados en el microservicio lilfac-analytics-ms y su relación de dependencias.

**Diagrama**
---
![img_5.png](img_5.png)
---
- **Documentación:**
- **Componente:** lilfac-analytics-ms
  **Tipo:** Desarrollado
  **Depende de:**
    - Spring Boot 3.3.5
    - Java 21
    - postgresql
    - Spring Cloud 4.1.3

##### 9.3.1.7 Componente 7

**Descripción del componente:** Microservicio encargado de gestionar el envío de notificaciones multicanal (SMS, correo electrónico) a clientes y empleados, integrado con los eventos del sistema para disparar comunicaciones automáticas sobre pedidos, entregas, multas y alertas de inventario.

**Motivación del diagrama:** Diagrama encargado de mostrar todos los componentes técnicos involucrados en el microservicio lilfac-notification-ms y su relación de dependencias.

**Diagrama**
---
![img_6.png](img_6.png)
---
- **Documentación:**
- **Componente:** lilfac-notification-ms
  **Tipo:** Desarrollado
  **Depende de:**
    - Spring Boot 3.3.5
    - Java 21
    

#### 9.3.2 Diagrama de paquetes

Un **diagrama de paquetes** es un tipo de diagrama que muestra la organización y las relaciones de alto nivel entre los 
paquetes de un sistema. Un paquete es una forma de agrupar elementos relacionados, como clases o componentes, y funciona
como una "carpeta" lógica para organizar el sistema en módulos.

### Motivación
Simplificar y organizar el diseño del sistema para que sea más comprensible y manejable. Los sistemas grandes y complejos
pueden tener muchos elementos que, si se muestran juntos, resultan difíciles de entender y gestionar. Al dividirlos en 
paquetes, el sistema se estructura de forma modular, facilitando el análisis, desarrollo y mantenimiento.

### Aportes al diseño del sistema
- **Modularidad:** Ayuda a dividir el sistema en módulos (paquetes) que encapsulan funcionalidad específica, permitiendo que cada módulo sea independiente.
- **Escalabilidad:** Facilita la adición de nuevas funcionalidades o la modificación de las existentes sin afectar todo el sistema.
- **Claridad y mantenimiento:** Ofrece una visión clara de cómo está organizado el sistema, lo que facilita la comprensión y el mantenimiento a largo plazo.
- **Control de dependencias:** Permite visualizar las relaciones y dependencias entre paquetes, ayudando a identificar acoplamientos fuertes y promoviendo el bajo acoplamiento.
- **Facilita la colaboración:** Al tener una estructura modular, es más fácil que varios equipos trabajen en paralelo en diferentes partes del sistema sin interferencias.

**Diagrama**
---
![img_7.png](img_7.png)
---

###### Documentación de Paquetes
---
**Paquete padre:** —
**Paquete:** `java`
**Jerarquía:** `java`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete raíz del lenguaje que agrupa todos los componentes del proyecto LILFAC.
---
**Paquete padre:** java
**Paquete:** `co`
**Jerarquía:** `co`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete raíz de la organización que agrupa todos los componentes del proyecto LILFAC.
---
**Paquete padre:** `co`
**Paquete:** `edu`
**Jerarquía:** `co.edu`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que indica el contexto educativo del proyecto dentro de la organización.
 
---

**Paquete padre:** `co.edu`
**Paquete:** `uco`
**Jerarquía:** `co.edu.uco`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que identifica la Universidad Cooperativa de Colombia como organización propietaria del proyecto.
 
---

**Paquete padre:** `co.edu.uco`
**Paquete:** `lilfac`
**Jerarquía:** `co.edu.uco.lilfac`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete principal que contiene todos los microservicios del sistema LILFAC. Cada sub-paquete `<<component>>` representa un microservicio independiente: empleado, cliente, producto, inventario, pedido, factura, dashboard y notificacion.

---

**Paquete padre:** `co.edu.uco.lilfac`
**Paquete:** `<<component>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que representa la raíz de cada microservicio del sistema LILFAC. El estereotipo `<<component>>` se reemplaza por el nombre concreto del componente (empleado, cliente, producto, inventario, pedido, factura, dashboard, notificacion). Es el nivel inmediatamente inferior al paquete lilfac.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>`
**Paquete:** `application`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.crosscutting.exceptions`
- `co.edu.uco.lilfac.<<component>>.crosscutting.helpers`
  **Es usado por:** —
  **Descripción paquete:** Paquete que contiene la lógica de negocio y los procesos principales del microservicio, coordinando los casos de uso y las interacciones entre los puertos primarios y secundarios según los principios de Clean Architecture.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application`
**Paquete:** `primaryports`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.primaryports`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que define los puertos primarios de entrada del microservicio, estableciendo los contratos que deben cumplir los adaptadores primarios (controllers REST) para interactuar con la lógica de negocio.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.primaryports`
**Paquete:** `dto`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.primaryports.dto`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que contiene los objetos de transferencia de datos (DTO) usados para intercambiar información entre los adaptadores primarios y la lógica de negocio del microservicio.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.primaryports.dto`
**Paquete:** `<<domain object>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.primaryports.dto.<<domain object>>`
**Depende de:** —
**Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application.primaryports.mapper.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller.rest.<<domain object>>`
  **Descripción paquete:** Paquete que define los objetos de transferencia de datos específicos del dominio utilizados para comunicar información entre el adaptador primario y la lógica de negocio del microservicio.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.primaryports`
**Paquete:** `interactor`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que contiene las interfaces de los interactores encargados de coordinar la lógica de negocio entre los controladores REST y los casos de uso del microservicio.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor`
**Paquete:** `<<domain object>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor.<<domain object>>`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.application.primaryports.dto.<<domain object>>`
  **Es usado por:**
- `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller.rest.<<domain object>>`
  **Descripción paquete:** Paquete que define las interfaces de los interactores específicos para cada objeto de dominio del microservicio.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor.<<domain object>>`
**Paquete:** `impl`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor.<<domain object>>.impl`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.application.primaryports.mapper.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.application.primaryports.dto.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.application.usecase.<<domain object>>.impl`
  **Es usado por:** —
  **Descripción paquete:** Paquete que implementa los interactores específicos del dominio, coordinando el mapeo de DTOs y la ejecución de los casos de uso del microservicio.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.primaryports`
**Paquete:** `mapper`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.primaryports.mapper`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que contiene los mappers responsables de transformar datos entre objetos de dominio y DTOs, facilitando la conversión y consistencia de datos entre la capa de entrada y la lógica de negocio.
 
---


**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.primaryports.mapper`
**Paquete:** `<<domain object>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.primaryports.mapper.<<domain object>>`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.application.primaryports.dto.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>`
  **Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor.<<domain object>>.impl`
  **Descripción paquete:** Paquete que contiene los mappers específicos del dominio para transformar objetos de dominio en DTOs y viceversa.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application`
**Paquete:** `secondaryports`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.secondaryports`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que define los puertos secundarios de salida del microservicio, estableciendo los contratos hacia recursos externos como PostgreSQL, Redis, Twilio, Amazon S3 y HashiCorp Vault.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.secondaryports`
**Paquete:** `mapper`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.mapper`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que contiene los mappers encargados de transformar datos entre el dominio y las entidades de persistencia utilizadas en los adaptadores secundarios.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.mapper`
**Paquete:** `<<domain object>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.mapper.<<domain object>>`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.application.secondaryports.entity.<<domain object>>`
  **Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application.usecase.<<domain object>>.impl`
  **Descripción paquete:** Paquete que contiene los mappers específicos para transformar objetos de dominio en entidades de persistencia y viceversa.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.secondaryports`
**Paquete:** `entity`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.entity`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que contiene las entidades JPA que representan las estructuras de datos persistentes utilizadas para interactuar con la base de datos PostgreSQL del microservicio.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.entity`
**Paquete:** `<<domain object>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.entity.<<domain object>>`
**Depende de:** —
**Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application.secondaryports.repository.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.application.secondaryports.mapper.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters.data.repository`
  **Descripción paquete:** Paquete que contiene las entidades JPA específicas del dominio para su almacenamiento y recuperación en PostgreSQL mediante Spring Data JPA.

---
**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.secondaryports`
**Paquete:** `repository`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.repository`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que define las interfaces de repositorio para gestionar las operaciones de persistencia de datos en PostgreSQL.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.repository`
**Paquete:** `<<domain object>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.secondaryports.repository.<<domain object>>`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.application.secondaryports.entity.<<domain object>>`
  **Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application.usecase.<<domain object>>.impl`
- `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters.data.repository`
  **Descripción paquete:** Paquete que define las interfaces de repositorio específicas del dominio para gestionar las operaciones de persistencia del microservicio.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application`
**Paquete:** `usecase`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.usecase`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que contiene los casos de uso del microservicio, coordinando la lógica de negocio entre los puertos primarios y secundarios.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.usecase`
**Paquete:** `<<domain object>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.usecase.<<domain object>>`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que agrupa los casos de uso específicos del objeto de dominio dentro del microservicio.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.application.usecase.<<domain object>>`
**Paquete:** `impl`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.application.usecase.<<domain object>>.impl`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.application.secondaryports.repository.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.application.secondaryports.mapper.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>.rules`
  **Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor.<<domain object>>.impl`
  **Descripción paquete:** Paquete que implementa los casos de uso del dominio, orquestando las reglas de negocio, los mapeos y las operaciones de persistencia necesarias para completar cada transacción del microservicio.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>`
**Paquete:** `crosscutting`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.crosscutting`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que agrupa los componentes transversales del microservicio, incluyendo el manejo de excepciones y utilidades auxiliares compartidas entre todas las capas.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.crosscutting`
**Paquete:** `exceptions`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.crosscutting.exceptions`
**Depende de:** —
**Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application`
- `co.edu.uco.lilfac.<<component>>.infrastructure`
  **Descripción paquete:** Paquete que centraliza el manejo de excepciones del microservicio, definiendo las clases base para errores de negocio, validación y sistema.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.crosscutting`
**Paquete:** `helpers`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.crosscutting.helpers`
**Depende de:** —
**Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application`
- `co.edu.uco.lilfac.<<component>>.infrastructure`
  **Descripción paquete:** Paquete que contiene las clases utilitarias y auxiliares compartidas entre las capas del microservicio, como validadores, formateadores y constantes del sistema.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>`
**Paquete:** `domain`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.domain`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que contiene el núcleo del dominio del microservicio, representando las entidades de negocio, las reglas de dominio y las excepciones específicas, independientes de cualquier framework o tecnología externa.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.domain`
**Paquete:** `<<domain object>>`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que agrupa los elementos del dominio para un objeto específico del microservicio, incluyendo su representación, reglas de negocio y excepciones.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>`
**Paquete:** `exception`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>.exception`
**Depende de:** —
**Es usado por:**
- `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>.rules.impl`
  **Descripción paquete:** Paquete que gestiona las excepciones específicas del objeto de dominio, proporcionando control de errores particular a las reglas y entidades del microservicio.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>`
**Paquete:** `rules`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>.rules`
**Depende de:** —
**Es usado por:**
- `co.edu.uco.lilfac.<<component>>.application.usecase.<<domain object>>.impl`
  **Descripción paquete:** Paquete que contiene las interfaces de las reglas de negocio del objeto de dominio, estableciendo las condiciones y restricciones que gobiernan el comportamiento del microservicio.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>.rules`
**Paquete:** `impl`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>.rules.impl`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.domain.<<domain object>>.exception`
  **Es usado por:** —
  **Descripción paquete:** Paquete que implementa las reglas de negocio específicas del objeto de dominio, proporcionando la lógica detallada que define el comportamiento y las restricciones del microservicio según las reglas del negocio de alquiler de eventos.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>`
**Paquete:** `features`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.features`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que agrupa las funcionalidades transversales del microservicio como auditoría, trazabilidad de modificaciones y filtros avanzados de búsqueda. En microservicios como lilfac-pedido y lilfac-factura, este paquete gestiona el registro de quién modificó cada transacción, dato crítico para los procesos de auditoría del negocio.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>`
**Paquete:** `infrastructure`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure`
**Depende de:**
- `co.edu.uco.lilfac.<<component>>.crosscutting.exceptions`
- `co.edu.uco.lilfac.<<component>>.crosscutting.helpers`
  **Es usado por:** —
  **Descripción paquete:** Paquete que gestiona los componentes de infraestructura del microservicio, incluyendo la configuración y el acceso a recursos externos como PostgreSQL, Redis, Twilio, Amazon S3 y HashiCorp Vault.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure`
**Paquete:** `primaryadapters`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que contiene los adaptadores primarios del microservicio, implementando la comunicación entre las solicitudes HTTP recibidas desde Kong Gateway y los interactores de la lógica de negocio.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters`
**Paquete:** `controller`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller`
**Depende de:** —
**Es usado por:** —
**Descripción paquete:** Paquete que define los controladores de los adaptadores primarios, gestionando las solicitudes externas recibidas a través de Kong Gateway y actuando como puntos de entrada del microservicio.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller`
**Paquete:** `response`
**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller.response`
**Depende de:** —
**Es usado por:**
- `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller.rest.<<domain object>>`
  **Descripción paquete:** Paquete que contiene las clases de respuesta de los controladores, estructurando los datos que se envían al cliente tras procesar una solicitud.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller`

**Paquete:** `rest`

**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller.rest`

**Depende de:** —

**Es usado por:** —

**Descripción paquete:** Paquete que contiene los controladores REST del microservicio, encargados de exponer los servicios del componente a través de endpoints HTTP consumidos por el frontend de LILFAC vía Kong Gateway.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller.rest`

**Paquete:** `<<domain object>>`

**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller.rest.<<domain object>>`

**Depende de:**
- `co.edu.uco.lilfac.<<component>>.application.primaryports.interactor.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.infrastructure.primaryadapters.controller.response`
- `co.edu.uco.lilfac.<<component>>.application.primaryports.dto.<<domain object>>`

- **Es usado por:** —
  
- **Descripción paquete:** Paquete que define los controladores REST específicos para los objetos de dominio del microservicio, manejando las solicitudes HTTP y delegando la ejecución al interactor correspondiente.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure`

**Paquete:** `secondaryadapters`

**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters`

**Depende de:** —

**Es usado por:** —

**Descripción paquete:** Paquete que agrupa los adaptadores secundarios del microservicio, facilitando la interacción con sistemas externos como PostgreSQL, Redis, Twilio, Amazon S3 y Debezium.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters`

**Paquete:** `data`

**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters.data`

**Depende de:** —

**Es usado por:** —

**Descripción paquete:** Paquete que contiene las clases de acceso y manejo de datos en los adaptadores secundarios, permitiendo la persistencia y recuperación de información desde PostgreSQL mediante Spring Data JPA.
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters.data`

**Paquete:** `repository`

**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters.data.repository`

**Depende de:**
- `co.edu.uco.lilfac.<<component>>.application.secondaryports.repository.<<domain object>>`
- `co.edu.uco.lilfac.<<component>>.application.secondaryports.entity.<<domain object>>`

- **Es usado por:** —
  
- **Descripción paquete:** Paquete que implementa los repositorios de datos en los adaptadores secundarios, gestionando las operaciones CRUD en PostgreSQL a través de Spring Data JPA.

---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters`

**Paquete:** `services`

**Jerarquía:** `co.edu.uco.lilfac.<<component>>.infrastructure.secondaryadapters.services`

**Depende de:** —

**Es usado por:** —

**Descripción paquete:** Paquete que contiene los servicios de los adaptadores secundarios, proporcionando integración con sistemas externos como Twilio (SMS/WhatsApp), Amazon S3 (almacenamiento de facturas en PDF) y HashiCorp Vault (gestión de secretos).
 
---

**Paquete padre:** `co.edu.uco.lilfac.<<component>>`

**Paquete:** `initializer`

**Jerarquía:** `co.edu.uco.lilfac.<<component>>.initializer`

**Depende de:**
- `co.edu.uco.lilfac.<<component>>.application`
- `co.edu.uco.lilfac.<<component>>.infrastructure`

- **Es usado por:** —
  
- **Descripción paquete:** Paquete que contiene la clase principal de arranque del microservicio (Spring Boot Application), responsable de inicializar el contexto de la aplicación, cargar la configuración desde Spring Cloud Config y registrar el servicio en el ecosistema de LILFAC.

---



##### 9.3.2.1 Componente 1

- **Diagrama:** *\<Muestre el diagrama de paquetes en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de paquetes del componente en cuestión con la documentación respectiva.\>*

##### 9.3.2.2 Componente 2

- **Diagrama:** *\<Muestre el diagrama de paquetes en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de paquetes del componente en cuestión con la documentación respectiva.\>*

##### 9.3.2.N Componente N

- **Diagrama:** *\<Muestre el diagrama de paquetes en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de paquetes del componente en cuestión con la documentación respectiva.\>*

---

### 9.4 Vista de Procesos

La vista de procesos es una representación que describe cómo se ejecutan y sincronizan los procesos dentro del sistema, 
mostrando la interacción y comunicación entre componentes en tiempo de ejecución. Su principal motivación es proporcionar
claridad sobre el flujo de trabajo, la concurrencia y la gestión de tareas, asegurando que todos comprendan cómo se 
coordinan los procesos para cumplir con las funciones del sistema de manera eficiente. En el diseño del sistema, esta
vista aporta una estructura que optimiza la distribución de tareas, facilita el manejo de múltiples usuarios y mejora
el rendimiento, ya que permite identificar cuellos de botella, gestionar recursos y asegurar que el sistema opere de 
manera estable y efectiva bajo distintas cargas de trabajo.

#### 9.4.1 Diagrama de secuencia

Un diagrama de secuencia es un tipo de diagrama utilizado en ingeniería de software que muestra cómo interactúan los 
diferentes componentes o partes de un sistema entre sí a lo largo del tiempo. Describe el flujo de mensajes y eventos 
entre objetos, componentes o actores (como usuarios) para cumplir una función o proceso específico del sistema, con el
tiempo representado en el eje vertical y los participantes en el eje horizontal.

##### 9.4.1.1 Componente 1 Without Return

- **Diagrama:** *\<Muestre el diagrama de secuencia en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de secuencia del componente en cuestión con la documentación respectiva.\>*

##### 9.4.1.2 Componente 2 With Return

- **Diagrama:** *\<Muestre el diagrama de secuencia en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de secuencia del componente en cuestión con la documentación respectiva.\>*

##### 9.4.1.N Componente N

- **Diagrama:** *\<Muestre el diagrama de secuencia en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de secuencia del componente en cuestión con la documentación respectiva.\>*

#### 9.4.2 Diagrama de colaboración

*\<Defina en términos comprensibles qué es diagrama de colaboración, cuál es su motivación y qué le aporta al diseño del sistema.\>*

##### 9.4.2.1 Componente 1

- **Diagrama:** *\<Muestre el diagrama de colaboración en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de colaboración del componente en cuestión con la documentación respectiva.\>*

##### 9.4.2.2 Componente 2

- **Diagrama:** *\<Muestre el diagrama de colaboración en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de colaboración del componente en cuestión con la documentación respectiva.\>*

##### 9.4.2.N Componente N

- **Diagrama:** *\<Muestre el diagrama de colaboración en cuestión.\>*
- **Documentación:** *\<Muestre y/o detalle el diagrama de colaboración del componente en cuestión con la documentación respectiva.\>*

---

### 9.5 Vista Física/Vista de Implantación

La vista física, o vista de implantación, es una representación que muestra cómo los componentes del sistema se distribuyen en el hardware 
físico, incluyendo servidores, redes y dispositivos. Su motivación principal es asegurar una comprensión clara de cómo el sistema se desplegará 
en la infraestructura física, considerando aspectos como la ubicación de los recursos, la conectividad de red y los requisitos de hardware. 

En el diseño del sistema, esta vista aporta una guía detallada para organizar el despliegue de manera óptima, garantizando que la infraestructura 
soporte adecuadamente la carga de trabajo, minimice los tiempos de respuesta y facilite la escalabilidad y el mantenimiento del sistema, asegurando
una operación confiable y eficiente en el entorno real.


#### 9.5.1 Diagrama de despliegue

Un diagrama de despliegue muestra la arquitectura física de un sistema, es decir, cómo se organizan y distribuyen los elementos del software en el
hardware. Este diagrama detalla qué componentes de software se ejecutan en qué nodos de hardware (servidores, bases de datos, dispositivos, etc.) 
y cómo estos elementos se comunican entre sí a través de redes o conexiones.

##### 9.5.1.1 Diagrama
![img_2.png](arquetipoReferencia.png)

##### 9.5.1.2 Documentación

---

### **Documentación Arquetipo de solución/referencia**

---


#### DNS Domain Name System
<u>Motivación</u>: Proveer resolución de nombres de dominio para abstraer la dirección IP de la infraestructura
subyacente, permitiendo que el sistema Lilfac sea accesible mediante un FQDN (Fully Qualified Domain Name) en lugar de
direcciones IP directas lo que permite a los usuarios acceder al sistema Lilfac mediante un nombre de dominio legible, sin
necesidad de conocer direcciones IP internas de la infraestructura.
También es indispensable para la operación de componentes como el WAF y el CDN que dependen de resolución DNS para el
enrutamiento del tráfico.

<u>Uso</u>: Resolver las consultas DNS que provienen de los clientes, traduciendo el nombre de dominio de la aplicación
en la dirección IP del siguiente componente en la cadena de red.

<u>Justificación</u>: Sin este componente, el sistema no sería accesible desde Internet de forma amigable ni escalable.
Además, permite abstraer la infraestructura real del sistema, facilitando cambios futuros de servidores o regiones sin
afectar la experiencia del usuario, La ausencia del DNS gestionado implicaría una dependencia directa en IPs estáticas,
lo que haría inviable cualquier estrategia de alta disponibilidad.

#### WAF Web Application Firewall

<u>Motivación</u>: Proteger el sistema Lilfac contra ataques externos estableciendo un perímetro de seguridad a nivel
de capa 7 del modelo OSI _(Capa de aplicación)_ que inspeccione el tráfico HTTP/HTTPS antes de que alcance cualquier
componente interno del sistema, mitigando vectores de ataque dirigidos específicamente a la capa de aplicación.

<u>Uso</u>: Inspeccionar y filtrar todo el tráfico HTTP/HTTPS entrante, bloqueando solicitudes que contengan patrones
de ataque conocidos como SQL Injection, XSS (Cross-Site Scripting), escaneo de vulnerabilidades o intentos de denegación
de servicio.

<u>Justificación</u>: Al ser una aplicación web expuesta a Internet, si no tuviese inspección en la capa 7 quedaría
vulnerable a exploits automatizados que no son detectables por firewalls de red tradicionales.
El WAF actúa como primera línea de defensa activa, reduciendo significativamente la superficie
de ataque antes de que cualquier solicitud llegue al CDN, al Frontend o al Backend.


#### CDN Content Delivery Network

<u>Motivación</u>: Garantizar que los usuarios de Lilfac reciban la interfaz de usuario con la menor latencia posible,
independientemente de su ubicación geográfica.

<u>Uso</u>: Distribuir y servir los archivos estáticos del Frontend Lilfac, como HTML, CSS, JavaScript e imágenes,
desde nodos de red cercanos al usuario. Además, enrutar las solicitudes dinámicas hacia el API Gateway.

<u>Justificación</u>: Mejora notablemente la velocidad de carga de la aplicación al evitar que cada solicitud de
contenido estático recorra toda la cadena hasta el servidor de origen. Al mismo tiempo, actúa como punto de
distribución inteligente del tráfico dinámico hacia el interior del sistema.

#### Storage Account

<u>Motivación</u>: Proveer un mecanismo de almacenamiento persistente y altamente disponible para alojar los archivos
estáticos del Frontend del sistema Lilfac, como HTML, CSS, JavaScript, imágenes, íconos y fuentes. Este componente
permite desacoplar la capa de presentación de la infraestructura de procesamiento, ofreciendo un repositorio optimizado
para servir contenido estático de forma segura y escalable.

<u>Uso</u>: Almacenar los artefactos compilados del Frontend y actuar como origen del CDN, desde donde se distribuyen
los recursos estáticos a los usuarios finales. Cada vez que se publica una nueva versión de la aplicación, los archivos
generados por el proceso de despliegue se cargan en este componente para quedar disponibles de manera inmediata.

<u>Justificación</u>: Sin este componente, los archivos del Frontend tendrían que hospedarse directamente en servidores
de aplicación, incrementando costos y acoplando innecesariamente la interfaz de usuario con la lógica del negocio.
El Storage Account ofrece alta durabilidad, disponibilidad y escalabilidad para contenido estático, permitiendo
desplegar nuevas versiones del Frontend de forma sencilla y sirviendo como origen confiable para el CDN, lo que mejora
el rendimiento y simplifica la arquitectura del sistema.

#### Front End Lilfac

<u>Motivación</u>: Proveer la interfaz gráfica con la que los usuarios interactúan para realizar las operaciones del
sistema Lilfac, como registrar cliente, registrar empleados, gestionar inventario, crear pedidos y consultar facturas.
Este componente traduce las funcionalidades del negocio en una experiencia visual intuitiva, accesible y fácil de usar.

<u>Uso</u>: Presentar formularios, tablas, reportes y paneles interactivos que permiten capturar información y visualizar
resultados. El Frontend consume los servicios expuestos por el Backend mediante APIs, enviando solicitudes y mostrando al
usuario la información procesada por el sistema.

<u>Justificación</u>: Sin este componente, los usuarios no contarían con un medio práctico para interactuar con el sistema.
Además, al separar la interfaz de usuario de la lógica de negocio, se facilita el mantenimiento, la evolución del diseño y
la posibilidad de adaptar la aplicación a distintos dispositivos y necesidades de usabilidad sin afectar los componentes
internos.

#### API Gateway

<u>Motivación</u>: Centralizar y controlar el acceso de todos los clientes implementando un único punto de entrada
para todas las solicitudes hacia el Backend Lilfac, centralizando funciones transversales como autenticación,
autorización, control de tráfico y observabilidad que de otro modo deberían ser implementadas de forma redundante
en cada servicio del Backend.

<u>Uso</u>: Recibir todas las solicitudes dinámicas provenientes del Frontend, validar los tokens de autenticación
en conjunto con el IAM, aplicar políticas de seguridad como rate limiting, y enrutar cada solicitud al endpoint
correspondiente del Backend Lilfac.

<u>Justificación</u>: Evita que los clientes interactúen directamente con el Backend, reduciendo la exposición de la
lógica interna del sistema. Centraliza funciones transversales como autenticación, logging de peticiones y
control de tráfico, simplificando considerablemente la arquitectura del Backend.

#### Back End Lilfac

<u>Motivación</u>: Centralizar la lógica de negocio del sistema Lilfac, implementando las reglas que controlan procesos
como la gestión de inventario, reservas, alquileres, facturación y autenticación de usuarios. Este componente actúa como
núcleo funcional del sistema y garantiza la integridad y consistencia de la información.

<u>Uso</u>: Recibir las solicitudes enviadas por el Frontend, validar los datos, ejecutar las reglas del negocio,
interactuar con la base de datos y con el Storage Account, y devolver respuestas estructuradas a los clientes.
También se encarga de aplicar controles de seguridad y auditoría.

<u>Justificación</u>: Sin este componente, no existiría un punto central encargado de procesar las operaciones
del sistema ni de garantizar que se cumplan las reglas del negocio. El Backend permite desacoplar la lógica funcional
de la interfaz de usuario, facilita la reutilización de servicios y proporciona una arquitectura más segura, mantenible
y escalable.

#### IAM Identity and access management

<u>Motivación</u>: Centralizar la gestión del ciclo de vida de identidades digitales y el control de acceso basado en
roles (RBAC) para todos los usuarios y servicios que interactúan con el sistema Lilfac lo cual garantiza que únicamente
los usuarios y servicios autorizados puedan acceder a los recursos y funcionalidades del sistema.

<u>Uso</u>: Gestionar la autenticación de usuarios mediante la validación de credenciales y la emisión de tokens de
seguridad, así como controlar la autorización definiendo qué acciones puede ejecutar cada usuario según su rol
dentro del sistema.

<u>Justificación</u>: Es el componente que sostiene la seguridad de acceso de todo el sistema. Sin él, no existiría
un mecanismo centralizado y confiable para distinguir entre un usuario administrador, un operador o un cliente,
ni para proteger los datos sensibles que maneja Lilfac.

#### CI /CD pipeline

<u>Motivación</u>: Automatizar el ciclo completo de construcción, pruebas y despliegue del software de Lilfac,
reduciendo el riesgo de errores manuales en cada entrega.

<u>Uso</u>: Detectar cambios en el repositorio de código, ejecutar automáticamente las pruebas definidas, construir
los artefactos del Frontend y del Backend, y desplegarlos en los ambientes correspondientes de forma controlada
y repetible.

<u>Justificación</u>: Permite que el equipo de desarrollo entregue nuevas funcionalidades y correcciones de forma ágil
y segura. Garantiza que ningún cambio llegue a producción sin haber pasado por un proceso de validación, lo que
reduce considerablemente los tiempos de detección de errores y los riesgos asociados a los despliegues.

#### Cache

<u> Motivación</u>: Reducir la carga sobre la base de datos SQL y mejorar los tiempos de respuesta del Backend de 
Lilfac ante consultas frecuentes o costosas.

<u>Uso</u>: Almacenar temporalmente resultados de consultas que el Backend solicita con alta frecuencia, de
manera que puedan ser retornados directamente sin necesidad de ejecutar nuevamente la consulta completa
contra la base de datos.

<u>Justificación</u>: En un sistema que puede recibir múltiples solicitudes concurrentes, acceder repetidamente
a la base de datos para los mismos datos representa un cuello de botella. La caché permite escalar el rendimiento
del sistema sin incrementar los recursos de base de datos, mejorando la experiencia del usuario final.

#### Base de datos

<u> Motivación</u> : Proveer almacenamiento persistente, estructurado y confiable para todos los datos de negocio 
que gestiona el sistema Lilfac.

<u>Uso</u>: Guardar y gestionar la información crítica del sistema como usuarios, registros operativos, transacciones
y cualquier entidad del dominio del negocio, garantizando integridad referencial y consistencia de los datos.

<u>Justificación</u>: Es el núcleo de persistencia del sistema. Toda la lógica de negocio del Backend depende de la
capacidad de leer y escribir datos de forma confiable. Una base de datos SQL relacional asegura la integridad de los datos y permite consultas complejas necesarias para las operaciones del sistema.


#### CDC Change Data Capture

<u> Motivación</u> : Detectar y propagar en tiempo real los cambios que ocurren en la base de datos SQL de 
Lilfac sin impactar el rendimiento del sistema principal.

<u> Uso</u> : Capturar eventos de inserción, actualización y eliminación en la base de datos y ponerlos a 
disposición de otros procesos o sistemas que necesiten reaccionar ante esos cambios, como procesos de auditoría,
sincronización o integración con sistemas externos.

<u> Justificación</u> : Permite que el sistema evolucione hacia integraciones y procesos reactivos sin necesidad
de implementar consultas periódicas a la base de datos, lo que sería ineficiente y costoso. Facilita la 
trazabilidad de cambios y sienta las bases para capacidades de auditoría y análisis de datos en tiempo real.


#### Parameter Catalog

<u> Motivación</u> : Centralizar la gestión de los parámetros de configuración del sistema Lilfac para que puedan
ser modificados sin necesidad de redesplegar el Backend.

<u>Uso</u>: Almacenar y exponer vía API valores configurables del sistema como umbrales, límites operativos,
indicadores de comportamiento y cualquier parámetro que controle la lógica de negocio del Backend.

<u>Justificación</u>: Separa la configuración del código, lo que otorga flexibilidad operativa al sistema.
Un cambio en un parámetro de negocio no implica un nuevo despliegue, reduciendo el riesgo operativo y permitiendo
ajustes rápidos ante cambios en los requisitos del negocio.


#### Message Catalog

<u>Motivación</u>: Centralizar todos los textos, mensajes de error y literales que el sistema Lilfac utiliza
en sus respuestas hacia el usuario o entre componentes.

<u>Uso</u>: Proveer al Backend y al Frontend un repositorio único de mensajes estandarizados que pueden
consultarse vía API, garantizando consistencia en la comunicación del sistema y facilitando soporte multiidioma
si el proyecto lo requiere.

<u>Justificación</u>: Evita que los mensajes estén dispersos y duplicados en el código de los distintos componentes.
Asegura uniformidad en la experiencia del usuario y simplifica el mantenimiento, ya que cualquier cambio en un texto
se realiza en un solo lugar.


#### Notification Catalog

<u>Motivación</u>: Centralizar las plantillas de notificación que el sistema Lilfac utiliza para comunicarse con los
usuarios a través del Notification Gateway.

<u>Uso</u>: Almacenar y exponer las plantillas estructuradas de correos electrónicos, SMS y notificaciones push,
incluyendo su contenido, formato y variables dinámicas que el Notification Gateway completa antes de enviar cada mensaje.

<u>Justificación</u>: Desacopla el contenido de las notificaciones de la lógica del Backend y del Gateway.
Permite que las plantillas sean gestionadas y actualizadas de forma centralizada sin modificar el código,
garantizando consistencia en todas las comunicaciones enviadas a los usuarios.


#### Notification Gateway

Notification Gateway
<u>Motivación</u>: Proveer un canal centralizado y desacoplado para el envío de notificaciones a los usuarios del sistema
Lilfac.

<u>Uso</u>: Recibir instrucciones del Backend indicando qué notificación enviar y a quién, consultar la plantilla
correspondiente en el Notification Catalog, y ejecutar el envío a través del canal adecuado, ya sea correo electrónico,
SMS o notificación push.

<u>Justificación</u>: Abstrae al Backend de los detalles técnicos de cada canal de notificación. Si en el futuro se
agrega un nuevo canal de comunicación, el cambio se realiza únicamente en el Gateway sin afectar la lógica del Backend,
lo que mejora la mantenibilidad y escalabilidad del sistema.


#### Key Vault

<u>Motivación</u>: Proteger todos los secretos, credenciales y claves criptográficas que el sistema Lilfac necesita
para operar, manteniéndolos fuera del código fuente y de los archivos de configuración.

<u>Uso</u>: Almacenar de forma segura contraseñas de bases de datos, claves de APIs externas, certificados y tokens
de servicio, permitiendo que el Backend los consulte en tiempo de ejecución mediante acceso controlado y auditado.

<u>Justificación</u>: Elimina el riesgo de exponer información sensible en el repositorio de código o en variables de
entorno sin cifrar. Centraliza la gestión de secretos con control de acceso granular, lo que facilita la rotación de
credenciales y el cumplimiento de buenas prácticas de seguridad.


#### APM Application performance monitoring

<u>Motivación</u>: Tener visibilidad continua sobre el comportamiento, el rendimiento y la salud del sistema Lilfac
en ambientes productivos.

<u>Uso</u>: Recopilar métricas de rendimiento, trazas de ejecución, registros de errores y excepciones del Backend en
tiempo real, generando alertas automáticas cuando se detectan degradaciones o fallos en el sistema.

<u>Justificación</u>: Sin observabilidad, los problemas en producción son difíciles de detectar y aún más difíciles de
diagnosticar. El APM permite al equipo identificar cuellos de botella, errores recurrentes y comportamientos anómalos
antes de que impacten negativamente a los usuarios, reduciendo los tiempos de respuesta ante incidentes.


---
