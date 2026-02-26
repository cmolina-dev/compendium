---
title: "Patrones de Comunicación entre Agentes"
category: "arquitectura-multiagente"
description: "Diferentes estrategias para la comunicación efectiva entre agentes en sistemas distribuidos de IA"
date: 2025-02-24
tags: ["agentes", "comunicacion", "mensajeria", "arquitectura"]
draft: false
order: 2
---

## Introducción

La comunicación entre agentes es fundamental para sistemas multiagente efectivos. Este documento explora los principales patrones utilizados en la industria.

## Patrones de Comunicación

### 1. Request-Response

El patrón más simple: un agente hace una pregunta y espera respuesta.

```mermaid
sequenceDiagram
    participant A as Agente A
    participant B as Agente B
    A->>B: Request
    B->>A: Response
```

### 2. Pub/Sub (Publicador-Suscriptor)

Los agentes publican eventos y otros se suscriben a los que les interesan.

```mermaid
graph TD
    P[Publicador] -->|evento| B[Message Broker]
    B -->|evento| S1[Suscriptor 1]
    B -->|evento| S2[Suscriptor 2]
    B -->|evento| S3[Suscriptor 3]
```

**Ventajas:**
- Desacoplamiento total
- Escalabilidad horizontal
- Nuevos suscriptores sin cambios

### 3. Blackboard Pattern

Un espacio compartido donde los agentes leen y escriben información.

```mermaid
graph TD
    A1[Agente 1] <-->|lee/escribe| BB[Blackboard]
    A2[Agente 2] <-->|lee/escribe| BB
    A3[Agente 3] <-->|lee/escribe| BB
    C[Controller] -->|coordina| BB
```

**Casos de uso:**
- Resolución colaborativa de problemas
- Sistemas expertos
- Planificación distribuida

