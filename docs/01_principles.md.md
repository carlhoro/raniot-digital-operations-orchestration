Principio 1 — Orquestación centralizada, no flujos aislados
    Las operaciones digitales no se conciben como flujos independientes, sino como procesos orquestados.
        Ningún sistema de origen contiene lógica de negocio
        Ningún sistema de destino controla el proceso
        La coordinación ocurre en una capa central
    n8n actúa como núcleo de orquestación, no como simple herramienta de automatización.
        Automatizar sin orquestar genera silos invisibles.

Principio 2 — Eventos como lenguaje común
    Todas las interacciones se modelan como eventos, independientemente de su origen o destino.
    Esto permite:
        Desacoplar plataformas
        Normalizar entradas heterogéneas
        Evolucionar el sistema sin rediseños estructurales
    Un evento no implica una acción inmediata; implica una decisión pendiente.

Principio 3 — Separación estricta de responsabilidades
    Cada componente del sistema tiene un rol único y delimitado.
        Rol	                Qué hace	        Qué no hace
        Fuentes	            Emiten eventos	    Decidir
        Orquestación	    Decide y coordina	Ejecutar directamente
        Extensiones	        Enriquecen	        Orquestar
        Destinos	        Ejecutan	        Gobernar
        Gobierno (RANIOT)	Define reglas	    Operar flujos
    Esta separación reduce riesgos, facilita auditoría y permite escalabilidad organizacional.

Principio 4 — Gobierno antes que automatización
    No se automatiza nada que no pueda:
        Auditarse
        Explicarse
        Controlarse
        Desactivarse
    La automatización sin gobierno técnico es una fuente de deuda operativa.
    El gobierno incluye:
        Control de accesos
        Manejo de credenciales
        Versionamiento de flujos
        Gestión de incidentes

Principio 5 — Seguridad por diseño, no por excepción
    La seguridad no es un agregado posterior.

    Se asume que:
        Toda credencial es sensible
        Todo webhook es una superficie de ataque
        Todo flujo puede fallar
    Por lo tanto:
        Las credenciales nunca viven en el repositorio
        Los secretos se gestionan externamente
        Los errores son estados esperados

Principio 6 — Evolución incremental y versionada
    La arquitectura está diseñada para evolucionar
    Esto implica:
        Diagramas versionados
        Cambios documentados
        Decisiones justificadas
        La estabilidad se prioriza sobre la velocidad.

Principio 7 — Observabilidad y trazabilidad

    Todo evento relevante debe poder:
        Rastrearse
        Correlacionarse
        Auditarse
    La trazabilidad es un requisito funcional
        Diagnóstico rápido
        Mejora continua
        Defensa técnica de decisiones automatizadas

Principio 8 — Documentación como activo técnico
    La documentación:
        No es decorativa
        No es posterior
        No es opcional
    Es un activo técnico que permite:
        Onboarding de nuevos miembros
        Transferencia de conocimiento
        Evaluación externa de la arquitectura
        Este repositorio existe precisamente para cumplir ese rol.

Principio 9 — Claridad antes que complejidad
    Si una solución no puede explicarse claramente:
        Está mal diseñada
        O aún no está lista
    La complejidad solo se acepta cuando es inevitable y justificada.
