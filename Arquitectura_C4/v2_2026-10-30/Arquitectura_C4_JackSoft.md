---
title: "Arquitectura de Software C4 — JackSoft"
system: "JackSoft"
client: "La Coca de Jacks S.A.S."
type: Architecture
tags:
  - c4-model
  - arquitectura
  - uml
---

# Arquitectura de Software C4 — JackSoft

Arquitectura de JackSoft en los cuatro niveles del modelo C4, alineada con `04_Modelado_DB/Modelo_Relacional/v3_2026-10-30/bd.uml` **v3.5** y la guía [`Diagramas C4.pptx.txt`](../Referencia/Diagramas%20C4.pptx.txt).

> **Estado (2026-10-30):** las fuentes `.puml` están actualizadas y las imágenes están en [Evidencia_C4_PNG/](Evidencia_C4_PNG/). Se dibujaron con Graphviz desde esos `.puml`, porque no hay Java para usar PlantUML; por eso no llevan la leyenda ni el estilo exacto de C4-PlantUML. Los archivos anteriores, basados en el modelo V2, están en [v1_2026-09-14/](../v1_2026-09-14/).

## Niveles

| Nivel | Responde | Fuente |
|---|---|---|
| 1. Contexto | ¿Quién usa el sistema y con qué sistemas externos se conecta? | [C4_Nivel1_Contexto.puml](C4_Nivel1_Contexto.puml) |
| 2. Contenedores | ¿Qué aplicaciones y almacenes de datos lo componen y cómo se comunican? | [C4_Nivel2_Contenedores.puml](C4_Nivel2_Contenedores.puml) |
| 3. Componentes | ¿Cómo se organiza el backend? | [General](C4_Nivel3_Componentes.puml) · [Detalle de suscripciones](C4_Nivel3_Suscripciones.puml) |
| 4. Código | ¿Qué entidades forman el dominio? | [C4_Nivel4_Codigo_Clases.puml](C4_Nivel4_Codigo_Clases.puml) |

## Nivel 1: Contexto

**Sistema:** JackSoft, gestión de alimentación por suscripción.

**Actores:**
- **Cliente:** compra y renueva su plan, sigue su entrega y reporta incidencias, por web o app móvil.
- **Administrador:** gestiona la operación y valida los pagos manualmente, por web.
- **Personal de Cocina:** consulta y registra la producción, por web.
- **Domiciliario:** consulta su ruta y registra entregas y cocas, por app móvil.

**Sistemas externos:**
- **Google Maps Platform:** mapas y geocodificación.
- **Cloudinary:** comprobantes de pago y fotos de incidencias.
- **Firebase Cloud Messaging:** notificaciones push.

Bancolombia y Nequi no aparecen porque JackSoft no se integra con ellos: el cliente paga por fuera y sube el comprobante, y el administrador lo valida.

## Nivel 2: Contenedores

| Contenedor | Tecnología | Responsabilidad |
|---|---|---|
| Aplicación Web | React | Una sola aplicación; muestra las pantallas de Cliente, Administrador o Cocina según el rol |
| Aplicación Móvil | Flutter / Dart | Funciones del Cliente y del Domiciliario, incluido el envío de GPS |
| Backend API | Node.js / NestJS / TypeScript | Reglas de negocio, API REST y WebSocket |
| Base de Datos | PostgreSQL | 35 tablas del modelo `bd.uml` v3.5 |

**Interacciones:**
- Las aplicaciones consumen la API por HTTPS con JSON.
- La app envía el GPS por WebSocket, y la API publica la ubicación en vivo a quienes tienen el mapa abierto.
- La API lee y escribe en PostgreSQL por SQL.
- La API sube archivos a Cloudinary, solicita notificaciones a Firebase y geocodifica direcciones con Google Maps.
- Las aplicaciones cargan el mapa directamente desde Google Maps.

## Nivel 3: Componentes

El backend tiene 8 módulos NestJS que cubren los 22 subprocesos:

| Módulo | Subprocesos |
|---|---|
| 1. Acceso y personal | Roles, Usuarios, Acceso, Empleados |
| 2. Inventario y compras | Categoría de insumos, Insumos, Proveedores, Compras |
| 3. Producción | Categoría productos, Productos, Producción, Ficha técnica, Producto terminado |
| 4. Servicios y calendario | Categoría de servicios, Servicio, Calendario |
| 5. Clientes y suscripciones | Clientes, Suscripciones |
| 6. Logística y monitoreo | Domiciliarios, Monitoreo y rutas |
| 7. Incidencias | Incidencias |
| 8. Dashboard | Dashboard |

El diagrama de detalle muestra el patrón de cada módulo con **Clientes y suscripciones**:
- **Controladores:** reciben las solicitudes.
- **Servicios:** contienen la lógica. `LiquidacionService` calcula días facturables, descuento por festivos, recargo, cobro de cocas y total.
- **Repositorios:** leen y escriben en la base de datos.
- **Clientes externos:** conectan con Google Maps, Cloudinary y Firebase.

## Nivel 4: Modelo de dominio

[C4_Nivel4_Codigo_Clases.puml](C4_Nivel4_Codigo_Clases.puml) se genera desde `bd.uml`: 35 clases agrupadas por módulo, con sus atributos y relaciones. No incluye métodos porque el código todavía no existe. El módulo Dashboard no tiene clases propias.

## Decisiones de arquitectura

- **Inicio de sesión único:** `accesos → usuarios → clientes / empleados`.
- **Domiciliario:** es un rol, sin tabla propia.
- **Permisos:** sin tablas; lo que puede hacer cada rol se define en la aplicación.
- **Festivos:** siguen RN-02: se descuentan del precio y el vencimiento no se mueve. La Ficha aprobada dice lo contrario y está pendiente la autorización del cliente.
- **Firebase Cloud Messaging y Cloudinary:** son la elección actual. Cloudinary se usará "por el momento".
